# Cisco Networking Command Cheat Sheet

## Table of Contents
- [OSPF (Open Shortest Path First)](#ospf)
- [HSRP (Hot Standby Router Protocol)](#hsrp)
- [STP (Spanning Tree Protocol)](#stp)
- [VLAN (Virtual LAN)](#vlan)
- [BGP (Border Gateway Protocol)](#bgp)
- [EIGRP (Enhanced Interior Gateway Routing Protocol)](#eigrp)
- [ACL (Access Control Lists)](#acl)
- [NAT (Network Address Translation)](#nat)
- [VTP (VLAN Trunking Protocol)](#vtp)
- [Interface Configuration](#interface-configuration)
- [General Management Commands](#general-management-commands)

---

## OSPF

**OSPF (Open Shortest Path First)** is a link-state routing protocol for IP networks. It uses Dijkstra's algorithm to calculate the shortest path to destinations. OSPF is an interior gateway protocol (IGP) that operates within a single autonomous system (AS) and supports hierarchical routing through areas, with Area 0 being the backbone area. It's widely used in enterprise networks for its fast convergence, scalability, and support for VLSM and CIDR.

| Command | Description |
|---------|-------------|
| `router ospf <process-id>` | Enters OSPF router configuration mode |
| `network <network> <wildcard-mask> area <area-id>` | Defines OSPF networks and assigns them to an area |
| `area <area-id> stub` | Configures an area as a stub area |
| `area <area-id> nssa` | Configures an area as a Not-So-Stubby Area (NSSA) |
| `area <area-id> range <network> <mask>` | Summarizes routes within an area |
| `router-id <ip-address>` | Manually sets the OSPF router ID |
| `passive-interface <interface>` | Prevents OSPF adjacency on the interface |
| `auto-cost reference-bandwidth <mbps>` | Adjusts OSPF cost calculation reference bandwidth |
| `ip ospf cost <value>` | Manually sets OSPF interface cost |
| `ip ospf priority <value>` | Sets OSPF priority for DR/BDR election |
| `ip ospf hello-interval <seconds>` | Sets OSPF hello interval |
| `ip ospf dead-interval <seconds>` | Sets OSPF dead interval |
| `ip ospf authentication key <key>` | Enables OSPF simple password authentication |
| `ip ospf authentication message-digest` | Enables OSPF MD5 authentication |
| `ip ospf message-digest-key <key-id> md5 <key>` | Sets OSPF MD5 authentication key |
| `show ip ospf` | Displays OSPF process information |
| `show ip ospf neighbor` | Shows OSPF neighbor relationships |
| `show ip ospf interface` | Displays OSPF interface details |
| `show ip ospf database` | Shows OSPF link-state database |
| `show ip route ospf` | Displays OSPF routes in the routing table |
| `clear ip ospf process` | Resets OSPF process |

---

## HSRP

**HSRP (Hot Standby Router Protocol)** is a Cisco proprietary redundancy protocol that provides gateway redundancy by allowing multiple routers to share a virtual IP and MAC address. HSRP creates a virtual default gateway with one active router and one or more standby routers. If the active router fails, a standby router takes over seamlessly, ensuring continuous network availability. It uses priority values (default 100) to determine the active router, with preempt allowing a higher-priority router to take the active role.

| Command | Description |
|---------|-------------|
| `standby <group-number> ip <virtual-ip>` | Enables HSRP and sets virtual IP address |
| `standby <group-number> priority <value>` | Sets HSRP priority (default 100) |
| `standby <group-number> preempt` | Enables router to preempt active role if priority higher |
| `standby <group-number> preempt delay <seconds>` | Sets preemption delay |
| `standby <group-number> track <interface>` | Tracks interface status for priority adjustment |
| `standby <group-number> authentication <string>` | Sets HSRP authentication (deprecated) |
| `standby <group-number> authentication md5 key-string <key>` | Sets HSRP MD5 authentication |
| `standby <group-number> timers <hello> <hold>` | Configures HSRP hello and hold timers |
| `standby <group-number> name <group-name>` | Assigns a name to HSRP group |
| `standby version <1&#124;2>` | Sets HSRP version |
| `show standby` | Displays HSRP status and configuration |
| `show standby brief` | Shows summarized HSRP information |

---

## STP (Spanning Tree Protocol)

**STP (Spanning Tree Protocol)** is a Layer 2 network protocol that prevents loops in Ethernet networks by creating a loop-free logical topology. It detects and blocks redundant paths while keeping them as backups in case of link failure. STP elects a root bridge and then determines which ports should be blocking and which should be forwarding. Variants include RSTP (Rapid Spanning Tree) for faster convergence and MSTP (Multiple Spanning Tree) for mapping multiple VLANs to a single spanning tree.

| Command | Description |
|---------|-------------|
| `spanning-tree mode <pvst&#124;rapid-pvst&#124;mst>` | Sets STP mode (PVST+, Rapid-PVST+, MST) |
| `spanning-tree vlan <vlan-id> priority <value>` | Sets STP priority for a VLAN |
| `spanning-tree vlan <vlan-id> root primary` | Configures switch as primary root bridge |
| `spanning-tree vlan <vlan-id> root secondary` | Configures switch as secondary root bridge |
| `spanning-tree portfast` | Enables PortFast on access ports |
| `spanning-tree portfast bpduguard default` | Enables BPDU Guard globally |
| `spanning-tree bpduguard enable` | Enables BPDU Guard on interface |
| `spanning-tree bpdufilter enable` | Enables BPDU Filter on interface |
| `spanning-tree guard root` | Enables Root Guard on interface |
| `spanning-tree guard loop` | Enables Loop Guard on interface |
| `spanning-tree link-type <point-to-point&#124;shared>` | Sets STP link type |
| `spanning-tree mst configuration` | Enters MST configuration mode |
| `spanning-tree cost <value>` | Sets STP path cost |
| `spanning-tree port-priority <value>` | Sets STP port priority |
| `spanning-tree vlan <vlan-id> hello-time <seconds>` | Sets hello timer |
| `spanning-tree vlan <vlan-id> forward-time <seconds>` | Sets forward delay timer |
| `spanning-tree vlan <vlan-id> max-age <seconds>` | Sets max age timer |
| `show spanning-tree` | Displays STP status |
| `show spanning-tree vlan <vlan-id>` | Shows STP for specific VLAN |
| `show spanning-tree detail` | Shows detailed STP information |
| `clear spanning-tree detected-protocols` | Clears detected protocols |

---

## VLAN

**VLAN (Virtual LAN)** is a Layer 2 network segmentation technique that logically groups devices into separate broadcast domains, regardless of their physical location. VLANs improve security, reduce broadcast traffic, and simplify network management. Traffic between VLANs requires a router or Layer 3 switch. VLANs are identified by numbers (1-4094), with VLAN 1 being the default native VLAN. Trunk ports carry multiple VLAN traffic using 802.1Q tagging.

| Command | Description |
|---------|-------------|
| `vlan <vlan-id>` | Creates a VLAN and enters VLAN configuration mode |
| `name <vlan-name>` | Assigns a name to the VLAN |
| `switchport mode access` | Sets interface to access mode |
| `switchport access vlan <vlan-id>` | Assigns VLAN to access port |
| `switchport mode trunk` | Sets interface to trunk mode |
| `switchport trunk allowed vlan <vlan-list>` | Specifies allowed VLANs on trunk |
| `switchport trunk encapsulation dot1q` | Sets 802.1Q encapsulation |
| `switchport trunk native vlan <vlan-id>` | Sets native VLAN for trunk |
| `switchport voice vlan <vlan-id>` | Assigns voice VLAN to port |
| `switchport nonegotiate` | Disables DTP negotiation |
| `switchport port-security` | Enables port security |
| `switchport port-security maximum <max>` | Sets maximum MAC addresses allowed |
| `switchport port-security violation <protect&#124;restrict&#124;shutdown>` | Sets violation action |
| `switchport port-security mac-address <mac>` | Statically assigns MAC address |
| `switchport port-security mac-address sticky` | Enables sticky MAC learning |
| `show vlan` | Displays VLAN information |
| `show vlan brief` | Shows summarized VLAN information |
| `show interface switchport` | Displays switchport configuration |
| `show interface trunk` | Shows trunk interfaces |
| `show mac address-table` | Displays MAC address table |
| `show spanning-tree vlan <vlan-id>` | Shows STP for VLAN |

---

## BGP

**BGP (Border Gateway Protocol)** is an exterior gateway protocol (EGP) used to exchange routing information between autonomous systems on the Internet. BGP makes routing decisions based on paths, network policies, and rule-sets configured by network administrators. It uses TCP port 179 for communication and supports classless inter-domain routing (CIDR). BGP is essential for ISPs and large enterprises connecting to multiple networks, choosing the best path based on attributes like AS path, MED, and local preference.

| Command | Description |
|---------|-------------|
| `router bgp <as-number>` | Enters BGP router configuration mode |
| `bgp router-id <ip-address>` | Sets BGP router ID |
| `neighbor <ip-address> remote-as <as-number>` | Configures BGP neighbor |
| `neighbor <ip-address> description <text>` | Adds description to neighbor |
| `neighbor <ip-address> password <password>` | Sets MD5 authentication |
| `neighbor <ip-address> ebgp-multihop <hops>` | Allows eBGP multihop |
| `neighbor <ip-address> update-source <interface>` | Sets source interface |
| `neighbor <ip-address> timers <keepalive> <holdtime>` | Sets BGP timers |
| `network <network> mask <mask>` | Advertises network to BGP |
| `aggregate-address <network> <mask>` | Creates aggregate route |
| `aggregate-address <network> <mask> summary-only` | Creates aggregate and suppresses specifics |
| `redistribute <protocol>` | Redistributes routes into BGP |
| `redistribute static` | Redistributes static routes |
| `redistribute connected` | Redistributes connected routes |
| `default-information originate` | Advertises default route |
| `no synchronization` | Disables BGP synchronization |
| `bgp always-compare-med` | Enables MED comparison |
| `bgp bestpath as-path ignore` | Ignores AS path length in path selection |
| `bgp log-neighbor changes` | Logs neighbor changes |
| `maximum-paths <number>` | Sets maximum parallel BGP paths |
| `route-reflector-client` | Configures route reflector client |
| `bgp cluster-id <cluster-id>` | Sets route reflector cluster ID |
| `show ip bgp` | Displays BGP table |
| `show ip bgp summary` | Shows BGP neighbor summary |
| `show ip bgp neighbors` | Displays BGP neighbor details |
| `show ip bgp regexp <pattern>` | Filters BGP routes with regex |
| `show ip bgp prefix <network>` | Shows specific prefix details |
| `clear ip bgp <neighbor>` | Resets BGP session |
| `clear ip bgp *` | Resets all BGP sessions |

---

## EIGRP

**EIGRP (Enhanced Interior Gateway Routing Protocol)** is a Cisco-proprietary advanced distance-vector routing protocol that combines features of both distance-vector and link-state protocols. EIGRP uses Diffusing Update Algorithm (DUAL) for fast convergence and supports VLSM and CIDR. It calculates metrics using bandwidth, delay, reliability, load, and MTU (K values). EIGRP supports unequal-cost load balancing and forms neighbor relationships using hello packets, making it efficient for medium to large enterprise networks.

| Command | Description |
|---------|-------------|
| `router eigrp <as-number>` | Enters EIGRP router configuration mode |
| `network <network> [wildcard-mask]` | Defines EIGRP networks |
| `no auto-summary` | Disables automatic summarization |
| `eigrp router-id <ip-address>` | Sets EIGRP router ID |
| `eigrp log-neighbor changes` | Logs EIGRP neighbor changes |
| `eigrp stub <receive-only&#124;connected&#124;static&#124;summary>` | Configures EIGRP stub routing |
| `passive-interface <interface>` | Suppresses EIGRP hellos on interface |
| `metric weights <tos> <k1> <k2> <k3> <k4> <k5>` | Adjusts EIGRP metric calculation |
| `variance <multiplier>` | Allows unequal-cost load balancing |
| `maximum-paths <number>` | Sets maximum EIGRP paths |
| `timers active-time <minutes>` | Sets EIGRP active timer |
| `ip bandwidth-percent eigrp <percent>` | Limits EIGRP bandwidth usage |
| `ip summary-address eigrp <as> <network> <mask>` | Creates EIGRP summary route |
| `show ip eigrp neighbors` | Displays EIGRP neighbors |
| `show ip eigrp topology` | Shows EIGRP topology table |
| `show ip eigrp interfaces` | Displays EIGRP interfaces |
| `show ip route eigrp` | Shows EIGRP routes |
| `debug eigrp packet` | Debugs EIGRP packets |
| `debug eigrp neighbor` | Debugs EIGRP neighbor events |

---

## ACL (Access Control Lists)

**ACL (Access Control Lists)** are packet filters that control network traffic by permitting or denying packets based on criteria such as source/destination IP addresses, protocol types, and port numbers. Standard ACLs (1-99, 1300-1999) filter based only on source IP, while extended ACLs (100-199, 2000-2699) can filter based on source, destination, protocol, and ports. ACLs are applied to interfaces in either inbound or outbound direction and are processed sequentially until a match is found.

| Command | Description |
|---------|-------------|
| `access-list <number> <permit&#124;deny> <protocol> <source> <destination>` | Creates numbered ACL |
| `ip access-list standard <name>` | Creates named standard ACL |
| `ip access-list extended <name>` | Creates named extended ACL |
| `permit <source> [wildcard]` | Permits traffic (standard ACL) |
| `deny <source> [wildcard]` | Denies traffic (standard ACL) |
| `permit <protocol> <source> <destination> [eq&#124;gt&#124;lt <port>]` | Permits traffic (extended ACL) |
| `deny <protocol> <source> <destination> [eq&#124;gt&#124;lt <port>]` | Denies traffic (extended ACL) |
| `permit ip any any` | Permits all IP traffic |
| `deny ip any any` | Denies all IP traffic |
| `remark <text>` | Adds comment to ACL |
| `ip access-group <acl> <in&#124;out>` | Applies ACL to interface |
| `ip access-list resequence <name> <start> <step>` | Resequences ACL entries |
| `show access-lists` | Displays all ACLs |
| `show access-lists <number>` | Shows specific numbered ACL |
| `show access-lists <name>` | Shows specific named ACL |
| `show access-lists brief` | Displays summarized ACL information |
| `show access-lists summary` | Shows ACL summary statistics |
| `show ip access-list` | Shows all IP ACLs |
| `show ip access-list <name>` | Shows specific IP ACL with details |
| `show ip access-lists brief` | Shows summarized IP ACL information |
| `show ip access-lists summary` | Shows IP ACL summary statistics |
| `show ip interface <interface>` | Shows ACLs applied to interface |
| `show running-config | include access-list` | Shows ACLs in running config |
| `clear access-list counters` | Clears ACL counters |
| `clear access-list counters <acl>` | Clears counters for specific ACL |
| `clear access-list counters <in|out> <interface>` | Clears ACL counters on interface |
| `no access-list <number>` | Deletes numbered ACL |
| `no ip access-list <name>` | Deletes named ACL |
| `no ip access-group <acl> <in|out>` | Removes ACL from interface |
| `ip access-list log-update <threshold>` | Sets logging threshold for ACL matches |
| `ip access-list logging interval <seconds>` | Sets logging interval for ACL events |
| `time-range <name>` | Creates time-range for time-based ACLs |
| `absolute start <date> <time>` | Sets absolute start time for time-range |
| `absolute end <date> <time>` | Sets absolute end time for time-range |
| `periodic <days> <start-time> <end-time>` | Sets periodic time for time-range |
| `permit tcp host <source> host <destination> eq <port>` | Permits TCP from specific host |
| `permit udp any any` | Permits all UDP traffic |
| `permit icmp any any` | Permits all ICMP traffic |
| `deny tcp any any eq <port>` | Denies TCP to specific port |
| `deny udp any any` | Denies all UDP traffic |

---

## NAT (Network Address Translation)

**NAT (Network Address Translation)** is a method of remapping IP address space by modifying network address information in IP packet headers while in transit. NAT conserves IPv4 addresses by allowing multiple devices to share a single public IP address. Types include Static NAT (one-to-one mapping), Dynamic NAT (pool-based mapping), and PAT (Port Address Translation or NAT Overload) which maps multiple private IPs to one public IP using different ports. NAT is essential for connecting private networks to the Internet.

| Command | Description |
|---------|-------------|
| `ip nat inside source static <local-ip> <global-ip>` | Static NAT (one-to-one) |
| `ip nat inside source list <acl> pool <pool-name>` | Dynamic NAT using ACL |
| `ip nat inside source list <acl> interface <interface> overload` | PAT (Port Address Translation) |
| `ip nat pool <name> <start-ip> <end-ip> <netmask&#124;prefix-length>` | Creates NAT address pool |
| `ip nat inside source list <acl> pool <pool> overload` | PAT using pool |
| `ip nat inside` | Marks interface as inside |
| `ip nat outside` | Marks interface as outside |
| `ip nat translation timeout <seconds>` | Sets NAT translation timeout |
| `show ip nat translations` | Displays NAT translations |
| `show ip nat statistics` | Shows NAT statistics |
| `clear ip nat translation *` | Clears all NAT translations |
| `clear ip nat translation <inside&#124;outside> <ip>` | Clears specific translation |

---

## VTP (VLAN Trunking Protocol)

**VTP (VLAN Trunking Protocol)** is a Cisco proprietary Layer 2 messaging protocol that manages the addition, deletion, and renaming of VLANs across a switched network. VTP ensures VLAN consistency by propagating VLAN configuration changes to all switches in the same VTP domain. Modes include Server (can create/modify/delete VLANs), Client (receives and applies VLAN changes), and Transparent (forwards VTP messages but doesn't sync, allowing local VLAN control). VTP reduces administrative overhead in large networks.

| Command | Description |
|---------|-------------|
| `vtp mode <server&#124;client&#124;transparent>` | Sets VTP mode |
| `vtp domain <domain-name>` | Sets VTP domain name |
| `vtp password <password>` | Sets VTP password |
| `vtp pruning` | Enables VTP pruning |
| `vtp version <1&#124;2&#124;3>` | Sets VTP version |
| `vtp filename <filename>` | Sets VTP configuration filename |
| `show vtp status` | Displays VTP status |
| `show vtp counters` | Shows VTP counters |
| `show vtp interface` | Displays VTP interfaces |

---

## Interface Configuration

| Command | Description |
|---------|-------------|
| `interface <type> <number>` | Enters interface configuration mode |
| `interface <type> <module>/<number>` | Enters modular interface |
| `interface range <range>` | Configures multiple interfaces |
| `ip address <ip> <mask>` | Assigns IP address |
| `ip address <ip> <mask> secondary` | Assigns secondary IP address |
| `no shutdown` | Enables the interface |
| `shutdown` | Disables the interface |
| `description <text>` | Adds description to interface |
| `bandwidth <kbps>` | Sets bandwidth for routing metrics |
| `ip helper-address <ip>` | Configures DHCP relay |
| `ip flow ingress` | Enables NetFlow ingress |
| `ip flow egress` | Enables NetFlow egress |
| `duplex <auto&#124;full&#124;half>` | Sets duplex mode |
| `speed <auto&#124;10&#124;100&#124;1000>` | Sets interface speed |
| `mdix auto` | Enables auto MDIX |
| `channel-group <number> mode <on&#124;auto&#124;desirable>` | Configures EtherChannel |
| `show ip interface` | Shows IP interface details |
| `show ip interface brief` | Shows summarized interface status |
| `show interfaces` | Displays all interface statistics |
| `show running-config interface <interface>` | Shows interface configuration |

---

## General Management Commands

| Command | Description |
|---------|-------------|
| `enable` | Enters privileged EXEC mode |
| `configure terminal` | Enters global configuration mode |
| `hostname <name>` | Sets device hostname |
| `banner motd <delimiter>` | Sets message of the day banner |
| `username <name> privilege <level> secret <password>` | Creates user account |
| `enable secret <password>` | Sets privileged mode password |
| `service password-encryption` | Encrypts passwords in config |
| `no ip domain-lookup` | Disables DNS lookup |
| `ip domain-name <domain>` | Sets domain name |
| `ip name-server <server>` | Sets DNS server |
| `logging console <level>` | Sets console logging level |
| `logging buffered <level>` | Sets buffered logging level |
| `logging host <ip>` | Sets syslog server |
| `line console 0` | Enters console line configuration |
| `line vty 0 4` | Enters VTY line configuration |
| `login local` | Enables local authentication |
| `password <password>` | Sets line password |
| `transport input <telnet&#124;ssh&#124;none>` | Sets allowed protocols |
| `crypto key generate rsa` | Generates RSA keys for SSH |
| `ip ssh version <1&#124;2>` | Sets SSH version |
| `show running-config` | Displays current configuration |
| `show startup-config` | Displays saved configuration |
| `copy running-config startup-config` | Saves configuration |
| `write memory` | Saves configuration (shorthand) |
| `erase startup-config` | Erases saved configuration |
| `reload` | Reloads the device |
| `show version` | Shows system version and hardware |
| `show flash:` | Shows flash file system |
| `show processes cpu` | Shows CPU utilization |
| `show memory` | Shows memory statistics |
| `show clock` | Displays system clock |
| `show logging` | Shows system logs |
| `ping <ip>` | Tests network connectivity |
| `traceroute <ip>` | Traces route to destination |
| `telnet <ip>` | Establishes Telnet connection |
| `ssh -l <user> <ip>` | Establishes SSH connection |
| `terminal monitor` | Enables logging to terminal |
| `terminal length 0` | Disables pagination |

---

## Quick Reference

### Common Mode Navigation
- `User EXEC (>)` → `Privileged EXEC (#)`: `enable`
- `Privileged EXEC` → `Global Config ((config)#)`: `configure terminal`
- `Global Config` → `Interface Config ((config-if)#)`: `interface <type> <number>`
- `Global Config` → `Router Config ((config-router)#)`: `router <protocol>`
- Exit any mode: `exit` or `end` (to privileged EXEC)

### View Commands
- `show running-config` - Current configuration
- `show startup-config` - Saved configuration
- `show version` - System information
- `show ip interface brief` - Interface status
- `show ip route` - Routing table
- `show processes cpu` - CPU usage

### Save Configuration
- `copy running-config startup-config`
- `write memory` or `wr`

---

*This cheat sheet covers common Cisco IOS commands. Always verify commands in your specific IOS version and device model.*
