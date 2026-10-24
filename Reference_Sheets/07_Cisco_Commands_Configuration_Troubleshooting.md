<style>@page{size:A4 landscape;margin:3.5mm}body{font-size:5pt;line-height:1.03;column-count:2;column-gap:3mm}h1,h2{column-span:all;margin:1px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}pre{font-size:4.25pt;line-height:1.02;margin:1px 0;white-space:pre-wrap}p{margin:1px 0}</style>

# IE3122 Reference 07 — Cisco Commands, Verification & Troubleshooting

> Packet Tracer lab syntax. Replace interface names, IPs, keys and policy values. Never reuse the sample passwords in production.

## VLAN, trunk, router-on-a-stick, DHCP

```ios
vlan 10
 name Staff
vlan 20
 name Guest
vlan 99
 name Native
interface fa0/2
 switchport mode access
 switchport access vlan 10
interface fa0/1
 switchport mode trunk
 switchport trunk native vlan 99
 switchport nonegotiate
! optionally restrict: switchport trunk allowed vlan 10,20,99
interface gi0/0
 no shutdown
interface gi0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
interface gi0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
ip dhcp excluded-address 192.168.10.1
ip dhcp pool VLAN10_POOL
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
```

```ios
interface range fa0/2-3
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
ip dhcp snooping
ip dhcp snooping vlan 10,20
interface fa0/1
 ip dhcp snooping trust
ip arp inspection vlan 10,20
interface fa0/1
 ip arp inspection trust
```

Verify: `show vlan brief`, `show interfaces trunk`, `show port-security interface fa0/2`, `show ip dhcp snooping`, `show ip dhcp snooping binding`, `show ip arp inspection interfaces`, `show ip arp inspection vlan 10,20`. Trust only real server/uplink paths; user access ports remain untrusted.

## STP hardening

```ios
spanning-tree mode rapid-pvst
spanning-tree vlan 1 priority 4096
interface fa0/1
 spanning-tree portfast
 spanning-tree bpduguard enable
interface range fa0/1-2
 spanning-tree guard root
interface range gi0/1-2
 spanning-tree guard loop
```

Use Root Guard only where a root must never appear; Loop Guard on redundant switch links; never PortFast a normal switch link. BPDU Filter can create silent loops—avoid unless specifically designed. Legacy: `spanning-tree uplinkfast`, `spanning-tree backbonefast`; RSTP normally supersedes. Verify: `show spanning-tree vlan 1`, `show spanning-tree summary`, `show interfaces status`.

## OSPF and EIGRP authentication

```ios
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 10.0.12.0 0.0.0.3 area 0
 area 0 authentication message-digest
interface gi0/1
 ip ospf message-digest-key 1 md5 OspfKey5
```

```ios
router eigrp 10
 network 192.168.1.0 0.0.0.255
 network 10.0.12.0 0.0.0.3
key chain EIGRPCHAIN
 key 1
  key-string EigrpKey5
interface gi0/1
 ip authentication mode eigrp 10 md5
 ip authentication key-chain eigrp 10 EIGRPCHAIN
```

Verify OSPF: `show ip ospf neighbor`, `show ip ospf interface gi0/1`, `show ip route ospf`. EIGRP: `show key chain`, `show ip eigrp neighbors`, `show ip route eigrp`. If adjacency fails: interface up/up and same subnet → protocol/AS/area/network statement → passive setting → matching auth mode/key ID/key/timing → ACL.

## ACL patterns and DMZ policy

```ios
! Outside: public HTTP; trusted host FTP; established TCP replies; deny rest
access-list 101 permit tcp any host 192.168.100.10 eq 80
access-list 101 permit tcp host 203.0.113.4 host 192.168.100.11 eq 21
access-list 101 permit tcp any any established
access-list 101 deny ip any any
interface gi0/0
 ip access-group 101 in
! Contain DMZ from Inside
access-list 102 deny ip 192.168.100.0 0.0.0.255 192.168.200.0 0.0.0.255
access-list 102 permit ip any any
interface gi0/1
 ip access-group 102 in
! Inside: one admin may Telnet to web server; all others denied; other IP allowed
access-list 103 permit tcp host 192.168.200.11 host 192.168.100.10 eq 23
access-list 103 deny tcp any host 192.168.100.10 eq 23
access-list 103 permit ip any any
interface gi0/2
 ip access-group 103 in
```

Named conversion: `ip access-list extended DENY_FTP_ADMIN` → `deny tcp 192.168.40.0 0.0.0.255 host 10.0.0.50 eq 21` → `permit ip any any`; apply with `ip access-group DENY_FTP_ADMIN in`. Verify `show access-lists`, interface attachment/direction, counters, order and implicit deny; test both permitted and forbidden matrix cells.

## GRE over IPsec site-to-site

```ios
! R1 tunnel; R2 mirrors .2 and destination .1
interface Tunnel0
 ip address 172.16.0.1 255.255.255.252
 tunnel source gi0/1
 tunnel destination 203.0.113.2
ip route 192.168.20.0 255.255.255.0 172.16.0.2
! PT 1941 prerequisite, save/reload
license boot module c1900 technology-package securityk9
crypto isakmp policy 10
 encryption aes 256
 authentication pre-share
 group 5
crypto isakmp key vpnpa55 address 203.0.113.2
crypto ipsec transform-set VPN-SET esp-aes esp-sha-hmac
access-list 110 permit gre host 203.0.113.1 host 203.0.113.2
crypto map VPN-MAP 10 ipsec-isakmp
 set peer 203.0.113.2
 set transform-set VPN-SET
 match address 110
interface gi0/1
 crypto map VPN-MAP
```

R2 mirrors WAN peers/routes/ACL direction. Lab Group 5 is simulator compatibility; lecture’s realistic minimum is Group 14 where supported. Trigger interesting traffic, then `show interfaces tunnel 0`, `show crypto isakmp sa`, `show crypto ipsec sa`. Troubleshoot: WAN reachability/routes → tunnel source/destination → mirrored IKE policy/PSK/peer → mirror ACLs → transform set → crypto map on WAN interface → generate traffic/check encaps/decaps counters. Plain packet exposes PC addresses/payload; GRE shows router outer addresses but readable inner packet; ESP protects inner content while outer peer IPs remain visible.

## AAA with fallback

```ios
username localadmin privilege 15 secret LocalPa55
aaa new-model
aaa authentication login default local
line vty 0 4
 login authentication default
 transport input telnet
! PT legacy TACACS+ form
tacacs-server host 192.168.1.2
tacacs-server key tacacspa55
aaa authentication login default group tacacs+ local
! or RADIUS
radius-server host 192.168.2.2
radius-server key radiuspa55
aaa authentication login default group radius local
```

Test local first → remote server user → server unreachable and local fallback. Explicit server rejection normally does not fall through; timeout/error does. Use SSH, protected secrets, redundant servers and out-of-band recovery in production.

## Universal verification checklist

1. Physical/interface: correct cable, `no shutdown`, `show ip interface brief`, up/up. 2. L2: VLAN membership, trunks/native/allowed list, STP state. 3. L3: address/mask/gateway/routes, ping next hop. 4. Policy: exact source/destination/protocol/port, order, direction, counters. 5. Crypto/AAA: reachability, matching identities/keys/policies and time. 6. Test a permitted case, denied case, failure/fallback case; save evidence. 7. `copy running-config startup-config` only after verified behavior.
