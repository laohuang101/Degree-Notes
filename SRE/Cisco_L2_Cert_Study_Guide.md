# Cisco Level 2 Certification Study Guide
## SRWE (Switching, Routing, and Wireless Essentials) - Exam Preparation

**Exam Date Reference:** SRWE Final Skill Exam due March 31, 2026

---

## Table of Contents
1. [EtherChannel Protocols - Detailed Comparison](#1-etherchannel-protocols---detailed-comparison)
2. [STP Comparison Table](#2-stp-comparison-table)
3. [EtherChannel Comparison Table](#3-etherchannel-comparison-table)
4. [Routing Concepts - OSPF & AD Comparison](#4-routing-concepts---ospf--ad-comparison)
5. [DHCPv4 Comparison Table](#5-dhcpv4-comparison-table)
6. [WLAN Concepts & Configuration Comparison](#6-wlan-concepts--configuration-comparison)
7. [LAN Security Comparison Table](#7-lan-security-comparison-table)
8. [FHRP Comparison Table](#8-fhrp-comparison-table)
9. [IP Addressing Comparison](#9-ip-addressing-comparison)
10. [Layer 2 Attacks & Mitigation - Command Reference](#10-layer-2-attacks--mitigation---command-reference)

---

## 1. EtherChannel Protocols - Detailed Comparison

### PAgP vs LACP vs On Mode - Mode Combinations

| Mode 1 | Mode 2 | Result | Protocol | Notes |
|--------|--------|--------|----------|-------|
| **PAgP Desirable** | PAgP Desirable | ✅ **EtherChannel Formed** | PAgP | Both actively request |
| **PAgP Desirable** | PAgP Auto | ✅ **EtherChannel Formed** | PAgP | Desirable requests, Auto accepts |
| **PAgP Auto** | PAgP Auto | ❌ **No EtherChannel** | PAgP | Both passive, no request |
| **LACP Active** | LACP Active | ✅ **EtherChannel Formed** | LACP | Both actively request |
| **LACP Active** | LACP Passive | ✅ **EtherChannel Formed** | LACP | Active requests, Passive accepts |
| **LACP Passive** | LACP Passive | ❌ **No EtherChannel** | LACP | Both passive, no request |
| **On** | On | ✅ **EtherChannel Formed** | None | Force bundling, no protocol |
| **On** | Any Other Mode | ⚠️ **Potential Mismatch/Error** | Mixed | Not recommended - can cause loops |

### PAgP vs LACP vs On - Key Differences

| Feature | PAgP (Cisco Proprietary) | LACP (IEEE 802.3ad) | On Mode |
|---------|-------------------------|---------------------|---------|
| **Standard** | Cisco only | Industry standard | No protocol |
| **Active Mode** | Desirable | Active | N/A |
| **Passive Mode** | Auto | Passive | N/A |
| **Load Balancing** | Same as LACP | Same as PAgP | Same |
| **Cross-Vendor Support** | ❌ No (Cisco only) | ✅ Yes (multi-vendor) | ✅ Yes |
| **Negotiation** | Yes (via PAgP) | Yes (via LACP) | No (forced) |
| **Risk of Loops** | Low (negotiation) | Low (negotiation) **HIGH** (if misconfigured) |
| **Exam Preference** | Mention but note it's proprietary | **Preferred** (industry standard) | Use with caution |
| **Multicast Address** | 01-00-0C-CC-CC-CC | 01-80-C2-00-00-02 | N/A |

### Example Scenarios

**Scenario 1: Two Cisco Switches**
```
Switch1(config)# interface range gi0/1-2
Switch1(config-if-range)# channel-group 1 mode desirable  (PAgP)

Switch2(config)# interface range gi0/1-2
Switch2(config-if-range)# channel-group 1 mode auto       (PAgP)
```
**Result:** ✅ EtherChannel formed (Desirable + Auto = Yes)

**Scenario 2: Cisco Switch + Non-Cisco Switch**
```
Switch1(config)# interface range gi0/1-2
Switch1(config-if-range)# channel-group 1 mode active     (LACP)

Switch2(config)# interface range gi0/1-2
Switch2(config-if-range)# channel-group 1 mode passive   (LACP)
```
**Result:** ✅ EtherChannel formed (Active + Passive = Yes)

**Scenario 3: Forcing EtherChannel (Not Recommended for Exam)**
```
Switch1(config)# interface range gi0/1-2
Switch1(config-if-range)# channel-group 1 mode on         (Forced)

Switch2(config)# interface range gi0/1-2
Switch2(config-if-range)# channel-group 1 mode on         (Forced)
```
**Result:** ⚠️ Works but HIGH RISK - can cause loops if misconfigured

### Exam Tips for EtherChannel

| Tip | Explanation |
|-----|-------------|
| **Use LACP** when possible | Industry standard, multi-vendor support |
| **Avoid On Mode** in exam unless explicitly told | No negotiation, loop risk |
| **Match both ends** | Both must use same protocol or compatible modes |
| **Verify configuration** | Use `show etherchannel summary` |
| **Check all requirements** | Speed, duplex, VLAN must match |

---

## 2. STP Comparison Table

### STP Standards Comparison

| Standard | Full Name | Convergence Time | Port States | VLAN Support | Status |
|----------|-----------|------------------|-------------|--------------|--------|
| **802.1D** | Classic STP | 30-50 seconds | 5 states (Blocking, Listening, Learning, Forwarding, Disabled) | Single instance | Legacy |
| **802.1w** | Rapid STP (RSTP) | <10 seconds | 3 states (Discarding, Learning, Forwarding) | Single instance | Preferred |
| **802.1s** | Multiple STP (MSTP) | <10 seconds | 3 states | Multiple instances | Enterprise |
| **PVST+** | Per-VLAN STP | 30-50 seconds | 5 states | Per-VLAN | Cisco legacy |
| **Rapid PVST+** | Rapid Per-VLAN STP | <10 seconds | 3 states | Per-VLAN | **Cisco recommended** |

### STP Port States - 802.1D vs RSTP

| 802.1D State | RSTP Equivalent | Forwards Data | Learns MACs | Timer Duration | Transition Trigger |
|--------------|-----------------|---------------|-------------|----------------|-------------------|
| Blocking | Discarding | ❌ No | ❌ No | Until topology change | No BPDUs received |
| Listening | Discarding | ❌ No | ❌ No | 15 seconds | Becoming root port/designated |
| Learning | Learning | ❌ No | ✅ Yes | 15 seconds | After listening (802.1D only) |
| Forwarding | Forwarding | ✅ Yes | ✅ Yes | Indefinite | Root or designated port |
| Disabled | Discarding | ❌ No | ❌ No | Until enabled | Administrative |

### STP Port Roles

| Role | Description | One Per Switch? | Can Forward? |
|------|-------------|-----------------|--------------|
| **Root Port** | Best path to root bridge | Yes (per non-root switch) | ✅ Yes |
| **Designated Port** | Forwarding port on each segment | Yes (per segment) | ✅ Yes |
| **Alternate Port** | Backup to root port | Multiple possible | ❌ No |
| **Backup Port** | Backup to designated port | Multiple possible | ❌ No |
| **Edge Port** | PortFast enabled, connects to end devices | Multiple | ✅ Yes (immediate) |

### STP Protection Mechanisms Comparison

| Mechanism | Command | Purpose | Where to Apply | Exam Importance |
|-----------|---------|---------|----------------|-----------------|
| **PortFast** | `spanning-tree portfast` | Skip listening/learning | Access ports to end devices | ⭐⭐⭐ |
| **BPDU Guard** | `spanning-tree bpduguard enable` | Disable port if BPDU received | Edge ports (PortFast) | ⭐⭐⭐⭐⭐ |
| **BPDU Filter** | `spanning-tree bpdufilter enable` | Don't send/receive BPDUs | Edge ports (use carefully) | ⭐⭐ |
| **Root Guard** | `spanning-tree guard root` | Prevent root bridge takeover | Designated ports toward edge | ⭐⭐⭐⭐ |
| **Loop Guard** | `spanning-tree guard loop` | Prevent unidirectional links | Root and alternate ports | ⭐⭐⭐ |

### Bridge ID Components (For Root Election)

| Component | Value Range | Default | Weight in Election |
|-----------|-------------|---------|-------------------|
| **Priority** | 0-65535 (multiples of 4096) | 32768 | ⭐⭐⭐ Most Important |
| **Extended System ID** | VLAN number (1-4096) | Auto | Included in priority |
| **MAC Address** | Factory assigned | Unique | ⭐ Tie-breaker only |

### STP Cost Values (802.1w - Current Standard)

| Bandwidth | Path Cost | Notes |
|-----------|-----------|-------|
| 4 Mbps | 5,000,000 | Very slow |
| 10 Mbps | 2,000,000 | Legacy Ethernet |
| 100 Mbps | 200,000 | Fast Ethernet |
| 1 Gbps | 20,000 | Gigabit Ethernet |
| 10 Gbps | 2,000 | 10 Gigabit Ethernet |

---

## 3. EtherChannel Comparison Table

### EtherChannel Protocols - Quick Reference

| Protocol | Mode - Active | Mode - Passive | Standard | Multicast Address | Load Balancing |
|----------|---------------|----------------|----------|-------------------|----------------|
| **PAgP** | Desirable | Auto | Cisco Proprietary | 01-00-0C-CC-CC-CC | src-dst-ip (default) |
| **LACP** | Active | Passive | IEEE 802.3ad | 01-80-C2-00-00-02 | src-dst-ip (default) |
| **On** | On | On | No Protocol | N/A | src-dst-ip (default) |

### EtherChannel Load Balancing Methods

| Method | Based On | Best For | Example Use Case |
|--------|----------|----------|------------------|
| **src-mac** | Source MAC | Same source to multiple destinations | Server to multiple clients |
| **dst-mac** | Destination MAC | Multiple sources to same destination | Multiple clients to server |
| **src-dst-mac** | Source & Destination MAC | Balanced MAC traffic | General Layer 2 |
| **src-ip** | Source IP | Many sources to same destination | Web server farm |
| **dst-ip** | Destination IP | Same source to many destinations | Proxy server |
| **src-dst-ip** | Source & Destination IP | **Best general purpose** | Most networks |
| **src-port** | Source port | Per-application balancing | VoIP traffic |
| **dst-port** | Destination port | Per-service balancing | Web traffic |
| **src-dst-port** | Source & Destination port | **Most precise** | Application-level balancing |

### EtherChannel Requirements (Must Match Both Ends)

| Requirement | Description | Failure if Not Met |
|-------------|-------------|-------------------|
| **Speed** | 10/100/1000 Mbps | Link not bundled |
| **Duplex** | Full or Half | Link not bundled |
| **VLAN Membership** | Same VLANs (access/trunk) | Link not bundled |
| **Trunk Configuration** | Same allowed VLANs | Link not bundled |
| **Physical Type** | All copper or all fiber | Link not bundled |
| **Channel Group Number** | Same group ID | Separate EtherChannels |

### Verification Commands

| Command | Purpose | Key Information |
|---------|---------|-----------------|
| `show etherchannel summary` | Check EtherChannel status | Flags (S=suspect, U=up, D=down) |
| `show etherchannel load-balance` | Verify load balancing method | Current algorithm |
| `show interfaces port-channel X` | Check port-channel status | Line protocol, bandwidth |
| `show lacp counters` | LACP statistics | PDUs sent/received |

---

## 4. Routing Concepts - OSPF & AD Comparison

### Administrative Distance Values (Memorize for Exam!)

| Route Source | Administrative Distance | Priority | Notes |
|--------------|------------------------|----------|-------|
| **Directly Connected** | 0 | Highest | Always preferred |
| **Static Route** | 1 | Very High | Manual routes |
| **EIGRP Summary** | 5 | High | Cisco proprietary |
| **EBGP** | 20 | High | External BGP |
| **EIGRP Internal** | 90 | Medium-High | Cisco proprietary |
| **IGRP** | 100 | Medium | Legacy Cisco |
| **OSPF** | 110 | Medium | Link-state |
| **IS-IS** | 115 | Medium-Low | Link-state |
| **RIP** | 120 | Low | Distance-vector |
| **EIGRP External** | 170 | Very Low | External routes |
| **iBGP** | 200 | Lowest | Internal BGP |
| **Unknown** | 255 | Not Used | Not installed |

### Routing Metrics Comparison

| Metric | Used By | Description | Calculation | Best For |
|--------|---------|-------------|-------------|----------|
| **Hop Count** | RIP | Number of routers to destination | Count hops | Simple networks |
| **Bandwidth** | OSPF, EIGRP | Link capacity | Inverse of bandwidth | High-speed networks |
| **Delay** | OSPF, EIGRP | Transit time | Cumulative delay | Time-sensitive traffic |
| **Reliability** | EIGRP | Link reliability | Packet loss rate | Critical links |
| **Load** | EIGRP | Current utilization | Bandwidth usage | Load balancing |
| **Cost** | OSPF, IS-IS | Inverse of bandwidth | 100Mbps ÷ bandwidth | General purpose |

### OSPF vs Other Routing Protocols

| Feature | OSPF | RIP | EIGRP |
|---------|------|-----|-------|
| **Type** | Link-state | Distance-vector | Advanced distance-vector |
| **Metric** | Cost (bandwidth-based) | Hop count | Composite (bandwidth, delay, etc.) |
| **Convergence** | Fast (<10s) | Slow (180s+) | Very Fast |
| **Administrative Distance** | 110 | 120 | 90 (internal) |
| **VLSM Support** | ✅ Yes | ❌ No (RIPv1) | ✅ Yes |
| **Scalability** | Large | Small | Medium-Large |
| **Hierarchical** | ✅ Areas | ❌ No | ❌ No |
| **Standard** | ✅ Open standard | ✅ Open standard | ❌ Cisco proprietary |

### OSPF Area Types

| Area Type | Description | Characteristics |
|-----------|-------------|----------------|
| **Backbone Area (0)** | Central area, connects all other areas | Must be present, contiguous |
| **Regular Area** | Non-backbone area | Connects to backbone, accepts all LSAs |
| **Stub Area** | No external routes, uses default route | Reduces LSDB size, no Type 5 LSAs |
| **Totally Stub** | Only default route, no inter-area routes | Cisco proprietary, minimal routing |
| **NSSA** | Not-so-stubby area, allows external routes | Allows Type 7 LSAs |
| **Totally NSSA** | Only default route, no inter-area routes | Cisco proprietary |

### OSPF Network Types

| Network Type | DR/BDR Election | Characteristics | Command |
|--------------|-----------------|----------------|---------|
| **Broadcast** | Yes | Ethernet, Token Ring | Default for multi-access |
| **Point-to-Point** | No | Serial, PPP | Serial links |
| **Point-to-Multipoint** | No | Multiple PVCs | Frame Relay |
| **Non-Broadcast Multi-Access (NBMA)** | Yes | Frame Relay (no broadcast) | Manual neighbor config |

---

## 5. DHCPv4 Comparison Table

### DHCPv4 Message Types (DORA Process)

| Step | Message | Direction | Purpose | Key Info |
|------|---------|-----------|---------|----------|
| **D** - Discover | DHCPDISCOVER | Client → Broadcast (255.255.255.255) | Find DHCP server | Source IP = 0.0.0.0 |
| **O** - Offer | DHCPOFFER | Server → Client (unicast/broadcast) | Offer IP address | Contains offered IP |
| **R** - Request | DHCPREQUEST | Client → Broadcast | Request offered IP | Confirms selection |
| **A** - Acknowledge | DHCPACK | Server → Client | Confirm assignment | Contains all config |

### Other DHCP Messages

| Message | Direction | Purpose |
|---------|-----------|---------|
| **DHCPNACK** | Server → Client | Deny client's request |
| **DHCPDECLINE** | Client → Server | Address already in use |
| **DHCPRELEASE** | Client → Server | Release IP address |
| **DHCPINFORM** | Client → Server | Request additional config only |

### DHCPv4 Address Assignment Methods

| Method | Server Required | Complexity | Scalability | Use Case |
|--------|----------------|------------|-------------|----------|
| **Manual (Static)** | None | High | Low | Servers, printers |
| **Automatic** | Yes | Low | Medium | Small networks |
| **Dynamic** | Yes | Low | High | **Most common** - Desktops, laptops |
| **APIPA** | None | None | Low | No DHCP server (169.254.x.x) |

### DHCPv4 Lease Management

| Timer | Percentage | Action | Characteristics |
|-------|------------|--------|----------------|
| **T1** | 50% of lease | Unicast renewal to original server | Tries to renew with same server |
| **T2** | 87.5% of lease | Broadcast renewal to any server | If original doesn't respond |
| **Expiration** | 100% of lease | Address returned to pool | Client must request new IP |

### DHCPv4 Configuration Comparison

| Configuration | Command | Purpose | Example |
|---------------|---------|---------|---------|
| **Exclude addresses** | `ip dhcp excluded-address X Y` | Reserve static IPs | `ip dhcp excluded-address 192.168.1.1 192.168.1.10` |
| **Create pool** | `ip dhcp pool POOL_NAME` | Create DHCP pool | `ip dhcp pool LAN` |
| **Network** | `network X.X.X.X mask` | Define network range | `network 192.168.1.0 255.255.255.0` |
| **Default gateway** | `default-router X.X.X.X` | Set gateway | `default-router 192.168.1.1` |
| **DNS servers** | `dns-server X.X.X.X Y.Y.Y.Y` | Set DNS | `dns-server 8.8.8.8 8.8.4.4` |
| **Domain name** | `domain-name NAME` | Set domain | `domain-name example.com` |
| **Lease time** | `lease DAYS` | Set lease duration | `lease 7` (7 days) |
| **Helper address** | `ip helper-address X.X.X.X` | Forward DHCP requests | `ip helper-address 192.168.2.10` |

### DHCP Relay vs DHCP Server

| Feature | DHCP Server | DHCP Relay (Helper) |
|---------|-------------|---------------------|
| **Role** | Assigns IP addresses | Forwards requests to server |
| **Configuration** | Create pools, network, etc. | `ip helper-address` on interface |
| **Placement** | Same subnet as clients | Router between subnets |
| **Broadcast** | Receives broadcasts | Converts to unicast |
| **Multiple subnets** | Needs multiple pools | Single server can serve multiple subnets |

---

## 6. WLAN Concepts & Configuration Comparison

### 802.11 Standards Comparison

| Standard | Frequency | Max Speed | Year | MIMO | Channel Width | Key Features |
|----------|-----------|-----------|------|------|---------------|--------------|
| **802.11a** | 5 GHz | 54 Mbps | 1999 | No | 20 MHz | Less interference |
| **802.11b** | 2.4 GHz | 11 Mbps | 1999 | No | 20 MHz | Longest range |
| **802.11g** | 2.4 GHz | 54 Mbps | 2003 | No | 20 MHz | Improved 2.4 GHz |
| **802.11n** | 2.4/5 GHz | 600 Mbps | 2009 | 4x4 | 20/40 MHz | MIMO, dual-band |
| **802.11ac** | 5 GHz | 3.5 Gbps | 2013 | 8x8 | 20/40/80/160 MHz | Beamforming, MU-MIMO |
| **802.11ax** | 2.4/5/6 GHz | 9.6 Gbps | 2019 | 8x8 | 20/40/80/160 MHz | OFDMA, WPA3, target wake time |

### Frequency Bands Comparison

| Band | Channels | Non-Overlapping | Range | Interference | Best For |
|------|----------|------------------|-------|--------------|----------|
| **2.4 GHz** | 1-14 | 1, 6, 11 | Longer | High (microwaves, Bluetooth) | Coverage, legacy devices |
| **5 GHz** | 36-165 | Many | Shorter | Low | High density, high speed |
| **6 GHz** | 1-233 | Many | Shortest | Very low | High performance, enterprise |

### AP Types Comparison

| Type | Management | Configuration | Scalability | Redundancy | Use Case |
|------|------------|---------------|-------------|------------|----------|
| **Autonomous AP** | Individual | Per-device | Low | Individual | Small deployments, remote sites |
| **Controller-based (LAP)** | Centralized (WLC) | Via WLC | High | Roaming, failover | **Enterprise**, large deployments |
| **Cloud-managed** | Cloud-based | Via cloud portal | High | Cloud-based | Multi-site, managed services |

### WLAN Modes Comparison

| Mode | Infrastructure Required | Communication Path | Characteristics | Use Case |
|------|-------------------------|-------------------|-----------------|----------|
| **Ad-Hoc (IBSS)** | No AP | Device-to-device | No AP, peer-to-peer | Temporary connections |
| **Infrastructure** | AP required | Device → AP → Network | Centralized, managed | **Standard** for most networks |

### Authentication Methods Comparison

| Method | Type | Configuration | Security Level | Use Case |
|--------|------|---------------|----------------|----------|
| **Open** | None | No password | Very Low | Public hotspots |
| **PSK (Pre-Shared Key)** | WPA/WPA2-Personal | Shared password | Medium | Home, small office |
| **802.1X** | WPA/WPA2-Enterprise | RADIUS server | Very High | **Corporate** networks |
| **Captive Portal** | Web-based | Web login | Low-Medium | Guest networks |

### Encryption Standards Comparison

| Encryption | Key Management | Authentication | Integrity | Security Level | Recommendation |
|-----------|----------------|----------------|-----------|----------------|----------------|
| **WEP** | Static (shared) | None (open) | CRC-32 | ❌ Broken | Do NOT use |
| **WPA** | TKIP (dynamic) | PSK or 802.1X | MIC | ⚠️ Weak | Upgrade to WPA2 |
| **WPA2** | CCMP/AES | PSK or 802.1X | CCMP | ✅ Good | **Recommended** |
| **WPA3** | SAE (simultaneous auth) | SAE | GCMP | ✅✅ Best | Latest standard |

### CAPWAP Tunnel Types

| Tunnel Type | Traffic | Encryption | Purpose |
|-------------|---------|------------|---------|
| **Control Tunnel** | Management, configuration | DTLS | AP-WLC communication |
| **Data Tunnel** | Client traffic | Optional (DTLS) | Client data forwarding |

### WLAN Security Features

| Feature | Purpose | Configuration | Protection |
|---------|---------|---------------|------------|
| **WIDS/WIPS** | Wireless intrusion detection/prevention | Via WLC | Rogue AP detection, attacks |
| **PMF (802.11w)** | Protect management frames | WPA3 | Deauth attacks |
| **Management Frame Protection** | Secure management frames | WPA2/3 | Disassociation attacks |
| **Geolocation** | Track AP locations | Via WLC | Security, compliance |

---

## 7. LAN Security Comparison Table

### AAA Components Comparison

| Component | Question Answered | Implementation | Example | Logging |
|-----------|-------------------|----------------|---------|---------|
| **Authentication** | Who are you? | Username/password, certificates, tokens | Login to switch | ✅ Yes |
| **Authorization** | What can you do? | Privilege levels, access lists | Enable mode commands | ✅ Yes |
| **Accounting** | What did you do? | Track commands, time | Command history | ✅ Yes |

### 802.1X Components

| Component | Role | Device Type | Example |
|-----------|------|-------------|---------|
| **Supplicant** | Requests access | End device | Laptop, phone |
| **Authenticator** | Enforces authentication | Network device | Switch, AP |
| **Authentication Server** | Validates credentials | Server | RADIUS server |

### Layer 2 Security Threats Comparison

| Attack | Type | Target | Impact | Difficulty | Primary Mitigation |
|--------|------|--------|--------|------------|-------------------|
| **MAC Flooding** | DoS | Switch MAC table | Switch floods all frames | Easy | Port Security |
| **MAC Spoofing** | Spoofing | Network access | Impersonate device | Easy | Port Security Sticky |
| **DHCP Starvation** | DoS | DHCP server | Exhaust address pool | Medium | DHCP Snooping |
| **DHCP Spoofing** | MiTM | Clients | Wrong network config | Easy | DHCP Snooping + DAI |
| **ARP Spoofing** | MiTM | ARP cache | Intercept traffic | Easy | DAI |
| **VLAN Hopping** | Unauthorized access | VLAN isolation | Access restricted VLANs | Medium | Disable DTP, proper trunking |
| **STP Attack** | DoS | STP topology | Network disruption | Medium | BPDU Guard, Root Guard |

### LAN Security Features Comparison

| Feature | Primary Protection | Configuration Complexity | Effectiveness | Prerequisites |
|----------|-------------------|-------------------------|--------------|---------------|
| **Port Security** | MAC flooding, spoofing | Low | High | None |
| **DHCP Snooping** | DHCP attacks | Medium | High | None |
| **Dynamic ARP Inspection (DAI)** | ARP spoofing | Medium | Very High | DHCP Snooping required |
| **IP Source Guard** | IP spoofing | Medium | Very High | DHCP Snooping required |
| **BPDU Guard** | STP attacks | Low | Very High | PortFast ports |
| **Root Guard** | Root bridge takeover | Low | High | Designated ports |
| **802.1X** | Unauthorized access | High | Very High | RADIUS server |
| **Storm Control** | Broadcast storms | Low | Medium | None |

### Port Security Violation Actions

| Action | Behavior | Logging | Port Recovery | Use Case |
|--------|----------|---------|---------------|----------|
| **Protect** | Drops violating frames | ❌ No | Automatic (when frames stop) | Silent monitoring |
| **Restrict** | Drops violating frames | ✅ Yes | Automatic (when frames stop) | Need alerts |
| **Shutdown** | Disables port (err-disabled) | ✅ Yes | Manual (`shutdown`, `no shutdown`) | High security |

---

## 8. FHRP Comparison Table

### FHRP Protocols Comparison

| Feature | HSRP (Cisco) | VRRP (IEEE) | GLBP (Cisco) |
|---------|--------------|-------------|--------------|
| **Standard** | Cisco proprietary | IEEE 802.3ad | Cisco proprietary |
| **Load Balancing** | ❌ No (Active/Standby) | ❌ No (Master/Backup) | ✅ Yes (AVG + AVFs) |
| **Virtual MAC** | One per group | One per group | Multiple per group |
| **IPv6 Support** | Version 2 only | ✅ Yes | ✅ Yes |
| **Preemption** | Optional | Optional | Default |
| **Multicast Address** | 224.0.0.2 | 224.0.0.18 | 224.0.0.102 |
| **Hello Timer (default)** | 3 seconds | 1 second | 3 seconds |
| **Hold Timer (default)** | 10 seconds | 3 seconds | 10 seconds |
| **Priority Range** | 0-255 (default 100) | 0-255 (default 100) | 1-255 (default 100) |
| **Authentication** | MD5 (v2) | None (RFC) | MD5 |
| **Virtual IP** | Configured | Same as router IP | Same as router IP |
| **Active/Master Election** | Highest priority | Highest priority | Highest priority |

### HSRP States Comparison

| State | Description | Can Forward? | Hello Messages? | Transition From |
|-------|-------------|--------------|-----------------|----------------|
| **Initial** | Router starting | ❌ No | ❌ No | Configuration |
| **Learn** | Waiting for hello with VIP | ❌ No | ❌ No | Received hello with VIP |
| **Listen** | Knows VIP, not active/standby | ❌ No | ✅ Yes | Lower priority, hello received |
| **Speak** | Sending hellos, election in progress | ❌ No | ✅ Yes | Higher priority, no active |
| **Standby** | Backup router | ❌ No (backup only) | ✅ Yes | Higher than speak, lower than active |
| **Active** | Currently forwarding | ✅ Yes | ✅ Yes | Highest priority |

### GLBP Roles Comparison

| Role | Description | Quantity | Responsibilities |
|------|-------------|----------|-------------------|
| **AVG (Active Virtual Gateway)** | Manages virtual MAC assignment | 1 per group | Responds to ARP requests, assigns VMACs |
| **AVF (Active Virtual Forwarder)** | Forwards traffic for a VMAC | Up to 4 per group | Forwards packets for assigned VMAC |

### FHRP Load Balancing Comparison

| Protocol | Load Balancing Method | How it Works | Number of Active Routers |
|----------|----------------------|--------------|-------------------------|
| **HSRP** | None | One active, others standby | 1 active |
| **VRRP** | None | One master, others backup | 1 master |
| **GLBP** | Round-robin MAC assignment | AVG assigns different VMACs to AVFs | Up to 4 AVFs |

---

## 9. IP Addressing Comparison

### FLSM vs VLSM Comparison

| Feature | FLSM (Fixed Length) | VLSM (Variable Length) |
|---------|---------------------|-----------------------|
| **Subnet Mask** | Same for all subnets | Different for each subnet |
| **Subnet Size** | Same for all subnets | Based on requirements |
| **Address Efficiency** | May waste addresses | Efficient utilization |
| **Configuration** | Simple | More complex |
| **Scalability** | Limited | Better |
| **Best For** | Small, uniform networks | Large, varied networks |
| **Planning** | Simple | Requires careful planning |
| **Summarization** | Easier | More complex |
| **Flexibility** | Low | High |

### IPv4 vs IPv6 Comparison

| Feature | IPv4 | IPv6 |
|---------|------|------|
| **Address Length** | 32 bits | 128 bits |
| **Address Format** | Dotted decimal | Hexadecimal (:) |
| **Total Addresses** | ~4.3 billion | ~340 undecillion |
| **Header Size** | 20-60 bytes | 40 bytes (fixed) |
| **Checksum** | Included | Removed (simpler processing) |
| **Broadcast** | Yes (255.255.255.255) | No (uses multicast) |
| **ARP** | Yes | No (uses NDP) |
| **DHCP** | Optional | Optional (SLAAC available) |
| **Fragmentation** | Routers and hosts | Hosts only |
| **NAT** | Common (due to shortage) | Not required |

### IPv6 Address Types Comparison

| Type | Prefix | Purpose | Scope |
|------|--------|---------|-------|
| **Link-Local** | FE80::/10 | Local communication | Link only |
| **Unique Local** | FC00::/7 | Private addressing | Internal use (like IPv4 private) |
| **Global Unicast** | 2000::/3 | Internet routable | Global |
| **Multicast** | FF00::/8 | One-to-many | Various scopes |
| **Anycast** | From other types | One-to-nearest | Routing-dependent |

### IPv6 Address Assignment Methods Comparison

| Method | Address Source | Server Required | Configuration Complexity | Characteristics |
|--------|----------------|-----------------|-------------------------|----------------|
| **SLAAC** | Prefix + EUI-64 or Random | No | Very Low | Stateless, automatic |
| **Stateless DHCPv6** | Address from SLAAC, other from DHCP | Yes | Low | Address auto, other manual |
| **Stateful DHCPv6** | Everything from DHCP | Yes | Medium | Full DHCP control |
| **Manual** | Configured manually | No | High | For servers, routers |

### Subnetting Reference (VLSM)

| Hosts Needed | Host Bits | Usable Hosts | CIDR | Subnet Mask |
|--------------|-----------|--------------|------|-------------|
| 2 | 2 | 2 | /30 | 255.255.255.252 |
| 6 | 3 | 6 | /29 | 255.255.255.248 |
| 14 | 4 | 14 | /28 | 255.255.255.240 |
| 30 | 5 | 30 | /27 | 255.255.255.224 |
| 62 | 6 | 62 | /26 | 255.255.255.192 |
| 126 | 7 | 126 | /25 | 255.255.255.128 |
| 254 | 8 | 254 | /24 | 255.255.255.0 |

---

## 10. Layer 2 Attacks & Mitigation - Command Reference

### Attack 1: MAC Flooding

**What is it?**
Attacker sends thousands of fake MAC addresses to switch, filling MAC address table. When table is full, switch enters "fail-open" mode and floods all frames out all ports, allowing attacker to capture all traffic.

**Mitigation: Port Security**

```bash
# Enable port security on interface
Switch(config)# interface fastethernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport port-security

# Set maximum MAC addresses
Switch(config-if)# switchport port-security maximum 3

# Set violation action (protect, restrict, shutdown)
Switch(config-if)# switchport port-security violation shutdown

# Sticky learning (learn MACs dynamically)
Switch(config-if)# switchport port-security mac-address sticky

# Static MAC assignment
Switch(config-if)# switchport port-security mac-address 00:11:22:33:44:55
```

**Verification:**
```bash
Switch# show port-security interface fastethernet 0/1
Switch# show port-security address
```

---

### Attack 2: MAC Spoofing

**What is it?**
Attacker changes their device's MAC address to match a legitimate device (like the router), allowing them to bypass MAC-based security filters and impersonate trusted devices.

**Mitigation: Port Security with Sticky MAC**

```bash
# Enable sticky MAC learning
Switch(config)# interface fastethernet 0/1
Switch(config-if)# switchport port-security
Switch(config-if)# switchport port-security mac-address sticky
Switch(config-if)# switchport port-security maximum 1
```

**Verification:**
```bash
Switch# show port-security address
Switch# show mac address-table address 00:11:22:33:44:55
```

---

### Attack 3: DHCP Starvation / Rogue DHCP

**What is it?**
Attacker floods network with DHCP requests using fake MAC addresses, exhausting all available IP addresses in the DHCP pool, preventing legitimate clients from getting IP addresses. Alternatively, attacker sets up unauthorized DHCP server to assign incorrect network configuration.

**Mitigation: DHCP Snooping**

```bash
# Enable DHCP snooping globally
Switch(config)# ip dhcp snooping

# Enable on specific VLANs
Switch(config)# ip dhcp snooping vlan 10,20,30

# Mark trusted ports (connected to legitimate DHCP server)
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# ip dhcp snooping trust

# Mark untrusted ports (user ports) - default is untrusted
Switch(config)# interface fastethernet 0/1
Switch(config-if)# no ip dhcp snooping trust

# Optional: Limit DHCP rate
Switch(config-if)# ip dhcp snooping limit rate 10
```

**Verification:**
```bash
Switch# show ip dhcp snooping
Switch# show ip dhcp snooping binding
```

---

### Attack 4: DHCP Spoofing (Rogue DHCP Server)

**What is it?**
Attacker sets up unauthorized DHCP server that assigns wrong default gateway, DNS servers, or IP addresses, directing traffic through attacker's device for man-in-the-middle attacks.

**Mitigation: DHCP Snooping + DAI (Dynamic ARP Inspection)**

```bash
# DHCP Snooping (prerequisite)
Switch(config)# ip dhcp snooping
Switch(config)# ip dhcp snooping vlan 10
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# ip dhcp snooping trust

# Dynamic ARP Inspection (prevents ARP spoofing)
Switch(config)# ip arp inspection vlan 10

# Mark trusted ports (router, switch)
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# ip arp inspection trust

# Untrusted ports (user devices) - default
Switch(config)# interface fastethernet 0/1
Switch(config-if)# no ip arp inspection trust
```

**Verification:**
```bash
Switch# show ip dhcp snooping
Switch# show ip arp inspection
Switch# show ip arp inspection statistics
```

---

### Attack 5: ARP Spoofing / Poisoning

**What is it?**
Attacker sends fake ARP messages mapping legitimate IP addresses to attacker's MAC address. This causes devices to send traffic to attacker instead of intended destination, enabling man-in-the-middle attacks.

**Mitigation: Dynamic ARP Inspection (DAI)**

```bash
# Prerequisite: DHCP Snooping must be enabled
Switch(config)# ip dhcp snooping
Switch(config)# ip dhcp snooping vlan 10

# Enable DAI on VLANs
Switch(config)# ip arp inspection vlan 10,20,30

# Mark trusted ports (routers, switches)
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# ip arp inspection trust

# Optional: Validate ARP packets
Switch(config-if)# ip arp inspection validate src-mac dst-mac ip

# Optional: Limit ARP rate
Switch(config-if)# ip arp inspection limit rate 15
```

**Verification:**
```bash
Switch# show ip arp inspection
Switch# show ip arp inspection statistics
Switch# show ip arp inspection interface fastethernet 0/1
```

---

### Attack 6: IP Spoofing

**What is it?**
Attacker sends packets with forged source IP addresses to bypass IP-based security controls or launch denial-of-service attacks while hiding their identity.

**Mitigation: IP Source Guard**

```bash
# Prerequisite: DHCP Snooping must be enabled
Switch(config)# ip dhcp snooping
Switch(config)# ip dhcp snooping vlan 10

# Enable IP Source Guard on interface
Switch(config)# interface fastethernet 0/1
Switch(config-if)# ip verify source vlan dhcp-snooping

# For static IP hosts, use:
Switch(config-if)# ip verify source vlan dhcp-snooping port-security
```

**Verification:**
```bash
Switch# show ip verify source
Switch# show ip verify source interface fastethernet 0/1
```

---

### Attack 7: VLAN Hopping

**What is it?**
Attacker attempts to access VLANs they're not authorized to access by exploiting trunking misconfigurations or using double-tagging attacks.

**Mitigation 1: Disable DTP on Access Ports**

```bash
# Force access mode and disable DTP negotiation
Switch(config)# interface fastethernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport nonegotiate
```

**Mitigation 2: Change Native VLAN from Default**

```bash
# On trunk ports, change native VLAN to unused VLAN
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk native vlan 999
Switch(config-if)# switchport trunk allowed vlan 10,20,30
```

**Mitigation 3: Prune Unused VLANs**

```bash
# Only allow necessary VLANs on trunk
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# switchport trunk allowed vlan 10,20,30
```

**Verification:**
```bash
Switch# show interfaces trunk
Switch# show interfaces switchport
```

---

### Attack 8: STP Manipulation / BPDU Attack

**What is it?**
Attacker sends fake BPDUs to become root bridge or disrupt STP topology, causing network disruption or enabling traffic interception.

**Mitigation 1: BPDU Guard (for edge ports)**

```bash
# Enable on edge ports (PortFast ports)
Switch(config)# interface fastethernet 0/1
Switch(config-if)# spanning-tree portfast
Switch(config-if)# spanning-tree bpduguard enable

# Or enable globally for all PortFast ports
Switch(config)# spanning-tree portfast bpduguard default
```

**Mitigation 2: Root Guard (for designated ports toward edge)**

```bash
# Enable on designated ports that should never be root
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# spanning-tree guard root
```

**Mitigation 3: BPDU Filter (use with caution)**

```bash
# Don't send or receive BPDUs (edge ports only)
Switch(config)# interface fastethernet 0/1
Switch(config-if)# spanning-tree bpdufilter enable
```

**Verification:**
```bash
Switch# show spanning-tree
Switch# show spanning-tree detail
Switch# show spanning-tree interface fastethernet 0/1
```

---

### Attack 9: STP Root Bridge Takeover

**What is it?**
Attacker sets up a switch with very low priority to become root bridge, causing STP topology changes that redirect traffic through attacker's switch.

**Mitigation: Root Guard**

```bash
# Enable on ports that should never receive superior BPDUs
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# spanning-tree guard root

# If port receives superior BPDU, it transitions to root-inconsistent state
```

**Verification:**
```bash
Switch# show spanning-tree inconsistentports
Switch# show spanning-tree interface gigabitethernet 0/1 detail
```

---

### Attack 10: Unidirectional Link

**What is it?**
Link where traffic flows in only one direction due to hardware failure, causing STP loops because one switch doesn't receive BPDUs.

**Mitigation: Loop Guard**

```bash
# Enable on root and alternate ports
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# spanning-tree guard loop

# Or enable globally
Switch(config)# spanning-tree loopguard default
```

**Verification:**
```bash
Switch# show spanning-tree
Switch# show spanning-tree detail
```

---

### Complete Security Configuration Example

```bash
! Enable DHCP Snooping
Switch(config)# ip dhcp snooping
Switch(config)# ip dhcp snooping vlan 10,20,30

! Enable DAI
Switch(config)# ip arp inspection vlan 10,20,30

! Configure trusted ports (DHCP server, router)
Switch(config)# interface gigabitethernet 0/1
Switch(config-if)# description Uplink to Router
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20,30
Switch(config-if)# switchport trunk native vlan 999
Switch(config-if)# ip dhcp snooping trust
Switch(config-if)# ip arp inspection trust
Switch(config-if)# spanning-tree guard root

! Configure user ports
Switch(config)# interface range fastethernet 0/1 - 24
Switch(config-if-range)# description User Ports
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10
Switch(config-if-range)# switchport nonegotiate
Switch(config-if-range)# switchport port-security
Switch(config-if-range)# switchport port-security maximum 2
Switch(config-if-range)# switchport port-security violation shutdown
Switch(config-if-range)# switchport port-security mac-address sticky
Switch(config-if-range)# spanning-tree portfast
Switch(config-if-range)# spanning-tree bpduguard enable
Switch(config-if-range)# ip verify source vlan dhcp-snooping
```

---

## Quick Command Reference for Exam

### General Verification Commands

```bash
show running-config                    # Current configuration
show startup-config                    # Saved configuration
show version                           # System information
show ip interface brief                # Interface status
show vlan brief                        # VLAN information
show spanning-tree                     # STP status
show etherchannel summary              # EtherChannel status
show ip route                          # Routing table
show ip dhcp binding                   # DHCP assignments
show ip dhcp snooping                  # DHCP snooping status
show ip arp inspection                 # DAI status
show port-security interface           # Port security status
show standby                           # HSRP status
show vrrp                              # VRRP status
show glbp                              # GLBP status
```

### Troubleshooting Commands

```bash
ping <ip-address>                      # Test connectivity
traceroute <ip-address>                # Show path
show mac address-table                 # MAC table
show controllers ethernet-controller X # Hardware details
debug ip dhcp server packet           # Monitor DHCP
debug spanning-tree events            # Monitor STP
```

---

## Exam Preparation Tips

### What to Focus On:

1. **EtherChannel** - Mode combinations, LACP vs PAgP
2. **STP** - Port states, protection mechanisms, root election
3. **Routing** - Administrative distance values (memorize!), OSPF basics
4. **DHCP** - DORA process, configuration commands
5. **WLAN** - Standards comparison, security (WPA2 vs WPA3)
6. **LAN Security** - L2 attacks and mitigations (memorize commands!)
7. **FHRP** - HSRP vs VRRP vs GLBP comparison
8. **VLSM** - Subnetting calculations, FLSM vs VLSM

### Practice Checklist:

- [ ] Configure VLANs and trunking
- [ ] Configure inter-VLAN routing (router-on-a-stick and Layer 3)
- [ ] Configure STP with protection mechanisms
- [ ] Configure EtherChannel with LACP
- [ ] Configure DHCP server and relay
- [ ] Configure WLAN security
- [ ] Configure port security, DHCP snooping, DAI, IP Source Guard
- [ ] Configure HSRP/VRRP/GLBP
- [ ] Troubleshoot common issues

### SRWE Final Skill Exam Preparation:

1. **Practice Packet Tracer scenarios** from NetAcad
2. **Memorize configuration commands** for all security features
3. **Understand the "why"** behind each technology
4. **Practice troubleshooting** - know verification commands
5. **Time management** - skill exam has time limits

**Good luck with your exam on March 31!** 🎯