# Networking Lecture Notes - Comprehensive

Based on CT133-3-2 Switching and Routing Essential Course

---

## Table of Contents
1. [Module Introduction](#module-introduction)
2. [Basic Configuration and Switching Concepts](#basic-configuration-and-switching-concepts)
3. [VLAN](#vlan)
4. [Inter-VLAN Routing](#inter-vlan-routing)
5. [STP Concepts](#stp-concepts)
6. [EtherChannel](#etherchannel)
7. [Routing Concepts](#routing-concepts)
8. [DHCPv4](#dhcpv4)
9. [WLAN Concepts and Configurations](#wlan-concepts-and-configurations)
10. [LAN Security Concepts](#lan-security-concepts)
11. [FHRP](#fhrp)
12. [IP Static Routing](#ip-static-routing)
13. [SLAAC and DHCPv6](#slaac-and-dhcpv6)
14. [Basic IP Addressing (FLSM vs VLSM)](#basic-ip-addressing-flsm-vs-vlsm)

---

## Module Introduction


### Module Coverage

The module covers:
- Architecture of routers and switches in small networks
- Switching and routing operations
- Wireless Local Area Networks (WLAN)
- Security concepts
- Configuration and troubleshooting of routers and switches
- Advanced functionality using security best practices
- Common issues with protocols in both IPv4 and IPv6 networks

---

## Basic Configuration and Switching Concepts

### Module Overview

This module focuses on configuring devices using security best practices. Students will learn to configure switches with initial settings, configure switch ports, secure remote access, configure basic router settings, and verify connectivity between directly connected networks.

### Learning Objectives Summary

| Topic | Objective |
|-------|-----------|
| Configure a Switch with Initial Settings | Configure initial settings on a Cisco switch |
| Configure Switch Ports | Configure switch ports to meet network requirements |
| Secure Remote Access | Configure secure management access on a switch |
| Basic Router Configuration | Configure basic settings on a router to route between two directly-connected networks |
| Verify Directly Connected Networks | Verify connectivity between two networks that are directly connected to a router |

### Key Terms

| Term | Definition |
|------|------------|
| Basic Device Configuration | Initial setup of network devices |
| boot system flash | Boot command to specify IOS location |
| Power over Ethernet (PoE) | Delivering power over network cables |
| duplex | Full or half-duplex communication mode |
| speed | Link speed (10/100/1000 Mbps) |
| auto-mdix | Automatic medium-dependent interface crossover |
| show controllers ethernet controller X | Display controller hardware details |
| show flash | Display contents of flash memory |
| show history | Display command history |
| show ip ssh | Display SSH configuration |
| ip ssh version 2 | Enable SSH version 2 |
| Loopback Interface | Virtual interface for testing and management |
| interface loopback x | Create loopback interface |
| include | Filter command output |
| exclude | Exclude from command output |
| section | Display configuration section |
| terminal history size | Set command history buffer size |
| Frame Forwarding | Process of forwarding frames through switch |
| Switching | Process of forwarding frames based on MAC address |

### Initial Switch Configuration

Proper initial switch configuration is essential for network security and management. The following settings should be configured on every switch:

#### Configuration Steps and Commands

| Configuration Step | Command | Purpose |
|-------------------|---------|---------|
| Set hostname | `hostname Switch1` | Identifies the switch in the network |
| Set enable secret | `enable secret class` | Sets encrypted privileged mode password |
| Set banner | `banner motd #Authorized Access Only#` | Displays legal warning at login |
| Configure VLAN 1 | `interface vlan 1` → `ip address 192.168.1.2 255.255.255.0` | Sets management IP address |
| Enable VLAN 1 | `no shutdown` | Activates the VLAN interface |
| Set default gateway | `ip default-gateway 192.168.1.1` | Sets default gateway for remote management |
| Configure console | `line console 0` → `password cisco` → `login` | Secures physical console access |
| Configure VTY | `line vty 0 4` → `password cisco` → `login` | Secures remote Telnet/SSH access |

#### Security Best Practices

| Practice | Description | Command |
|----------|-------------|---------|
| Use enable secret | Encrypted password instead of enable password | `enable secret <password>` |
| Disable unused ports | Prevent unauthorized access | `shutdown` on unused ports |
| Set banners | Legal warnings and information | `banner motd #<message>#` |
| Use strong passwords | Complex passwords with mixed characters | Minimum 8 characters, uppercase, lowercase, numbers, special characters |
| Configure description | Identify ports and interfaces | `description <text>` |

### Secure Remote Access

Secure remote access is critical for network management. SSH should always be used instead of Telnet for encrypted communication.

#### SSH Configuration Process

| Step | Command | Description |
|------|---------|-------------|
| 1 | `hostname Router1` | Set hostname (required for RSA keys) |
| 2 | `ip domain-name example.com` | Set domain name (required for RSA keys) |
| 3 | `crypto key generate rsa` | Generate RSA keys (use 1024+ bits) |
| 4 | `ip ssh version 2` | Enable SSH version 2 (more secure) |
| 5 | `line vty 0 4` | Enter VTY configuration mode |
| 6 | `transport input ssh` | Allow only SSH (disable Telnet) |
| 7 | `username admin privilege 15 secret password` | Create local user account |
| 8 | `login local` | Enable local authentication |

#### SSH vs Telnet Comparison

| Feature | SSH | Telnet |
|---------|-----|--------|
| Encryption | Yes (encrypted) | No (plaintext) |
| Security | High | Low |
| Port | 22 | 23 |
| Authentication | Supports public key | Password only |
| Recommendation | Use SSH | Avoid in production |

### Switch Port Configuration

Switch ports can be configured as access ports or trunk ports depending on their role in the network.

#### Port Types and Configuration

| Port Type | Mode | Configuration Commands | Use Case |
|-----------|------|------------------------|----------|
| Access | Access | `switchport mode access` → `switchport access vlan 10` | Connects end devices (PCs, printers) |
| Trunk | Trunk | `switchport mode trunk` → `switchport trunk allowed vlan 10,20,30` | Connects switches, routers, or servers |
| Voice | Access + Voice | `switchport mode access` → `switchport access vlan 10` → `switchport voice vlan 30` | Connects IP phones with separate voice VLAN |
| PortFast | Edge | `spanning-tree portfast` | Skips listening/learning states for immediate forwarding |

#### Port Security Configuration

| Command | Description |
|---------|-------------|
| `switchport port-security` | Enable port security on the interface |
| `switchport port-security maximum 3` | Set maximum number of MAC addresses allowed |
| `switchport port-security violation shutdown` | Set action when violation occurs (protect/restrict/shutdown) |
| `switchport port-security mac-address sticky` | Learn MAC addresses dynamically |
| `switchport port-security mac-address 00:11:22:33:44:55` | Statically assign MAC address |

### Basic Router Configuration

Routers require basic configuration to route between directly connected networks. This includes configuring interfaces and enabling routing.

#### Interface Configuration

| Interface Type | Configuration Commands | Notes |
|----------------|------------------------|-------|
| GigabitEthernet | `interface gigabitethernet 0/0` → `ip address 192.168.1.1 255.255.255.0` → `no shutdown` | LAN interface configuration |
| Serial (DCE) | `interface serial 0/0/0` → `ip address 10.1.1.1 255.255.255.252` → `clock rate 64000` → `no shutdown` | DCE end requires clock rate |
| Serial (DTE) | `interface serial 0/0/0` → `ip address 10.1.1.2 255.255.255.252` → `no shutdown` | DTE end doesn't require clock rate |

#### Other Basic Router Settings

| Setting | Command | Purpose |
|---------|---------|---------|
| Hostname | `hostname Router1` | Set router hostname |
| Enable secret | `enable secret class` | Set privileged mode password |
| Banner | `banner motd #Authorized Access Only#` | Set login banner |
| Loopback interface | `interface loopback 0` → `ip address 1.1.1.1 255.255.255.255` | Create virtual interface for testing |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show running-config` | Displays current configuration |
| `show startup-config` | Displays saved configuration |
| `show ip interface brief` | Shows interface status |
| `show ip route` | Displays routing table |
| `ping <ip-address>` | Tests network connectivity |
| `traceroute <ip-address>` | Shows path to destination |
| `show version` | Shows system version and hardware |
| `show flash` | Shows contents of flash memory |
| `show history` | Shows command history |
| `show controllers ethernet controller X` | Shows controller hardware details |
| `show controllers phy` | Shows physical layer details |

---

## VLAN

### Module Overview

This module explains how network protocols enable devices to access local and remote network resources. It covers VLAN concepts, multi-switched environments, VLAN configuration, trunking, and Dynamic Trunking Protocol (DTP).

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Overview of VLANs | Explain the purpose of VLANs in a switched network |
| VLANs in a Multi-Switched Environment | Explain how a switch forwards frames based on VLAN configuration in a multi-switch environment |
| VLAN Configuration | Configure a switch port to be assigned to a VLAN based on requirements |
| VLAN Trunks | Configure a trunk port on a LAN switch |
| Dynamic Trunking Protocol | Configure Dynamic Trunking Protocol (DTP) |

### Key Terms

| Term | Definition |
|------|------------|
| VLAN | Virtual Local Area Network - logical broadcast domain |
| Logical broadcast domain | Network segment defined by VLAN membership |
| Data VLAN | Carries user-generated traffic |
| Default VLAN | VLAN 1 on Cisco switches (cannot be deleted) |
| Native VLAN | Untagged VLAN on trunk port (default VLAN 1) |
| Management VLAN | Used for network management traffic |
| Voice VLAN | Dedicated to IP phone traffic |
| VLAN Trunk | Link carrying traffic for multiple VLANs |
| VLAN Segmentation | Dividing network into logical groups |
| IEEE 802.1Q | Industry standard trunking protocol |
| VLAN Tagging | Process of adding VLAN identifier to frame |
| Canonical Format Identifier (CFI) | Part of 802.1Q tag |
| User Priority | Priority field in 802.1Q tag |
| VLAN ID | VLAN number (1-4094) |

### Overview of VLANs

A Virtual LAN (VLAN) is a logical broadcast domain that groups devices based on logical rather than physical location. VLANs are used to segment switched Layer 2 networks for various reasons.

#### Why Use VLANs?

| Benefit | Description |
|---------|-------------|
| Security | Isolates traffic between different groups or departments |
| Performance | Reduces broadcast traffic by containing it to VLAN |
| Cost | Eliminates need for separate physical switches |
| Flexibility | Easy to move devices between VLANs without recabling |
| Management | Simplifies network administration by grouping devices logically |

#### VLAN Types

| VLAN Type | Description | VLAN Range | Example |
|-----------|-------------|------------|---------|
| Data VLAN | Carries user-generated traffic | 2-1001 | VLAN 10 for Sales, VLAN 20 for Engineering |
| Voice VLAN | Dedicated to IP phone traffic | 2-1001 | VLAN 30 for Voice |
| Management VLAN | Used for network management | 2-1001 | VLAN 99 for Management |
| Native VLAN | Untagged traffic on trunk | 1 (default), can be changed | VLAN 999 (custom native VLAN) |
| Default VLAN | Default VLAN on Cisco switches | 1 | Cannot be deleted |

### VLAN Configuration

#### Creating VLANs

| Command | Description |
|---------|-------------|
| `vlan 10` | Create VLAN 10 and enter VLAN configuration mode |
| `name Sales` | Assign name to VLAN 10 |
| `no vlan 10` | Delete VLAN 10 |

#### Example VLAN Configuration

```
configure terminal
vlan 10
name Sales
exit
vlan 20
name Engineering
exit
vlan 30
name Voice
exit
```

#### Assigning Ports to VLANs

| Command | Description |
|---------|-------------|
| `interface fastethernet 0/1` | Enter interface configuration mode |
| `switchport mode access` | Set interface to access mode |
| `switchport access vlan 10` | Assign interface to VLAN 10 |

#### Voice VLAN Configuration

| Command | Description |
|---------|-------------|
| `interface fastethernet 0/1` | Enter interface configuration mode |
| `switchport mode access` | Set interface to access mode |
| `switchport access vlan 10` | Assign data VLAN |
| `switchport voice vlan 30` | Assign voice VLAN for IP phone |

### VLAN Trunking

A VLAN trunk is a point-to-point link that carries traffic for multiple VLANs between switches or between a switch and a router.

#### Trunking Protocols

| Protocol | Type | Standard | VLAN Support | Status |
|----------|------|----------|--------------|--------|
| IEEE 802.1Q | Tagging | IEEE 802.1Q | 1-4094 | Industry standard |
| ISL | Encapsulation | Cisco | 1-1005 | Deprecated |

#### Trunk Configuration

| Command | Description |
|---------|-------------|
| `switchport mode trunk` | Set interface to trunk mode |
| `switchport trunk allowed vlan 10,20,30` | Specify allowed VLANs on trunk |
| `switchport trunk allowed vlan all` | Allow all VLANs on trunk |
| `switchport trunk native vlan 999` | Set native VLAN for trunk |
| `switchport trunk allowed vlan remove 20` | Remove specific VLAN from trunk |
| `switchport trunk allowed vlan add 40` | Add specific VLAN to trunk |

#### Example Trunk Configuration

```
interface gigabitethernet 0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 999
```

### Dynamic Trunking Protocol (DTP)

DTP is a Cisco proprietary protocol that automatically negotiates trunking between switches.

#### DTP Modes

| Mode | Description | Sends DTP | Receives DTP | Result with Trunk | Result with Access |
|------|-------------|-----------|--------------|-------------------|-------------------|
| Access | Forces access mode | Access request | Access request | No trunk | Access |
| Trunk | Forces trunk mode | Trunk request | Trunk request | Trunk | May cause errors |
| Dynamic Auto | Passive (waits) | Access request | Any | Trunk if other requests | Access |
| Dynamic Desirable | Active (requests) | Trunk request | Any | Trunk | Access if no response |

#### DTP Configuration

| Command | Description |
|---------|-------------|
| `switchport mode trunk` | Forces trunk mode |
| `switchport mode dynamic auto` | Sets mode to auto (passive) |
| `switchport mode dynamic desirable` | Sets mode to desirable (active) |
| `switchport nonegotiate` | Disables DTP negotiation |

#### DTP Best Practices

| Practice | Reason |
|----------|--------|
| Use `switchport mode trunk` | Explicit configuration, no negotiation |
| Use `switchport nonegotiate` | Disables DTP when not needed for security |
| Never use dynamic modes on access ports | Security risk - could become trunk |

### VLAN Verification Commands

| Command | Description |
|---------|-------------|
| `show vlan brief` | Shows summarized VLAN information |
| `show vlan` | Shows detailed VLAN information |
| `show interfaces switchport` | Displays switchport configuration |
| `show interfaces trunk` | Shows trunk interfaces and status |
| `show mac address-table` | Displays MAC address table |

---

## Inter-VLAN Routing

### Module Overview

This module covers inter-VLAN routing, which is the process of forwarding network traffic from one VLAN to another VLAN. It explains how to troubleshoot inter-VLAN routing on Layer 3 devices.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Inter-VLAN Routing Operation | Describe options for configuring inter-VLAN routing |
| Router-on-a-Stick Inter-VLAN Routing | Configure router-on-a-stick inter-VLAN routing |
| Inter-VLAN Routing using Layer 3 Switches | Configure inter-VLAN routing using Layer 3 switching |

### Key Terms

| Term | Definition |
|------|------------|
| Inter-VLAN Routing | Process of forwarding traffic between VLANs |
| Router-on-a-Stick | Using single router interface with subinterfaces for multiple VLANs |
| encapsulation dot1q X [native] | Configures 802.1Q encapsulation on subinterface |
| no switchport | Converts Layer 2 switch port to Layer 3 |
| router ospf | OSPF routing protocol configuration mode |
| ip routing | Enables IP routing on Layer 3 switch |

### Inter-VLAN Routing Operation

VLANs are used to segment switched Layer 2 networks for a variety of reasons. Regardless of the reason, hosts in one VLAN cannot communicate with hosts in another VLAN unless there is a router or a Layer 3 switch to provide routing services.

#### Why Inter-VLAN Routing is Needed

| Reason | Description |
|--------|-------------|
| Communication | Devices in different VLANs need to communicate |
| Resource Sharing | Printers, servers, and services shared across VLANs |
| Internet Access | All VLANs need access to internet gateway |
| Central Services | Email, file servers, databases accessed by all VLANs |

#### Inter-VLAN Routing Options

| Option | Description | Advantages | Disadvantages |
|--------|-------------|------------|---------------|
| Legacy Inter-VLAN Routing | Separate physical router interface per VLAN | Simple, dedicated bandwidth | Expensive, limited scalability |
| Router-on-a-Stick | Single router interface with subinterfaces | Cost-effective, flexible | Single point of failure, shared bandwidth |
| Layer 3 Switching | SVIs on Layer 3 switch | High performance, no external router needed | More expensive hardware |

### Router-on-a-Stick Configuration

Router-on-a-stick is an acceptable solution for small to medium networks. It uses a single physical router interface with multiple logical subinterfaces, each configured for a different VLAN.

#### Configuration Steps

**Switch Configuration:**

| Command | Description |
|---------|-------------|
| `interface gigabitethernet 0/1` | Enter interface configuration mode |
| `switchport mode trunk` | Set interface to trunk mode |
| `switchport trunk allowed vlan 10,20` | Specify allowed VLANs |

**Router Configuration:**

| Command | Description |
|---------|-------------|
| `interface gigabitethernet 0/0` | Enter physical interface configuration |
| `no shutdown` | Enable the physical interface |
| `interface gigabitethernet 0/0.10` | Create subinterface for VLAN 10 |
| `encapsulation dot1q 10` | Set 802.1Q encapsulation for VLAN 10 |
| `ip address 192.168.10.1 255.255.255.0` | Assign IP address to subinterface |
| `interface gigabitethernet 0/0.20` | Create subinterface for VLAN 20 |
| `encapsulation dot1q 20` | Set 802.1Q encapsulation for VLAN 20 |
| `ip address 192.168.20.1 255.255.255.0` | Assign IP address to subinterface |

#### Native VLAN Configuration

| Command | Description |
|---------|-------------|
| `encapsulation dot1q 99 native` | Set VLAN 99 as native VLAN (untagged) |

### Inter-VLAN Routing using Layer 3 Switches

Layer 3 switches can provide inter-VLAN routing using Switched Virtual Interfaces (SVIs). This is the preferred method for larger networks due to higher performance.

#### Configuration Steps

| Step | Command | Description |
|------|---------|-------------|
| 1 | `ip routing` | Enable IP routing on the switch |
| 2 | `interface vlan 10` | Create SVI for VLAN 10 |
| 3 | `ip address 192.168.10.1 255.255.255.0` | Assign IP address to SVI |
| 4 | `no shutdown` | Enable the SVI |
| 5 | `interface vlan 20` | Create SVI for VLAN 20 |
| 6 | `ip address 192.168.20.1 255.255.255.0` | Assign IP address to SVI |
| 7 | `no shutdown` | Enable the SVI |
| 8 | `interface fastethernet 0/1` | Configure access port |
| 9 | `switchport mode access` | Set to access mode |
| 10 | `switchport access vlan 10` | Assign to VLAN 10 |

#### SVI Requirements

| Requirement | Description |
|-------------|-------------|
| VLAN Must Exist | Create VLAN before creating SVI |
| Active Ports | At least one port must be in VLAN or trunk must carry VLAN |
| No Shutdown | SVI must be enabled with `no shutdown` |
| IP Routing | Must enable `ip routing` on switch |

### Troubleshooting Inter-VLAN Routing

| Issue | Possible Cause | Solution |
|-------|----------------|----------|
| VLAN not created | SVI created before VLAN exists | Create VLAN first, then SVI |
| SVI down | No active ports in VLAN | Add access ports to VLAN or ensure trunk carries VLAN |
| Encapsulation mismatch | Wrong encapsulation type | Verify dot1q encapsulation on router subinterfaces |
| IP routing disabled | Layer 3 switch not routing | Enable `ip routing` on switch |
| No connectivity | Wrong default gateway on hosts | Verify hosts have correct default gateway (SVI IP address) |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show ip route` | Display routing table |
| `show ip interface brief` | Show interface status |
| `show vlan brief` | Show VLAN status |
| `show interfaces trunk` | Show trunk configuration |
| `show running-config interface` | Show interface configuration |
| `ping <ip-address>` | Test connectivity |
| `traceroute <ip-address>` | Test routing path |

---

## STP Concepts

### Module Overview

This module explains how Spanning Tree Protocol (STP) enables redundancy in a Layer 2 network. It covers common problems in redundant networks, STP operation, and Rapid PVST+.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Purpose of STP | Explain common problems in a redundant, L2 switched network |
| STP Operations | Explain how STP operates in a simple switched network |
| Evolution of STP | Explain how Rapid PVST+ operates |

### Key Terms

| Term | Definition |
|------|------------|
| Spanning Tree Protocol (STP) | Protocol that prevents loops in switched networks |
| Spanning Tree Algorithm (STA) | Algorithm used by STP to create loop-free topology |
| IEEE 802.1D | Original STP standard |
| IEEE 802.1w | Rapid STP standard |
| Broadcast Storm | Uncontrolled propagation of broadcast frames |
| Root Bridge | Central switch in STP topology |
| Root Port | Port with best path to root bridge |
| Designated Port | Forwarding port on each network segment |
| Alternate (Blocked) Port | Backup port that does not forward traffic |
| Learning | STP state where MAC addresses are learned |
| Listening | STP state where BPDUs are received and sent |
| Bridge ID (BID) | Priority + MAC address used in root election |
| Root ID | Bridge ID of root bridge |
| Bridge Protocol Data Unit (BPDU) | STP messages exchanged between switches |
| Bridge Priority | Configurable value (0-65535, default 32768) |
| Extended System ID | Extended Bridge ID with VLAN number |
| Short path cost | Metric based on link bandwidth |
| Rapid STP (RSTP) | Fast-converging version of STP |
| Port priority | Configurable value (0-255, default 128) |
| Hello timer | Interval between BPDU transmissions (default 2s) |
| Max Age timer | Maximum time to wait for BPDUs (default 20s) |
| Forward Delay timer | Time spent in listening/learning states (default 15s) |
| Blocking | STP state where port does not forward frames |
| Forwarding | STP state where port forwards frames |
| Discarding | RSTP state combining blocking, listening, learning |
| Per-VLAN Spanning Tree (PVST) | Cisco's per-VLAN STP |
| PVST+ | Enhanced PVST with 802.1Q support |
| Rapid PVST+ | Cisco's rapid per-VLAN STP |
| Multiple Spanning Tree Protocol (MSTP) | IEEE standard for multiple spanning trees |
| Multiple Spanning Tree (MST) | Instance of MSTP |
| PortFast | Feature that skips listening/learning states |
| BPDU Guard | Feature that disables port if BPDU received |

### Purpose of STP

Redundancy is an important part of hierarchical design for eliminating single points of failure and preventing disruption of network services. However, redundant links in Layer 2 networks can cause problems without STP.

#### Problems in Redundant Layer 2 Networks

| Problem | Description | Impact |
|---------|-------------|--------|
| Broadcast Storm | Broadcast frames loop endlessly through redundant links | Consumes all network bandwidth, crashes switches |
| MAC Address Table Instability | Switch receives same frame on multiple ports | MAC table entries constantly change, switch floods frames |
| Duplicate Frame Transmission | Same frame received multiple times | Application errors, wasted network resources |

#### Why STP is Needed

STP solves these problems by:
- Creating a loop-free logical topology
- Blocking redundant links while keeping them as backups
- Automatically reconverging when topology changes
- Maintaining network redundancy without loops

### STP Operations

STP operates by electing a root bridge and then determining which ports should forward and which should block.

#### STP Port States

| State | Description | Forward Data | Learn MAC | Duration |
|-------|-------------|--------------|-----------|----------|
| Blocking | Prevents loops, does not forward frames | No | No | Until topology changes |
| Listening | Determines root port, receives/sends BPDUs | No | No | 15 seconds |
| Learning | Builds MAC address table | No | Yes | 15 seconds |
| Forwarding | Normal operation, forwards data frames | Yes | Yes | Indefinite |
| Disabled | Administratively shut down | No | No | Until enabled |

#### STP Election Process

| Step | Description |
|------|-------------|
| 1 | Elect Root Bridge - Switch with lowest Bridge ID (Priority + MAC) becomes root |
| 2 | Elect Root Ports - Each non-root switch selects one port with lowest path cost to root |
| 3 | Elect Designated Ports - Each segment selects one port with lowest path cost to root |
| 4 | Block Non-Designated Ports - All other ports are blocked to prevent loops |

#### Bridge ID Components

| Component | Value Range | Default |
|-----------|-------------|---------|
| Priority | 0-65535 | 32768 |
| Extended System ID | VLAN number (1-4096) | Determined by VLAN |
| MAC Address | Unique per switch | Factory assigned |

#### Path Cost Values

| Bandwidth | 802.1D Cost | 802.1w Cost |
|-----------|-------------|-------------|
| 4 Mbps | 250 | 5,000,000 |
| 10 Mbps | 100 | 2,000,000 |
| 16 Mbps | 62 | 1,250,000 |
| 45 Mbps | 39 | 555,555 |
| 100 Mbps | 19 | 200,000 |
| 155 Mbps | 14 | 128,000 |
| 622 Mbps | 6 | 32,000 |
| 1 Gbps | 4 | 20,000 |
| 10 Gbps | 2 | 2,000 |

### Evolution of STP

#### STP Standards

| Standard | Description | Convergence Time | Type |
|----------|-------------|------------------|------|
| IEEE 802.1D | Original STP | 30-50 seconds | Single instance |
| IEEE 802.1w | Rapid STP (RSTP) | <10 seconds | Single instance |
| IEEE 802.1s | Multiple STP (MSTP) | <10 seconds | Multiple instances |
| Cisco PVST+ | Per-VLAN STP | 30-50 seconds | Per-VLAN |
| Cisco Rapid PVST+ | Per-VLAN RSTP | <10 seconds | Per-VLAN |

#### Rapid PVST+ Features

| Feature | Description |
|---------|-------------|
| Faster Convergence | <10 seconds vs 30-50 seconds |
| Backup Port Role | Immediate transition to forwarding |
| Edge Ports | Skip listening/learning states (PortFast) |
| Proposal/Agreement | Fast synchronization between switches |

#### Rapid PVST+ Port States

| State | Description |
|-------|-------------|
| Discarding | Combines blocking, listening, learning |
| Learning | Learning MAC addresses |
| Forwarding | Forwarding data frames |

#### Rapid PVST+ Port Roles

| Role | Description |
|------|-------------|
| Root Port | Port with best path to root bridge |
| Designated Port | Forwarding port on each segment |
| Alternate Port | Backup to root port |
| Backup Port | Backup to designated port |
| Edge Port | Connected to end device (PortFast) |

### STP Configuration

| Command | Description | Example |
|---------|-------------|---------|
| `spanning-tree mode pvst` | Enable per-VLAN STP | `spanning-tree mode pvst` |
| `spanning-tree mode rapid-pvst` | Enable Rapid PVST+ | `spanning-tree mode rapid-pvst` |
| `spanning-tree vlan <id> priority <value>` | Set priority (multiple of 4096) | `spanning-tree vlan 1 priority 24576` |
| `spanning-tree vlan <id> root primary` | Make switch primary root | `spanning-tree vlan 1 root primary` |
| `spanning-tree vlan <id> root secondary` | Make switch secondary root | `spanning-tree vlan 1 root secondary` |
| `spanning-tree portfast` | Enable PortFast on port | `interface fa0/1` → `spanning-tree portfast` |
| `spanning-tree bpduguard enable` | Enable BPDU Guard | `interface fa0/1` → `spanning-tree bpduguard enable` |
| `spanning-tree guard root` | Enable Root Guard | `interface gi0/1` → `spanning-tree guard root` |
| `spanning-tree guard loop` | Enable Loop Guard | `interface gi0/1` → `spanning-tree guard loop` |

### STP Protection Mechanisms

| Mechanism | Purpose | Command | Use On |
|-----------|---------|---------|--------|
| PortFast | Skip listening/learning for edge ports | `spanning-tree portfast` | Access ports to end devices |
| BPDU Guard | Disable port if BPDU received | `spanning-tree bpduguard enable` | Edge ports |
| BPDU Filter | Don't send/receive BPDUs | `spanning-tree bpdufilter enable` | Edge ports (use carefully) |
| Root Guard | Prevent root bridge takeover | `spanning-tree guard root` | Designated ports toward edge switches |
| Loop Guard | Prevent unidirectional links | `spanning-tree guard loop` | Root and alternate ports |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show spanning-tree` | Display STP status |
| `show spanning-tree vlan <id>` | Show STP for specific VLAN |
| `show spanning-tree detail` | Show detailed STP information |
| `show spanning-tree root` | Show root bridge information |
| `show spanning-tree interface <interface>` | Show port-specific STP information |

---

## EtherChannel

### Module Overview

This module covers EtherChannel technology, which is a link aggregation technology that groups multiple physical Ethernet links together into one single logical link.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| EtherChannel Operation | Describe EtherChannel technology |
| Configure EtherChannel | Configure EtherChannel |
| Verify and Troubleshoot EtherChannel | Troubleshoot EtherChannel |

### Key Terms

| Term | Definition |
|------|------------|
| Link Aggregation | Combining multiple physical links into one logical link |
| EtherChannel | Cisco's link aggregation technology |
| Port Channel | Logical interface representing EtherChannel |
| Port Aggregation Protocol (PAgP) | Cisco proprietary link aggregation protocol |
| Link Aggregation Control Protocol (LACP) | IEEE standard link aggregation protocol |
| PAgP desirable | Active mode that requests EtherChannel formation |
| PAgP auto | Passive mode that waits for PAgP request |
| LACP active | Active mode that requests EtherChannel formation |
| LACP passive | Passive mode that waits for LACP request |

### EtherChannel Operation

There are scenarios in which more bandwidth or redundancy between devices is needed than what can be provided by a single link. Multiple links could be connected between devices to increase bandwidth. However, Spanning Tree Protocol (STP), which is enabled on Layer 2 devices like Cisco switches by default, will block redundant links to prevent switching loops.

#### Why EtherChannel is Needed

| Problem | Solution |
|---------|----------|
| Single link bandwidth insufficient | Aggregate multiple links for more bandwidth |
| STP blocks redundant links | EtherChannel allows redundant links without STP blocking |
| Need for redundancy | EtherChannel provides link aggregation with failover |

#### EtherChannel Benefits

| Benefit | Description |
|---------|-------------|
| Increased Bandwidth | 2 Gbps = 2 × 1 Gbps links |
| Redundancy | Link failure doesn't disrupt connectivity |
| Load Balancing | Distributes traffic across all links |
| Simplified Configuration | One logical interface instead of multiple |
| Loop Prevention | STP treats as single link |

### EtherChannel Protocols

#### PAgP (Port Aggregation Protocol)

| Attribute | Details |
|-----------|---------|
| Type | Cisco proprietary |
| Modes | Desirable (active), Auto (passive) |
| Combinations | Desirable+Desirable=EtherChannel, Desirable+Auto=EtherChannel, Auto+Auto=No EtherChannel |

#### LACP (Link Aggregation Control Protocol)

| Attribute | Details |
|-----------|---------|
| Type | IEEE standard (802.3ad) |
| Modes | Active (active), Passive (passive) |
| Combinations | Active+Active=EtherChannel, Active+Passive=EtherChannel, Passive+Passive=No EtherChannel |

#### On Mode

| Attribute | Details |
|-----------|---------|
| Type | No protocol |
| Configuration | Both sides configured as `on` |
| Risk | May create loops if misconfigured |

### EtherChannel Configuration

#### Configuration Steps

| Step | Command | Description |
|------|---------|-------------|
| 1 | `interface range gi0/1 - 2` | Select multiple interfaces |
| 2 | `channel-group 1 mode active` | Assign to EtherChannel group 1 with LACP active |
| 3 | `interface port-channel 1` | Configure port-channel logical interface |
| 4 | `switchport mode trunk` | Set trunk mode |
| 5 | `switchport trunk allowed vlan 10,20` | Allow specific VLANs |

#### Example Configuration (LACP)

**Switch 1:**
```
configure terminal
interface range gigabitethernet 0/1 - 2
channel-group 1 mode active
exit
interface port-channel 1
switchport mode trunk
switchport trunk allowed vlan 10,20
```

**Switch 2:**
```
configure terminal
interface range gigabitethernet 0/1 - 2
channel-group 1 mode active
exit
interface port-channel 1
switchport mode trunk
switchport trunk allowed vlan 10,20
```

#### Configuration Guidelines and Restrictions

| Requirement | Description |
|-------------|-------------|
| Same Speed | All links must have same speed (10/100/1000 Mbps) |
| Same Duplex | All links must have same duplex (full/half) |
| Same VLAN Configuration | All ports must have same VLAN membership |
| Same Trunk Configuration | All ports must be trunk or all access |
| Same Physical Type | All links must be same type (copper/fiber) |
| Maximum Links | Usually 8 links per bundle (varies by platform) |

### Load Balancing

#### Load Balancing Methods

| Method | Description |
|--------|-------------|
| src-mac | Source MAC address |
| dst-mac | Destination MAC address |
| src-dst-mac | Source and destination MAC |
| src-ip | Source IP address |
| dst-ip | Destination IP address |
| src-dst-ip | Source and destination IP |
| src-port | Source port number |
| dst-port | Destination port number |
| src-dst-port | Source and destination port |

#### Load Balancing Configuration

| Command | Description |
|---------|-------------|
| `port-channel load-balance src-dst-ip` | Set load balancing to source and destination IP |

### Verification and Troubleshooting

#### Verification Commands

| Command | Description |
|---------|-------------|
| `show etherchannel summary` | Show EtherChannel status |
| `show etherchannel load-balance` | Show load balancing method |
| `show running-config interface port-channel 1` | Show port-channel configuration |
| `show interfaces port-channel 1` | Show port-channel status |
| `show lacp sys-id` | Show LACP system ID |
| `show lacp counters` | Show LACP statistics |
| `show pagp neighbor` | Show PAgP neighbors |

#### Common Issues and Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| Mismatched Modes | Both sides must have compatible modes | Verify both sides use same protocol or compatible modes |
| Configuration Mismatch | Speed, duplex, VLAN must match | Verify all settings match on both ends |
| Wrong Channel Group | Group numbers must match | Verify channel group numbers match |
| STP Blocking | One link blocked if spanning-tree blocks | Verify EtherChannel is properly formed |

---

## Routing Concepts

### Module Overview

This module explains how routers use information in packets to make forwarding decisions. It covers path determination, packet forwarding, router configuration review, routing table structure, and comparison of static and dynamic routing.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Path Determination | Explain how routers determine the best path |
| Packet Forwarding | Explain how routers forward packets to the destination |
| Basic Router Configuration Review | Configure basic settings on a router |
| IP Routing Table | Describe the structure of a routing table |
| Static and Dynamic Routing | Compare static and dynamic routing concepts |

### Key Terms

| Term | Definition |
|------|------------|
| best path | Optimal route to destination selected by router |
| longest match | Routing principle selecting most specific route |
| prefix length | Number of bits in network portion of IP address |
| next-hop router | Next router in path to destination |
| process switching | Software-based packet forwarding (slow) |
| fast switching | Cached forwarding (faster) |
| Cisco Express Forwarding (CEF) | Hardware-based forwarding (fastest) |
| route sources | Methods routes are learned (connected, static, dynamic) |
| static routes | Manually configured routes |
| dynamic routing protocols | Protocols that exchange routing information |
| ip route | Command to configure static route |
| Default Route | Route of last resort (0.0.0.0/0) |
| ip route 0.0.0.0 0.0.0.0 [exit-if \| next-hop-ip] | Default route configuration |
| ipv6 route ::/0 [exit-if \| next-hop-ipv6] | IPv6 default route configuration |
| Administrative Distance | Trustworthiness of route source (0-255) |
| RIPv2, OSPFv2 | Dynamic routing protocols for IPv4 |
| EIGRP, EIGRP for IPv6 | Cisco's dynamic routing protocols |
| OSPFv3, IS-IS | Dynamic routing protocols supporting IPv6 |

### Path Determination

When a router receives an IP packet on one interface, it determines which interface to use to forward the packet towards its destination. This process involves two key functions: path determination and packet switching.

#### Two Functions of a Router

| Function | Description |
|----------|-------------|
| Path Determination | Finding the best path to destination network |
| Packet Switching | Moving packets from input interface to output interface |

#### Path Determination Process

| Step | Description |
|------|-------------|
| 1 | Router receives packet on ingress interface |
| 2 | Router checks destination IP address |
| 3 | Router searches routing table for longest prefix match |
| 4 | Router selects best path based on administrative distance and metric |
| 5 | Router determines next-hop router or directly connected network |
| 6 | Router selects outgoing interface |

#### Routing Metrics

| Metric | Used By | Description |
|--------|---------|-------------|
| Hop Count | RIP | Number of routers to destination |
| Bandwidth | OSPF, EIGRP | Link capacity |
| Delay | OSPF, EIGRP | Transit time |
| Reliability | EIGRP | Link reliability |
| Load | EIGRP | Current link utilization |
| Cost | OSPF, IS-IS | Inverse of bandwidth |

### Packet Forwarding

After determining the best path, the router forwards the packet toward its destination.

#### Packet Forwarding Process

| Step | Description |
|------|-------------|
| 1 | Router receives frame on ingress interface |
| 2 | Router checks FCS and strips Layer 2 header |
| 3 | Router checks routing table for destination |
| 4 | Router determines next-hop and outgoing interface |
| 5 | Router creates new Layer 2 header for outgoing interface |
| 6 | Router forwards frame out egress interface |

#### Switching Methods

| Method | Description | Speed |
|--------|-------------|-------|
| Process Switching | Software-based forwarding, each packet processed by CPU | Slowest |
| Fast Switching | Caches forwarding information in fast-switching cache | Faster |
| CEF (Cisco Express Forwarding) | Hardware-based forwarding with FIB and adjacency table | Fastest |

### IP Routing Table

The routing table is a database of network destinations and paths to reach them.

#### Routing Table Entry Components

| Component | Description |
|-----------|-------------|
| Destination Network | IP address and subnet mask |
| Next Hop | IP address of next router (if not directly connected) |
| Outgoing Interface | Interface to send packet out |
| Administrative Distance | Trustworthiness of route source (0-255) |
| Metric | Cost of using this route |

#### Administrative Distance Values

| Route Source | Administrative Distance | Priority |
|--------------|------------------------|----------|
| Directly Connected | 0 | Highest |
| Static Route | 1 | Very High |
| EIGRP Summary | 5 | High |
| EBGP | 20 | High |
| EIGRP Internal | 90 | Medium-High |
| IGRP | 100 | Medium |
| OSPF | 110 | Medium |
| IS-IS | 115 | Medium-Low |
| RIP | 120 | Low |
| EIGRP External | 170 | Very Low |
| iBGP | 200 | Lowest |
| Unknown | 255 | Not used |

#### Routing Table Example

| Code | Network | Next Hop | Interface | AD | Metric |
|------|---------|----------|-----------|----|--------|
| C | 192.168.1.0/24 | - | Gig0/0 | 0 | 0 |
| S | 10.0.0.0/8 | 10.1.1.2 | Serial0/0/0 | 1 | 0 |
| D | 172.16.0.0/16 | 10.1.1.2 | Serial0/0/0 | 90 | 2172416 |
| O | 192.168.100.0/24 | 10.1.1.2 | Serial0/0/0 | 110 | 2 |
| S* | 0.0.0.0/0 | 203.0.113.1 | Serial0/0/1 | 1 | 0 |

### Static vs Dynamic Routing

#### Comparison

| Feature | Static Routing | Dynamic Routing |
|---------|---------------|-----------------|
| Configuration | Manual | Automatic |
| Network Overhead | None | Routing updates |
| Scalability | Poor | Good |
| CPU Usage | Low | Higher |
| Failover | Manual | Automatic |
| Best For | Small networks | Large networks |
| Examples | Default routes | OSPF, EIGRP, BGP |

#### Static Routing

| Characteristic | Description |
|----------------|-------------|
| Configuration | Manually configured by administrator |
| Protocol | No routing protocol used |
| Overhead | No network overhead for routing updates |
| Adaptability | Does not adapt to topology changes |
| Scalability | Does not scale well to large networks |
| Administrative Overhead | High in large networks |
| Security | No routing updates transmitted (more secure) |

#### Dynamic Routing

| Characteristic | Description |
|----------------|-------------|
| Configuration | Automatically learns routes via routing protocols |
| Protocol | Uses routing protocols (RIP, OSPF, EIGRP, BGP) |
| Overhead | Network bandwidth for routing updates |
| Adaptability | Automatically adapts to topology changes |
| Scalability | Scales to large, complex networks |
| Administrative Overhead | Lower in large networks |
| Security | Routing updates transmitted (potential security risk) |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show ip route` | Display routing table |
| `show ip interface brief` | Show interface status |
| `show running-config` | Show current configuration |
| `show protocols` | Show routing protocol status |
| `show ip protocols` | Show detailed routing protocol information |
| `traceroute <ip>` | Show path to destination |
| `ping <ip>` | Test connectivity |

---

## DHCPv4

### Module Overview

This module explains how DHCPv4 operates in a small- to medium-sized business network. It covers DHCPv4 concepts, configuring a Cisco IOS DHCPv4 server, and configuring a DHCPv4 client.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| DHCPv4 Concepts | Explain how DHCPv4 operates in a small- to medium-sized business network |
| Configure a Cisco IOS DHCPv4 Server | Configure a router as a DHCPv4 server |
| Configure a DHCPv4 Client | Configure a router as a DHCPv4 client |

### Key Terms

| Term | Definition |
|------|------------|
| Dynamic Host Configuration Protocol (DHCP) | Protocol for automatic IP address assignment |
| DHCP Discover (DHCPDISCOVER) | Client broadcast to find DHCP server |
| DHCP Offer (DHCPOFFER) | Server offers IP address to client |
| DHCP Request (DHCPREQUEST) | Client requests offered IP address |
| DHCP Acknowledgment (DHCPACK) | Server confirms and assigns IP address |

### DHCPv4 Concepts

Dynamic Host Configuration Protocol v4 (DHCPv4) assigns IPv4 addresses and other network configuration information dynamically. Because desktop clients typically make up the bulk of network nodes, DHCPv4 is an extremely useful and timesaving tool for network administrators.

#### DHCPv4 Server and Client

| Component | Description |
|-----------|-------------|
| DHCPv4 Server | Assigns IP addresses and configuration to clients |
| DHCPv4 Client | Device requesting IP address from server |
| DHCP Relay | Forwards DHCP requests between subnets |

#### Benefits of DHCPv4

| Benefit | Description |
|---------|-------------|
| Automated Configuration | No manual IP assignment needed |
| Centralized Management | All IP addresses managed from one location |
| Efficient Address Utilization | Addresses reused when not needed |
| Reduced Errors | Eliminates duplicate addresses and typos |
| Easy Network Changes | Update DHCP server, not all devices |

### DHCPv4 Message Types

| Message | Description | Direction |
|---------|-------------|-----------|
| DHCPDISCOVER | Client broadcasts to find DHCP server | Client → Broadcast |
| DHCPOFFER | Server offers IP address to client | Server → Client |
| DHCPREQUEST | Client requests IP address | Client → Broadcast |
| DHCPACK | Server confirms IP address assignment | Server → Client |
| DHCPNACK | Server denies client's request | Server → Client |
| DHCPDECLINE | Client declines IP address (already in use) | Client → Server |
| DHCPRELEASE | Client releases IP address back to server | Client → Server |
| DHCPINFORM | Client requests additional configuration only | Client → Server |

### DHCPv4 Operation (DORA Process)

| Step | Message | Description |
|------|---------|-------------|
| D - Discover | DHCPDISCOVER | Client broadcasts to find available DHCP server |
| O - Offer | DHCPOFFER | Server offers IP address from its pool to client |
| R - Request | DHCPREQUEST | Client requests the offered IP address |
| A - Acknowledge | DHCPACK | Server confirms IP address assignment and provides configuration |

#### DHCP Lease Renewal

| Timer | Percentage | Description |
|-------|------------|-------------|
| T1 | 50% of lease | Client attempts to renew with original server |
| T2 | 87.5% of lease | Client broadcasts to any DHCP server for renewal |

### Configure a Cisco IOS DHCPv4 Server

#### Configuration Steps

| Step | Command | Description |
|------|---------|-------------|
| 1 | `ip dhcp excluded-address 192.168.1.1 192.168.1.10` | Exclude static addresses from pool |
| 2 | `ip dhcp excluded-address 192.168.1.200 192.168.1.254` | Exclude more static addresses |
| 3 | `ip dhcp pool LAN_POOL` | Create DHCP pool named LAN_POOL |
| 4 | `network 192.168.1.0 255.255.255.0` | Define network range |
| 5 | `default-router 192.168.1.1` | Set default gateway |
| 6 | `dns-server 8.8.8.8 8.8.4.4` | Set DNS servers |
| 7 | `domain-name example.com` | Set domain name |
| 8 | `lease 7` | Set lease time to 7 days |

#### Example Configuration

```
configure terminal
ip dhcp excluded-address 192.168.1.1 192.168.1.10
ip dhcp excluded-address 192.168.1.200 192.168.1.254
ip dhcp pool LAN_POOL
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8 8.8.4.4
domain-name example.com
lease 7
```

### Configure a DHCPv4 Client

| Command | Description |
|---------|-------------|
| `interface gigabitethernet 0/0` | Enter interface configuration mode |
| `ip address dhcp` | Enable DHCP on interface |

### DHCPv4 Across Multiple LANs

For DHCP to operate across multiple networks, DHCP relay (helper addresses) must be configured on routers.

| Command | Description |
|---------|-------------|
| `interface gigabitethernet 0/1` | Enter interface configuration mode |
| `ip helper-address 192.168.1.10` | Forward DHCP broadcasts to DHCP server |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show ip dhcp binding` | Display assigned IP addresses |
| `show ip dhcp pool` | Display DHCP pool configuration |
| `show ip dhcp conflict` | Display address conflicts |
| `show ip dhcp server statistics` | Display server statistics |
| `show running-config | section dhcp` | Display DHCP configuration |
| `debug ip dhcp server packet` | Monitor DHCP packets |
| `debug ip dhcp server events` | Monitor DHCP events |

---

## WLAN Concepts and Configurations

### Module Overview

This module explains how WLANs enable network connectivity. It covers WLAN technology and standards, components of WLANs, WLAN operation, CAPWAP operation, channel management, WLAN threats, and WLAN security mechanisms.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Introduction to Wireless | Describe WLAN technology and standards |
| Components of WLANs | Describe the components of a WLAN infrastructure |
| WLAN Operation | Explain how wireless technology enables WLAN operation |
| CAPWAP Operation | Explain how a WLC uses CAPWAP to manage multiple APs |
| Channel Management | Describe channel management in a WLAN |
| WLAN Threats | Describe threats to WLANs |
| Secure WLANs | Describe WLAN security mechanisms |

### Key Terms

| Term | Definition |
|------|------------|
| WPAN | Wireless Personal Area Network |
| WLAN | Wireless Local Area Network |
| WMAN | Wireless Metropolitan Area Network |
| WWAN | Wireless Wide Area Network |
| Bluetooth | Short-range wireless technology |
| 802.11 | IEEE wireless LAN standards |
| Electromagnetic spectrum | Range of all electromagnetic frequencies |
| ITU, IEEE | Organizations defining wireless standards |
| Lightweight AP (LAP) | Access point managed by wireless LAN controller |
| Lightweight Access Point Protocol (LWAPP) | Cisco's protocol for LAP-WLC communication |
| Wireless LAN Controller (WLC) | Device managing multiple access points |
| SSID | Service Set Identifier (network name) |
| Autonomous AP | Self-contained access point |
| Controller-based AP | Access point managed by WLC |
| Omni-directional antenna | Antenna radiating in all directions |
| Directional antenna | Antenna focusing signal in specific direction |
| MIMO antenna | Multiple Input Multiple Output antenna |
| Ad hoc mode | Direct peer-to-peer wireless communication |
| Infrastructure mode | Wireless communication through access point |

### Introduction to Wireless

#### Benefits of Wireless

| Benefit | Description |
|---------|-------------|
| Mobility | Users can move freely within coverage area |
| Flexibility | Easy to add or relocate devices |
| Cost | Reduced cabling costs |
| Productivity | Users can work from anywhere |
| Guest Access | Easy to provide temporary network access |

#### Wireless Network Types

| Type | Range | Description |
|------|-------|-------------|
| WPAN | 10 meters | Personal area network (Bluetooth) |
| WLAN | 100 meters | Local area network (Wi-Fi) |
| WMAN | Kilometers | Metropolitan area network (WiMAX) |
| WWAN | Global | Wide area network (Cellular) |

### WLAN Standards

| Standard | Frequency | Max Speed | Year |
|----------|-----------|-----------|------|
| 802.11a | 5 GHz | 54 Mbps | 1999 |
| 802.11b | 2.4 GHz | 11 Mbps | 1999 |
| 802.11g | 2.4 GHz | 54 Mbps | 2003 |
| 802.11n | 2.4/5 GHz | 600 Mbps | 2009 |
| 802.11ac | 5 GHz | 3.5 Gbps | 2013 |
| 802.11ax | 2.4/5/6 GHz | 9.6 Gbps | 2019 |

### Components of WLANs

| Component | Description | Role |
|-----------|-------------|------|
| AP (Access Point) | Connects wireless clients to wired network | Transmits/receives radio signals |
| WLC (WLAN Controller) | Manages multiple APs | Centralized management and configuration |
| Client Devices | Laptops, smartphones, tablets | End user devices |
| Wireless Switch | PoE switch for APs | Powers and connects APs |

#### AP Types

| Type | Description | Management |
|------|-------------|------------|
| Autonomous AP | Self-contained, standalone configuration | Individual configuration |
| Controller-based AP (LAP) | Managed by WLC | Centralized configuration |

### WLAN Operation

#### WLAN Modes

| Mode | Description | AP Required |
|------|-------------|-------------|
| Ad-Hoc (IBSS) | Direct client-to-client communication | No |
| Infrastructure | Clients communicate through AP | Yes |

### CAPWAP Operation

CAPWAP (Control And Provisioning of Wireless Access Points) is a protocol used between lightweight APs and WLC.

| Step | Description |
|------|-------------|
| Discovery | AP discovers WLC |
| Join | AP establishes secure tunnel with WLC |
| Configuration | WLC pushes configuration to AP |
| Run | AP operates under WLC control |
| Heartbeat | AP sends keepalive to WLC |

#### CAPWAP Tunnel Types

| Tunnel Type | Description | Encryption |
|-------------|-------------|------------|
| Control Tunnel | Management traffic | Encrypted |
| Data Tunnel | Client traffic | Can be encrypted |

### Channel Management

| Frequency Band | Non-Overlapping Channels | Channel Width |
|----------------|------------------------|---------------|
| 2.4 GHz | 1, 6, 11 | 20 MHz, 40 MHz |
| 5 GHz | 23+ channels | 20, 40, 80, 160 MHz |

#### Channel Assignment Best Practices

| Practice | Description |
|----------|-------------|
| Use Non-Overlapping Channels | Prevents interference between adjacent APs |
| Separate Adjacent AP Channels | Reduces co-channel interference |
| Automatic Channel Selection | Allows WLC to optimize channel usage |
| DFS Channels | Requires radar detection in some regions |

### WLAN Threats

| Threat | Description | Impact |
|--------|-------------|--------|
| Rogue APs | Unauthorized APs on network | Security breach, data interception |
| Ad-Hoc Connections | Direct client-to-client | Bypasses security controls |
| War Driving | Scanning for open networks | Network mapping, potential attacks |
| Eavesdropping | Intercepting wireless traffic | Data theft |
| Jamming | Interfering with wireless signals | Denial of service |
| Man-in-the-Middle | Intercepting/modifying traffic | Data manipulation |
| Deauthentication Attacks | Forcing client disconnection | Disruption of service |

### Secure WLANs

#### Authentication Methods

| Method | Description | Use Case |
|--------|-------------|----------|
| Open Authentication | No authentication | Public networks (insecure) |
| Pre-Shared Key (PSK) | Shared password | Home/small office |
| 802.1X | Enterprise with RADIUS | Corporate networks |
| Captive Portal | Web-based authentication | Guest networks |

#### Encryption Standards

| Encryption | Security Status | Recommendation |
|-----------|----------------|----------------|
| WEP | Broken | Do not use |
| WPA | Weak | Upgrade to WPA2+ |
| WPA2 | Good | Recommended |
| WPA3 | Best | Latest standard |

#### Security Features

| Feature | Description |
|---------|-------------|
| WPA2 Enterprise | 802.1X with RADIUS authentication |
| WPA3 | SAE handshake, forward secrecy |
| WIDS/WIPS | Wireless intrusion detection/prevention |
| Management Frame Protection | Protects management frames |
| PMF (802.11w) | Protects against deauth attacks |

---

## LAN Security Concepts

### Module Overview

This module explains how to use endpoint security to mitigate attacks. It covers endpoint security, access control (AAA and 802.1x), Layer 2 security threats, MAC address table attacks, and other LAN attacks.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Endpoint Security | Explain how to use endpoint security to mitigate attacks |
| Access Control | Explain how AAA and 802.1x are used to authenticate LAN endpoints and devices |
| Layer 2 Security Threats | Identify Layer 2 vulnerabilities |
| MAC Address Table Attack | Explain how a MAC address table attack compromises LAN security |
| LAN Attacks | Explain how LAN attacks compromise LAN security |

### Key Terms

| Term | Definition |
|------|------------|
| Data Breach | Unauthorized access to sensitive data |
| Malware | Malicious software (viruses, worms, Trojans) |
| Next-Generation Firewall (NGFW) | Advanced firewall with application awareness |
| Next-Generation IPS (NGIPS) | Advanced intrusion prevention system |
| Advanced Malware Protection (AMP) | Protection against sophisticated malware |
| Authentication, Authorization, Accounting (AAA) | Framework for network access control |
| Identity Services Engine (ISE) | Cisco's network access control solution |
| Host-Based Intrusion Prevention System (HIPS) | Host-level intrusion prevention |
| Email Security Appliance (ESA) | Email filtering and protection |
| Web Security Appliance (WSA) | Web filtering and protection |
| Authenticator | Network device requiring authentication |
| Port Security | Limits MAC addresses per port |
| DHCP Snooping | Filters DHCP messages |
| Dynamic ARP Inspection (DAI) | Prevents ARP spoofing |
| IP Source Guard (IPSG) | Prevents IP spoofing |
| VLAN Hopping | Accessing unauthorized VLANs |
| VLAN Double-Tagging | Exploiting trunk ports to access VLANs |
| DHCP Starvation | Requesting all DHCP addresses |
| DHCP Spoofing | Unauthorized DHCP server |
| Gratuitous ARP | ARP message announcing IP address |
| ARP Spoofing | Fake ARP messages |
| ARP Poisoning | Corrupting ARP cache |
| Cisco Discovery Protocol (CDP) | Cisco proprietary discovery protocol |

### Endpoint Security

#### What is Endpoint Security?

Protection of devices connected to the network including laptops, desktops, servers, mobile devices, IoT devices, and network printers.

#### Endpoint Security Measures

| Measure | Description |
|---------|-------------|
| Antivirus/Antimalware | Detects and removes malicious software |
| Host-based Firewall | Controls inbound/outbound traffic |
| Patch Management | Keeps OS and applications updated |
| Device Encryption | Protects data at rest |
| Application Whitelisting | Only allows approved applications |
| Endpoint Detection and Response (EDR) | Advanced threat detection and response |

### Access Control (AAA)

#### AAA Components

| Component | Description | Example |
|-----------|-------------|---------|
| Authentication | Verify identity | Username/password, certificates, tokens |
| Authorization | Determine permissions | Admin vs User access rights |
| Accounting | Track activities | Logging access times and commands |

#### AAA Configuration

| Command | Description |
|---------|-------------|
| `aaa new-model` | Enable AAA |
| `radius-server host 192.168.1.10 key secretkey` | Configure RADIUS server |
| `aaa authentication login default group radius local` | Set authentication method |
| `aaa authorization exec default group radius local` | Set authorization method |
| `aaa accounting exec default start-stop group radius` | Enable accounting |

#### 802.1X Port-Based Authentication

| Component | Description | Example |
|-----------|-------------|---------|
| Supplicant | Device seeking access | Laptop, phone |
| Authenticator | Network device requiring authentication | Switch, AP |
| Authentication Server | Validates credentials | RADIUS server |

#### 802.1X Configuration

| Command | Description |
|---------|-------------|
| `aaa new-model` | Enable AAA |
| `radius-server host 192.168.1.10 key secretkey` | Configure RADIUS server |
| `dot1x system-auth-control` | Enable 802.1X globally |
| `interface fastethernet 0/1` | Enter interface mode |
| `switchport mode access` | Set access mode |
| `authentication port-control auto` | Enable 802.1X |
| `dot1x pae authenticator` | Set as authenticator |
| `dot1x timeout reauth-period 3600` | Set reauth timeout |

### Layer 2 Security Threats

| Attack | Description | Impact |
|--------|-------------|--------|
| MAC Flooding | Overwhelms switch MAC table | Switch floods all frames |
| MAC Spoofing | Fakes MAC address | Impersonates legitimate device |
| Rogue DHCP | Unauthorized DHCP server | Incorrect network configuration |
| ARP Spoofing | Fake ARP messages | Man-in-the-middle attack |
| VLAN Hopping | Accesses unauthorized VLANs | Bypasses VLAN security |
| STP Attack | Disrupts STP operation | Network disruption |

#### MAC Address Table Attack

**MAC Flooding:**
- Attacker floods switch with fake MAC addresses
- Switch MAC table fills up
- Switch enters fail-open mode, floods all frames
- Attacker can capture all traffic

**MAC Spoofing:**
- Attacker changes device MAC address
- Impersonates legitimate device
- Bypasses MAC-based security

#### Prevention Methods

| Threat | Mitigation | Command |
|--------|------------|---------|
| MAC Flooding | Port Security | `switchport port-security` |
| MAC Spoofing | Port Security Sticky | `switchport port-security mac-address sticky` |
| Rogue DHCP | DHCP Snooping | `ip dhcp snooping` |
| ARP Spoofing | DAI | `ip arp inspection` |
| VLAN Hopping | Disable unused trunks | `switchport nonegotiate` |
| STP Attack | BPDU Guard | `spanning-tree bpduguard enable` |

### Security Configuration Examples

#### Port Security

| Command | Description |
|---------|-------------|
| `switchport port-security` | Enable port security |
| `switchport port-security maximum 3` | Set max MAC addresses |
| `switchport port-security violation shutdown` | Set violation action |
| `switchport port-security mac-address sticky` | Enable sticky learning |

#### DHCP Snooping

| Command | Description |
|---------|-------------|
| `ip dhcp snooping` | Enable DHCP snooping |
| `ip dhcp snooping vlan 10,20` | Enable on VLANs |
| `ip dhcp snooping trust` | Mark port as trusted |

#### Dynamic ARP Inspection

| Command | Description |
|---------|-------------|
| `ip arp inspection vlan 10,20` | Enable DAI on VLANs |
| `ip arp inspection trust` | Mark port as trusted |

#### IP Source Guard

| Command | Description |
|---------|-------------|
| `ip verify source vlan dhcp-snooping` | Enable IPSG with DHCP snooping |
| `interface fastethernet 0/1` | Enter interface mode |
| `ip verify source` | Enable IPSG on interface |

---

## FHRP

### Module Overview

This module explains how First Hop Redundancy Protocols (FHRPs) provide default gateway services in a redundant network. It covers the purpose and operation of FHRPs and HSRP.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| First Hop Redundancy Protocols | Explain the purpose and operation of first hop redundancy protocols |
| HSRP | Explain how HSRP operates |

### Key Terms

| Term | Definition |
|------|------------|
| First Hop Redundancy Protocol (FHRP) | Protocols providing redundant default gateways |
| Router Redundancy | Multiple routers providing same gateway service |
| Virtual Router | Logical router represented by multiple physical routers |
| Active Router | Router currently forwarding traffic |
| Standby Router | Backup router ready to take over |
| Hot Standby Routing Protocol (HSRP) | Cisco's FHRP |
| Virtual Router Redundancy Protocol (VRRP) | IEEE standard FHRP |
| Gateway Load Balancing Protocol (GLBP) | Cisco's FHRP with load balancing |
| ICMP Router Discovery Protocol (IRDP) | Legacy router discovery protocol |
| Virtual Router Master | Active router in VRRP |
| standby priority | Priority value for HSRP election |
| standby preempt | Allows higher priority router to take over |

### First Hop Redundancy Protocols

#### Default Gateway Limitations

| Issue | Description |
|-------|-------------|
| Single Point of Failure | If default gateway fails, LAN hosts lose connectivity |
| No Redundancy | Even if redundant router exists, hosts can't use it |

#### FHRP Purpose

FHRPs provide alternate default gateways in switched networks where two or more routers are connected to the same LAN.

#### FHRP Operation

| Step | Description |
|------|-------------|
| 1 | Multiple routers share virtual IP and MAC address |
| 2 | Hosts use virtual IP as default gateway |
| 3 | One router active, others standby |
| 4 | Active router failure → standby takes over |
| 5 | Hosts unaware of failover |

### FHRP Protocols Comparison

| Feature | HSRP | VRRP | GLBP |
|---------|------|------|------|
| Standard | Cisco proprietary | IEEE 802.3ad | Cisco proprietary |
| Load Balancing | No | No | Yes |
| Virtual MAC | One | One | Multiple |
| IPv6 Support | v2 only | Yes | Yes |
| Preemption | Optional | Optional | Default |
| Tracking | Yes | Yes | Yes |

### HSRP (Hot Standby Routing Protocol)

#### HSRP Overview

| Attribute | Details |
|-----------|---------|
| Standard | Cisco proprietary |
| Default Gateway Redundancy | Yes |
| Virtual MAC | 0000.0c07.acXX (XX = HSRP group) |
| IPv6 Support | Version 2 only |
| Versions | HSRPv1, HSRPv2 |

#### HSRP States

| State | Description |
|-------|-------------|
| Initial | Router starting, not configured |
| Learn | Waiting for hello messages |
| Listen | Knows virtual IP, not active or standby |
| Speak | Sending hello messages, election in progress |
| Standby | Next router to become active |
| Active | Currently forwarding traffic |

#### HSRP Configuration

| Command | Description |
|---------|-------------|
| `standby 1 ip 192.168.1.1` | Set virtual IP address |
| `standby 1 priority 110` | Set priority (default 100, higher is better) |
| `standby 1 preempt` | Enable preemption (take over if higher priority) |
| `standby 1 track serial 0/0/0 20` | Track interface, lower priority if link fails |
| `standby 1 authentication md5 key-string cisco` | Set MD5 authentication |
| `standby 1 timers 1 3` | Set hello (1s) and hold (3s) timers |
| `standby version 2` | Enable HSRP version 2 |

#### HSRP Verification

| Command | Description |
|---------|-------------|
| `show standby` | Display HSRP status and configuration |
| `show standby brief` | Show summarized HSRP information |
| `show standby name GROUP1` | Show specific group |

---

## IP Static Routing

### Module Overview

This module covers configuring IPv4 and IPv6 static routes. It includes static routes, default static routes, floating static routes, and static host routes.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| Static Routes | Describe the command syntax for static routes |
| Configure IP Static Routes | Configure IPv4 and IPv6 static routes |
| Configure IP Default Static Routes | Configure IPv4 and IPv6 default static routes |
| Configure Floating Static Routes | Configure a floating static route to provide a backup connection |
| Configure Static Host Routes | Configure IPv4 and IPv6 static host routes that direct traffic to a specific host |

### Key Terms

| Term | Definition |
|------|------------|
| static route | Manually configured route |
| default static route | Route of last resort (0.0.0.0/0) |
| floating static route | Backup route with higher administrative distance |
| summary static route | Route representing multiple networks |
| next-hop route | Route specifying next-hop router IP |
| directly connected static route | Route specifying outgoing interface |
| Fully specified static route | Route specifying both next-hop and interface |
| ip route | Command to configure IPv4 static route |
| ipv6 route | Command to configure IPv6 static route |
| show ip route static | Show IPv4 static routes |
| show ipv6 route static | Show IPv6 static routes |
| quad-zero route | Another name for default route (0.0.0.0) |

### Static Route Types

| Type | Description | Example |
|------|-------------|---------|
| Standard Static | Manual route to network | `ip route 192.168.2.0 255.255.255.0 10.1.1.2` |
| Default Route | Route of last resort | `ip route 0.0.0.0 0.0.0.0 203.0.113.1` |
| Floating Static | Backup route (higher AD) | `ip route 192.168.2.0 255.255.255.0 10.2.1.2 5` |
| Summary Static | Represents multiple networks | `ip route 192.168.0.0 255.255.252.0 10.1.1.2` |
| Host Route | Route to single host | `ip route 192.168.1.100 255.255.255.255 10.1.1.2` |

### IPv4 Static Routes

| Command Syntax | Description |
|----------------|-------------|
| `ip route <network> <mask> <next-hop-ip>` | Basic static route |
| `ip route <network> <mask> <interface>` | Static route with outgoing interface |
| `ip route 0.0.0.0 0.0.0.0 <next-hop-ip>` | Default route |
| `ip route <network> <mask> <next-hop-ip> <distance>` | Floating static route |
| `ip route <network> <mask> <interface> <next-hop-ip> <distance>` | Fully specified static route |

### IPv6 Static Routes

| Command Syntax | Description |
|----------------|-------------|
| `ipv6 route <network/prefix> <next-hop>` | Basic static route |
| `ipv6 route <network/prefix> <interface>` | Static route with outgoing interface |
| `ipv6 route ::/0 <next-hop>` | Default route |
| `ipv6 route <host-ip>/128 <next-hop>` | Host route |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show ip route` | Show IPv4 routing table |
| `show ip route static` | Show static routes only |
| `show running-config | include ip route` | Show configured routes |
| `show ipv6 route` | Show IPv6 routing table |
| `show ipv6 route static` | Show IPv6 static routes |
| `show running-config | include ipv6 route` | Show configured IPv6 routes |

---

## SLAAC and DHCPv6

### Module Overview

This module explains the operation of SLAAC and DHCPv6. It covers IPv6 Global Unicast address assignment, SLAAC operation, DHCPv6 operation, and configuring DHCPv6 servers.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| IPv6 Global Unicast Address Assignment | Explain how an IPv6 host can acquire its IPv6 configuration |
| SLAAC | Explain the operation of SLAAC |
| DHCPv6 | Explain the operation of DHCPv6 |
| Configure DHCPv6 Server | Configure a stateful and stateless DHCPv6 server |
| First Hop Redundancy Protocols | Explain the purpose and operation of FHRPs |
| FHRP Gateway Services | Explain how FHRPs provide default gateway services |

### Key Terms

| Term | Definition |
|------|------------|
| Stateless Address Autoconfiguration (SLAAC) | Automatic IPv6 address configuration without server |
| Global Unicast Address (GUA) | Routable IPv6 address |
| Link Local Address (LLA) | IPv6 address for local link communication |
| Zone ID vs. Scope ID | Identifies link-local address interface |
| Address Autoconfiguration Flag | Flag in Router Advertisement |
| Other Configuration Flag | Flag indicating DHCPv6 for other config |
| Managed Address Configuration Flag | Flag indicating stateful DHCPv6 |
| Router Solicitation (RS) | Host requests router advertisement |
| Router Advertisement (RA) | Router announces prefix and configuration |
| ipv6 unicast-routing | Enable IPv6 routing |
| EUI-64 | IPv6 interface ID based on MAC address |
| Duplicate Address Detection (DAD) | Process to verify address uniqueness |
| Neighbor Solicitation (NS) | Message for address resolution |
| Neighbor Advertisement (NA) | Message with address resolution info |
| DHCPv6 SOLICIT | Client requests address |
| DHCPv6 ADVERTISE | Server offers address |
| DHCPv6 REPLY | Server confirms address |
| Stateless DHCPv6 Client | Gets IPv6 address from SLAAC, other config from DHCPv6 |
| Stateful DHCPv6 Client | Gets IPv6 address and config from DHCPv6 |

### IPv6 Address Assignment Methods

| Method | IPv6 Address | Other Config | Server Required |
|--------|-------------|--------------|-----------------|
| SLAAC | Generated (Prefix + EUI-64 or Random) | Router Advertisements | No |
| Stateless DHCPv6 | Generated (SLAAC) | DHCPv6 (DNS, domain name) | Yes |
| Stateful DHCPv6 | Assigned (DHCPv6) | DHCPv6 | Yes |

### Router Advertisement Flags

| M Flag | O Flag | Result |
|--------|--------|--------|
| 0 | 0 | SLAAC only |
| 0 | 1 | SLAAC + Stateless DHCPv6 |
| 1 | 0 | Stateful DHCPv6 only |
| 1 | 1 | Stateful DHCPv6 (both address and config) |

### SLAAC Configuration

| Command | Description |
|---------|-------------|
| `ipv6 unicast-routing` | Enable IPv6 routing |
| `ipv6 address 2001:db8:1::1/64` | Configure IPv6 address |
| `ipv6 nd prefix 2001:db8:1::/64` | Advertise prefix in RA |
| `ipv6 nd ra lifetime 1800` | Set RA lifetime |

### Stateless DHCPv6 Configuration

| Command | Description |
|---------|-------------|
| `ipv6 dhcp pool STATELESS` | Create DHCPv6 pool |
| `dns-server 2001:4860:4860::8888` | Set DNS server |
| `domain-name example.com` | Set domain name |
| `ipv6 nd other-config-flag` | Indicate DHCPv6 available for other config |

### Stateful DHCPv6 Configuration

| Command | Description |
|---------|-------------|
| `ipv6 dhcp pool STATEFUL` | Create DHCPv6 pool |
| `address prefix 2001:db8:1::/64 lifetime 300 600` | Assign address prefix |
| `dns-server 2001:4860:4860::8888` | Set DNS server |
| `ipv6 nd managed-config-flag` | Use stateful DHCPv6 |

### Verification Commands

| Command | Description |
|---------|-------------|
| `show ipv6 interface brief` | Show IPv6 interface status |
| `show ipv6 interface` | Show detailed IPv6 interface info |
| `show ipv6 route` | Show IPv6 routing table |
| `show ipv6 routers` | Show router information |
| `show ipv6 dhcp binding` | Show DHCPv6 bindings |
| `show ipv6 dhcp pool` | Show DHCPv6 pools |

---

## Basic IP Addressing (FLSM vs VLSM)

### Module Overview

This module distinguishes between Fixed Length Subnet Mask (FLSM) and Variable Length Subnet Mask (VLSM). It explains the steps involved in VLSM and includes case studies.

### Learning Objectives

| Topic | Objective |
|-------|-----------|
| FLSM vs VLSM | Distinguish between FLSM and VLSM |
| Steps in VLSM | Explain the steps involved in VLSM |
| Case Study 1 - VLSM | Case Study on VLSM |
| Case Study 2 - VLSM | Configure a stateful and stateless DHCPv6 server |
| Case Study 3 - VLSM | Explain the purpose and operation of FHRPs |

### FLSM vs VLSM

| Feature | FLSM (Fixed Length Subnet Mask) | VLSM (Variable Length Subnet Mask) |
|---------|--------------------------------|-----------------------------------|
| Subnet Masks | Same for all subnets | Different for each subnet |
| Subnet Size | Same for all subnets | Based on requirements |
| Address Efficiency | May waste addresses | Efficient utilization |
| Configuration | Simple | More complex |
| Scalability | Limited | Better |
| Best For | Small, uniform networks | Large, varied networks |

### Steps in VLSM

| Step | Action | Description |
|------|--------|-------------|
| 1 | Sort Requirements | List requirements of IPs in descending order (Highest to Lowest) |
| 2 | Allocate Highest Range | Allocate the highest range of IPs to the highest requirement |
| 3 | Allocate Next Highest | Allocate the next highest range to next requirement |
| 4 | Continue | Continue allocating to remaining requirements |
| 5 | Router Links | Take note of router-to-router networks (usually /30) |

### Host Bits Reference

| Hosts Required | Host Bits Needed | Usable Hosts | Subnet Mask |
|----------------|------------------|--------------|-------------|
| 2 | 2 | 2 | /30 (255.255.255.252) |
| 6 | 3 | 6 | /29 (255.255.255.248) |
| 14 | 4 | 14 | /28 (255.255.255.240) |
| 30 | 5 | 30 | /27 (255.255.255.224) |
| 62 | 6 | 62 | /26 (255.255.255.192) |
| 126 | 7 | 126 | /25 (255.255.255.128) |
| 254 | 8 | 254 | /24 (255.255.255.0) |

### Case Study Example

**Network:** 192.168.1.0/24
**Requirements:**
- Sales: 50 hosts
- Engineering: 20 hosts
- Management: 10 hosts
- Router links: 2 hosts each

**VLSM Allocation:**

| Subnet | Hosts Required | Hosts Needed | Subnet Mask | Network Address | Host Range | Broadcast |
|--------|----------------|--------------|-------------|-----------------|------------|-----------|
| Sales | 50 | 6 (62 hosts) | /26 | 192.168.1.0/26 | 192.168.1.1-62 | 192.168.1.63 |
| Engineering | 20 | 5 (30 hosts) | /27 | 192.168.1.64/27 | 192.168.1.65-94 | 192.168.1.95 |
| Management | 10 | 4 (14 hosts) | /28 | 192.168.1.96/28 | 192.168.1.97-110 | 192.168.1.111 |
| Router Link 1 | 2 | 2 (2 hosts) | /30 | 192.168.1.112/30 | 192.168.1.113-114 | 192.168.1.115 |
| Router Link 2 | 2 | 2 (2 hosts) | /30 | 192.168.1.116/30 | 192.168.1.117-118 | 192.168.1.119 |

---

## Summary

This comprehensive document covers all 13 lectures of the CT133-3-2 Switching and Routing Essential course, mapped to CCNA2 – Switching, Routing and Wireless Essentials (SRWE). Each topic includes:

- Detailed explanations with paragraph descriptions
- Tabular summaries of key concepts
- Configuration commands and examples
- Comparison tables for technologies and protocols
- Verification commands for troubleshooting

The course provides students with the knowledge and skills to:
- Configure and troubleshoot routers and switches
- Implement VLANs, trunking, and inter-VLAN routing
- Configure STP, EtherChannel, and routing protocols
- Implement DHCPv4 and DHCPv6
- Deploy wireless networks with proper security
- Implement LAN security measures
- Configure FHRP for gateway redundancy
- Implement static routing
- Apply VLSM for efficient IP addressing

---

*This document serves as a comprehensive study guide combining detailed explanations with tabular formats for easy reference and quick review.*
