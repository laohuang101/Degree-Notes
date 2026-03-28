# Ethical Hacking and Incident Response - Complete Lecture Notes

**Course Code:** CT080-3-2 (Version VE1)
**Total Modules:** 10

---

## Table of Contents

1. [Module 1: Introduction to Ethical Hacking](#module-1-introduction-to-ethical-hacking)
2. [Module 2: Footprinting and Reconnaissance](#module-2-footprinting-and-reconnaissance)
3. [Module 3: Computer and Network Scanning](#module-3-computer-and-network-scanning)
4. [Module 4: System Enumeration](#module-4-system-enumeration)
5. [Module 5: Vulnerability Analysis](#module-5-vulnerability-analysis)
6. [Module 6: System Hacking](#module-6-system-hacking)
7. [Module 7: Introduction to Incident Response and Digital Forensics](#module-7-introduction-to-incident-response-and-digital-forensics)
8. [Module 8: Memory Acquisition and Analysis](#module-8-memory-acquisition-and-analysis)
9.  [Module 9: Data Hiding and Steganography](#module-9-data-hiding-and-steganography)
10. [Module 10: Cryptography](#module-10-cryptography)

---

### Virtual Machines Used

- **Windows XP**
- **Windows 2008**
- **Windows 2000**
- **Kali Linux** (Debian-derived distribution designed for Penetration Testing)

---

## Module 1: Introduction to Ethical Hacking

---

### 1. Information Security Overview

#### Elements of Information Security

| Element | Description |
|---------|-------------|
| **Confidentiality** | Preventing unauthorized disclosure of information |
| **Integrity** | Preventing unauthorized modification of information |
| **Availability** | Ensuring timely and reliable access to information |
| **Non-repudiation** | Proof of origin and delivery of information |
| **Authentication** | Verifying the identity of users and systems |
| **Authorization** | Granting access rights to resources |

#### Information Security Attacks

| Attack Type | Description | Example |
|-------------|-------------|---------|
| **Passive Attacks** | Monitor and intercept data without altering it | Eavesdropping, traffic analysis |
| **Active Attacks** | Alter data or disrupt system operations | Denial of service, data modification |
| **Insider Attacks** | Perpetrated by authorized users | Disgruntled employee data theft |
| **Outsider Attacks** | Perpetrated by unauthorized external parties | External hacking attempts |

---

### 2. Cyber Kill Chain Concepts

#### What is Cyber Kill Chain?

- Security framework developed by Lockheed Martin
- Describes stages of a cyberattack and how defenders can detect & stop it
- Helps organizations understand threats at every stage of an attack
- Provides clear insight into attack strategy used by adversaries

#### Cyber Kill Chain Methodology

| Stage | Description | Adversary Activities |
|-------|-------------|---------------------|
| **1. Reconnaissance** | Gathering information about the target | Searching internet, Whois, DNS, network footprinting, scanning |
| **2. Weaponization** | Creating malicious payload | Identifying malware payload, creating phishing emails, using exploit kits |
| **3. Delivery** | Transmitting payload to victim | Sending phishing emails, distributing USB drives, watering hole attacks |
| **4. Exploitation** | Triggering malicious code to exploit vulnerabilities | Exploiting software/hardware vulnerabilities to gain remote access |
| **5. Installation** | Installing malicious software to maintain access | Downloading backdoors, gaining remote access, hiding presence |
| **6. Command and Control (C2)** | Establishing communication channel with victim | Creating two-way communication, applying encryption, privilege escalation |
| **7. Actions on Objectives** | Accomplishing attacker's goals | Gaining access to confidential data, disrupting services, destroying capabilities |

#### Tactics, Techniques, and Procedures (TTPs)

| Component | Description |
|-----------|-------------|
| **Tactics** | What attacker wants to achieve |
| **Techniques** | How the attacker achieves the goal |
| **Procedures** | Step-by-step execution of the attack |

#### Indicators of Compromise (IoCs)

Artifacts observed on a network or in an operating system that indicate a computer intrusion:

| Type | Examples |
|------|----------|
| **Network IoCs** | IP addresses, domain names, URLs, file hashes |
| **Host-based IoCs** | File names, registry keys, process names, file paths |
| **Behavioral IoCs** | Unusual network traffic, unusual process behavior |

---

### 3. Hacking Concepts

#### What is Hacking?

Hacking is the practice of modifying the features of a system to accomplish a goal outside the creator's original purpose.

#### Hacker Classes

| Type | Description | Motivation |
|------|-------------|------------|
| **White Hat Hackers** | Ethical hackers who help organizations find vulnerabilities | Improve security |
| **Black Hat Hackers** | Malicious hackers who exploit vulnerabilities for personal gain | Financial gain, destruction |
| **Gray Hat Hackers** | Hackers who may violate laws or ethical standards but without malicious intent | Curiosity, challenge |
| **Script Kiddies** | Inexperienced hackers who use pre-written scripts | Fun, mischief |
| **Hacktivists** | Hackers who use hacking for political or social causes | Political/social messaging |
| **State-sponsored Hackers** | Hackers employed by governments | Cyber warfare, espionage |

#### Five Phases of Hacking

| Phase | Description | Techniques |
|-------|-------------|------------|
| **1. Reconnaissance** | Information gathering about target | OSINT, social engineering, Whois, DNS queries |
| **2. Scanning** | Identify live systems, open ports, services | Port scanning, vulnerability scanning |
| **3. Gaining Access** | Exploit vulnerabilities to enter system | Password cracking, exploiting buffer overflows |
| **4. Maintaining Access** | Establish persistence on compromised system | Backdoors, rootkits, creating new accounts |
| **5. Clearing Tracks** | Remove evidence of compromise | Log deletion, file wiping, disabling auditing |

---

### 4. Ethical Hacking Concepts

#### What is Ethical Hacking?

Ethical hacking (also called penetration testing) involves breaking into computer systems with permission to identify vulnerabilities and security weaknesses that malicious hackers could exploit.

#### Why is Ethical Hacking Necessary?

| Reason | Explanation |
|--------|-------------|
| **Identify vulnerabilities** | Find security weaknesses before attackers do |
| **Improve security posture** | Strengthen defenses against real attacks |
| **Compliance requirements** | Meet regulatory and industry standards |
| **Risk mitigation** | Reduce the risk of successful attacks |
| **Cost-effective security** | Finding issues early is cheaper than dealing with breaches |

#### Skills Required for Ethical Hacking

| Skill Area | Required Knowledge |
|------------|-------------------|
| **Technical Skills** | Networking, operating systems, programming, databases |
| **Security Knowledge** | Cryptography, protocols, vulnerabilities, exploits |
| **Tools Proficiency** | Nmap, Metasploit, Burp Suite, Wireshark, etc. |
| **Analytical Skills** | Problem-solving, critical thinking, attention to detail |
| **Communication Skills** | Report writing, presentation, documentation |

---

### 5. Information Security Controls

#### Defense-in-Depth

Defense-in-depth is a layered security approach that uses multiple security controls to protect systems and data:

| Layer | Controls |
|-------|----------|
| **Perimeter** | Firewalls, IDS/IPS, network segmentation |
| **Network** | VPN, network access control, secure protocols |
| **Endpoint** | Antivirus, host-based firewall, application whitelisting |
| **Application** | Secure coding, input validation, authentication |
| **Data** | Encryption, backup, access controls |
| **Physical** | Access control, surveillance, environmental controls |

#### Risk Management

| Component | Description |
|-----------|-------------|
| **Risk Identification** | Identify assets, threats, and vulnerabilities |
| **Risk Assessment** | Evaluate likelihood and impact of risks |
| **Risk Mitigation** | Implement controls to reduce risks |
| **Risk Monitoring** | Continuously monitor and review risks |
| **Risk = Threat × Vulnerability × Impact** |

#### Cyber Threat Intelligence (CTI)

| Type | Purpose | Example |
|------|---------|---------|
| **Strategic** | Align cybersecurity strategies with potential risks | Report on emerging ransomware threats |
| **Tactical** | Assist security teams in implementing defenses | Details of phishing campaign characteristics |
| **Operational** | Provide insights into ongoing attacks | Real-time alerts about DDoS attacks |
| **Technical** | Used by security tools for detection and blocking | Malware signatures, C2 server IP addresses |

#### Threat Modeling Process

| Step | Description |
|------|-------------|
| **1. Identify Security Objectives** | Define confidentiality, integrity, and availability requirements |
| **2. Application Overview** | Identify components, data flows, and trust boundaries |
| **3. Decompose the Application** | Break down to identify entry/exit points and data flows |
| **4. Identify Threats** | Use threat modeling methodologies (STRIDE, DREAD) |
| **5. Identify Vulnerabilities** | Find weaknesses related to identified threats |

#### Incident Handling and Response (IH&R) Process

| Phase | Activities |
|-------|------------|
| **1. Preparation** | Audit resources, define policies, train team, gather tools |
| **2. Recording and Assignment** | Report incident, define communication plans |
| **3. Triage** | Analyze, validate, categorize, and prioritize incidents |
| **4. Notification** | Inform stakeholders (management, vendors, clients) |
| **5. Containment** | Prevent spread of infection to other assets |
| **6. Evidence Gathering** | Collect evidence for forensic analysis |
| **7. Eradication** | Remove root cause and close attack vectors |
| **8. Recovery** | Restore affected systems, services, and data |
| **9. Post-Incident Activities** | Document, assess impact, review policies, close investigation |

---

## Module 2: Footprinting and Reconnaissance

### 1. Footprinting Concepts

#### What is Footprinting?

Footprinting is the first and most important phase of ethical hacking, involving gathering as much information as possible about the target system before attempting to compromise it.

#### Objectives of Footprinting

| Objective | Description |
|-----------|-------------|
| **Know Security Posture** | Get complete profile of organization's security posture |
| **Reduce Focus Area** | Reduce unknown entity to specific domain names, network blocks, IP addresses |
| **Identify Vulnerabilities** | Identify vulnerabilities in target systems to select appropriate exploits |
| **Draw Network Map** | Create diagrammatic representation of target's network infrastructure |

#### Footprinting Methodology

| Step | Description | Tools |
|------|-------------|-------|
| **1. Identify the Target** | Define scope of footprinting activity | Google Dorks, Whois, Shodan, OSINT Framework |
| **2. Passive Footprinting** | Collect information without interacting with target | OSINT, DNS enumeration, social media recon |
| **3. Active Footprinting** | Interact directly with target system | Nmap, Masscan, Sublist3r, Burp Suite |
| **4. Network Information Gathering** | Gather network-related information | Nmap, Shodan, Censys, IPinfo.io |
| **5. Social Engineering** | Collect non-technical information from people | SET, Sherlock, Maltego |
| **6. Website Footprinting** | Discover web application vulnerabilities | Burp Suite, OWASP ZAP, Nikto |
| **7. DNS Footprinting** | Gather DNS server and record information | DNSDumpster, Fierce, Sublist3r, Nslookup |
| **8. Compile & Report** | Organize and report collected information | Create network maps, subdomain lists, vulnerability lists |

---

### 2. Footprinting via Search Engines

#### Google Hacking Techniques

Advanced search operators allow complex queries to find specific information:

| Operator | Purpose | Example |
|----------|---------|---------|
| `site:` | Search within specific domain | `site:example.com` |
| `filetype:` | Search for specific file types | `filetype:pdf` |
| `inurl:` | Search for URL containing specific text | `inurl:admin` |
| `intitle:` | Search for pages with specific title | `intitle:"index of"` |
| `cache:` | View cached version of webpage | `cache:example.com` |
| `link:` | Find pages linking to URL | `link:example.com` |
| `intext:` | Search for specific text in page body | `intext:"password"` |

#### Google Hacking Database (GHDB)

The GHDB contains queries that can find:

1. Error messages containing sensitive information
2. Files containing passwords
3. Sensitive directories
4. Pages containing logon portals
5. Pages containing network or vulnerability data
6. Advisories and server vulnerabilities
7. Software version information
8. Web application source code
9. Connected IoT devices and control panels
10. Hidden web pages (intranet, VPN services)

---

### 3. Footprinting via Web Services

#### Types of Information Gathered

| Information Source | What It Provides |
|-------------------|------------------|
| **Internet Archives** | Historical website data, removed content |
| **Social Networking Sites** | Employee names, job titles, relationships |
| **People Search Services** | Personal information, contact details |
| **Financial Services** | Company financial data, investors |
| **Job Sites** | Technology stack, organizational structure |
| **Deep/Dark Web** | Leaked credentials, exploit discussions |
| **Competitive Intelligence** | Market position, business strategies |

#### Popular Web Services for Footprinting

| Service | Purpose |
|---------|---------|
| **LinkedIn** | Employee information, organizational structure |
| **Hunter.io** | Email address discovery |
| **Maltego** | Visual link analysis and OSINT gathering |
| **Shodan** | Internet-connected device search |
| **Wayback Machine** | Historical website snapshots |
| **Have I Been Pwned** | Compromised credential checking |

---

### 4. Website Footprinting

#### Website Footprinting Techniques

| Technique | Description | Tools |
|-----------|-------------|-------|
| **Website Enumeration** | Identify subdomains, directories, files | Sublist3r, Gobuster, Dirb |
| **Server Fingerprinting** | Identify web server and version | WhatWeb, Wappalyzer, BuiltWith |
| **Content Discovery** | Find hidden files and directories | Gobuster, Dirbuster, Feroxbuster |
| **SSL/TLS Analysis** | Identify encryption weaknesses | SSL Labs, testssl.sh |
| **Website Mirroring** | Create local copy of website | HTTrack, NCollector Studio |
| **Link Extraction** | Extract all links from website | Burp Suite, Screaming Frog |
| **Metadata Extraction** | Extract metadata from documents | FOCA, exiftool |

---

### 5. Email Footprinting

#### Email Tracking Information

Email tracking tools can gather:

| Information | Description |
|-------------|-------------|
| **Recipient's System IP** | Track recipient's IP address |
| **Geolocation** | Estimate recipient's location |
| **Email Received/Read** | Notification when email is read |
| **Read Duration** | Time spent reading email |
| **Proxy Detection** | Type of server used by recipient |
| **Links Clicked** | Check if links were accessed |
| **OS and Browser** | Recipient's operating system and browser |
| **Forward Status** | Whether email was forwarded |
| **Device Type** | Desktop, mobile, or laptop |
| **Path Travelled** | Email route through transfer agents |

#### Email Tracking Tools

| Tool | Features |
|------|----------|
| **Mailtrack** | Email read receipts and tracking |
| **Yesware** | Email analytics and tracking |
| **BananaTag** | Email tracking and analytics |
| **Mixmax** | Email productivity and tracking |
| **Streak** | Email tracking and CRM |

---

### 6. Whois Footprinting

#### Whois Information Retrieved

| Information | Description |
|-------------|-------------|
| **Domain Name** | Registered domain name |
| **Registrar** | Organization that registered the domain |
| **Registration Details** | Creation, expiration, and updated dates |
| **Name Server** | DNS servers for the domain |
| **Contact Information** | Administrative, technical, and billing contacts |
| **IP Geolocation** | Geographic location of IP address |

#### Whois Lookup Tools

| Tool | Features |
|------|----------|
| **Whois** | Command-line Whois lookup |
| **Whois.net** | Online Whois lookup |
| **DomainTools** | Comprehensive domain research |
| **IPinfo.io** | IP geolocation and Whois |
| **MXToolbox** | DNS and Whois lookup |

---

### 7. DNS Footprinting

#### DNS Records Types

| Record Type | Purpose |
|-------------|---------|
| **A Record** | Maps hostname to IPv4 address |
| **AAAA Record** | Maps hostname to IPv6 address |
| **CNAME Record** | Alias for another domain name |
| **MX Record** | Mail exchange servers |
| **NS Record** | Name servers for domain |
| **TXT Record** | Text information (SPF, DKIM) |
| **SOA Record** | Start of Authority information |

#### DNS Footprinting Tools

| Tool | Features |
|------|----------|
| **Nslookup** | DNS lookup utility |
| **Dig** | Advanced DNS lookup tool |
| **DNSDumpster** | DNS reconnaissance and mapping |
| **Fierce** | DNS reconnaissance tool |
| **Sublist3r** | Subdomain enumeration |
| **Recon-ng** | Full-featured web reconnaissance framework |

#### Zone Transfer Attack

A Zone Transfer Attack exploits the DNS zone transfer (AXFR) mechanism:

| Step | Description |
|------|-------------|
| **1. DNS Servers Synchronize** | Primary DNS server maintains zone file |
| **2. Legitimate Use Case** | Secondary server requests zone copy via AXFR |
| **3. Exploitation** | Attacker mimics secondary server and sends AXFR request |
| **4. Result** | If misconfigured, attacker receives entire DNS zone file |

---

### 8. Network Footprinting

#### Network Footprinting Techniques

| Technique | Description | Tools |
|-----------|-------------|-------|
| **Locate Network Range** | Identify IP address ranges and subnets | Whois, IPinfo, CIDR calculators |
| **Traceroute** | Trace network path to target | Traceroute, tracert |
| **Network Mapping** | Create visual network topology | Nmap, Zenmap, Network Mapper |
| **Banner Grabbing** | Identify services and versions | Netcat, Telnet, Nmap |
| **OS Fingerprinting** | Identify operating system | Nmap, Xprobe2, p0f |

#### Traceroute Tools

| Tool | Features |
|------|----------|
| **Traceroute** | Unix/Linux network path tracer |
| **Tracert** | Windows network path tracer |
| **TCPtraceroute** | TCP-based traceroute |
| **MTR** | Combines ping and traceroute |

---

### 9. Footprinting via Social Engineering

#### Social Engineering Techniques

| Technique | Description |
|-----------|-------------|
| **Eavesdropping** | Listening to private conversations |
| **Shoulder Surfing** | Looking over someone's shoulder |
| **Dumpster Diving** | Searching through trash for information |
| **Impersonation** | Pretending to be someone else |
| **Phishing** | Sending fraudulent emails to obtain information |
| **Pretexting** | Creating a fabricated scenario to obtain information |
| **Baiting** | Offering something enticing to trick victim |
| **Quid Pro Quo** | Offering benefit in exchange for information |

#### Social Engineering Tools

| Tool | Features |
|------|----------|
| **Social-Engineer Toolkit (SET)** | Social engineering framework |
| **Maltego** | Link analysis for social engineering |
| **Sherlock** | Social media username enumeration |
| **OSINT Framework** | OSINT gathering tools |
| **Have I Been Pwned** | Check for compromised credentials |

---

### 10. Footprinting Tools

| Tool | Type | Features |
|------|------|----------|
| **Maltego** | OSINT | Visual link analysis and intelligence gathering |
| **Recon-ng** | OSINT | Full-featured web reconnaissance framework |
| **FOCA** | Metadata | Extract metadata from documents |
| **OSRFramework** | OSINT | Online search and reconnaissance |
| **Nmap** | Network | Network discovery and security auditing |
| **Shodan** | Network | Internet-connected device search |
| **Burp Suite** | Web | Web application security testing |
| **OWASP ZAP** | Web | Web application security scanner |

---

### 11. Footprinting Countermeasures

| Countermeasure | Description |
|----------------|-------------|
| **Restrict Public Information** | Minimize information available on public websites |
| **Configure DNS Security** | Disable zone transfers, implement DNSSEC |
| **Implement WAF** | Web Application Firewall to block reconnaissance |
| **Monitor Traffic** | Detect and block unusual scanning activities |
| **Educate Employees** | Train on social engineering awareness |
| **Use SSL/TLS** | Encrypt communications |
| **Implement Rate Limiting** | Prevent excessive scanning |
| **Disable Unnecessary Services** | Reduce attack surface |
| **Keep Software Updated** | Patch known vulnerabilities |
| **Use Security Headers** | Implement security headers (CSP, X-Frame-Options) |

---

## Module 3: Computer and Network Scanning

### 1. Network Scanning Concepts

#### Types of Scanning

| Scan Type | Purpose | Information Gathered |
|-----------|---------|---------------------|
| **Network Scanning** | Identify active hosts/IPs | Live systems, IP addresses |
| **Port Scanning** | Identify open ports/services | Open ports, running services |
| **Vulnerability Scanning** | Identify known weaknesses | Vulnerabilities, CVEs |

#### Objectives of Network Scanning

| Objective | Description |
|-----------|-------------|
| **Discover Live Hosts** | Identify active systems on network |
| **Discover OS and Architecture** | Identify operating system and system architecture (fingerprinting) |
| **Discover Running Services** | Identify services listening on target system |
| **Identify Applications/Versions** | Find specific applications or versions |
| **Identify Vulnerabilities** | Find vulnerabilities in network systems |

---

### 2. Scanning Tools

| Tool | Purpose | Key Features |
|------|---------|--------------|
| **Nmap** | Port/host/service/OS scanning | Flexible, powerful, extensive features |
| **Zenmap** | GUI for Nmap | Graphical interface for Nmap |
| **Hping2/Hping3** | Firewall testing, custom packet scanning | Custom packet crafting, firewall evasion |
| **Metasploit** | Exploits, vulnerability scanning | Exploit database, automated exploitation |
| **NetScanTools Pro** | LAN/internet scanning | Comprehensive network tools |

#### Nmap Features

Network administrators use Nmap for:
- Inventorying a network
- Managing service upgrade schedules
- Monitoring host or service uptime

Attackers use Nmap to extract:
- Live hosts on network
- Open ports
- Services (application name and version)
- Packet filters/firewalls
- Operating systems and versions

#### Hping2/Hping3

| Feature | Description |
|---------|-------------|
| **Network Security Auditing** | Test network security |
| **Firewall Testing** | Test firewall rules and configurations |
| **Manual Path MTU Discovery** | Discover path MTU |
| **Advanced Traceroute** | Advanced network path tracing |
| **Remote OS Fingerprinting** | Identify remote operating systems |
| **Remote Uptime Guessing** | Estimate system uptime |
| **TCP/IP Stacks Auditing** | Audit TCP/IP implementations |

---

### 3. Host Discovery

#### Host Discovery Techniques

| Technique | Description | Advantages |
|-----------|-------------|------------|
| **ARP Ping Scan** | Send ARP requests to discover active devices | More efficient and accurate, works behind firewalls |
| **UDP Ping Scan** | Send UDP packets to target host | Detects systems behind firewalls with strict TCP filtering |
| **ICMP ECHO Ping Scan** | Send ICMP echo requests (ping) | Simple, widely supported |
| **TCP Ping Scan** | Send TCP packets to specific ports | More stealthy than ICMP |

#### ARP Ping Scan

| Feature | Description |
|---------|-------------|
| **How it works** | ARP packets sent to discover active devices in IPv4 range |
| **Advantages** | More efficient and accurate than other techniques |
| **Benefits** | Shows MAC addresses, handles ARP requests automatically |
| **Use case** | System discovery, large address space scanning |

#### ICMP ECHO Ping Scan

| Feature | Description |
|---------|-------------|
| **How it works** | Sends ICMP echo requests to target hosts |
| **Response** | Active hosts displayed as "Host is up" |
| **Zenmap option** | `-PE` option for ICMP ECHO ping scan |

#### Ping Sweep Tools

| Tool | Features |
|------|----------|
| **Nmap** | `-sP` or `-sn` option for ping sweep |
| **fping** | Fast ping sweep utility |
| **Angry IP Scanner** | Graphical IP scanner |
| **Advanced IP Scanner** | Fast, friendly network scanner |

#### Ping Sweep Countermeasures

| Countermeasure | Description |
|----------------|-------------|
| **Block ICMP** | Block ICMP packets at firewall |
| **Rate Limiting** | Limit rate of ICMP responses |
| **Stealth Modes** | Use stealth scanning techniques |
| **Monitor Traffic** | Detect and alert on scanning activities |

---

### 4. Port and Service Discovery

#### Common Port Numbers

| Port | Protocol | Service |
|------|----------|---------|
| 20/21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 443 | TCP | HTTPS |
| 3306 | TCP | MySQL |
| 3389 | TCP | RDP |
| 5432 | TCP | PostgreSQL |

#### Port Number Groups

| Range | Type | Description |
|-------|------|-------------|
| 0-1023 | Well-known Ports | Standard services (HTTP, FTP, SSH) |
| 1024-49151 | Registered Ports | Registered for specific services |
| 49152-65535 | Dynamic/Private Ports | Temporary/ephemeral ports |

#### Port Scanning Techniques

| Technique | Description | Stealth Level |
|-----------|-------------|---------------|
| **TCP Connect/Full Open** | Completes 3-way handshake | Low - logged by system |
| **SYN Scan (Half-open)** | Sends SYN, receives SYN-ACK, sends RST | Medium - harder to detect |
| **FIN Scan** | Sends FIN packets | High - avoids logging |
| **NULL Scan** | Sends packets with no flags | High - avoids logging |
| **XMAS Scan** | Sends packets with FIN, URG, PSH flags | High - avoids logging |
| **UDP Scan** | Sends UDP packets to detect UDP services | Medium - slower, less reliable |

#### Inverse TCP Flag Scans

| Scan Type | Flags Set | Advantages | Disadvantages |
|-----------|-----------|------------|---------------|
| **NULL Scan** | None | Avoids IDS/logging | Needs raw socket access |
| **FIN Scan** | FIN only | Highly stealthy | Mostly effective against BSD-derived stacks |
| **XMAS Scan** | FIN, URG, PSH | Highly stealthy | Mostly effective against BSD-derived stacks |

#### UDP Scanning

| Feature | Description |
|---------|-------------|
| **How it works** | Sends UDP packets to target host |
| **Default port** | Nmap uses port 40,125 by default |
| **Advantage** | Detects systems behind firewalls with strict TCP filtering |
| **Disadvantage** | Provides port information only, requires privileged access |

#### Service Version Discovery

| Tool | Command | Description |
|------|---------|-------------|
| **Nmap** | `-sV` | Detect service versions |
| **Netcat** | Banner grabbing | Grab service banners |
| **Telnet** | Banner grabbing | Grab service banners |

#### Port Scanning Countermeasures

| Countermeasure | Description |
|----------------|-------------|
| **Close Unnecessary Ports** | Disable unused services |
| **Implement Firewalls** | Block scanning attempts |
| **Use IDS/IPS** | Detect and block port scans |
| **Port Knocking** | Require specific sequence of connections |
| **Rate Limiting** | Limit connection attempts |

---

### 5. OS Discovery (Banner Grabbing/OS Fingerprinting)

#### Banner Grabbing Techniques

| Technique | Description |
|-----------|-------------|
| **Active Banner Grabbing** | Send malformed packets, compare responses with database |
| **Passive Banner Grabbing** | Capture packets via sniffing, study telltale signs |

#### Why Banner Grabbing?

Allows attackers to:
- Identify OS used on target host
- Determine system vulnerabilities
- Select appropriate exploits
- Carry out further attacks

#### OS Discovery Tools

| Tool | Features |
|------|----------|
| **Nmap** | `-O` option for OS detection |
| **Unicornscan** | Advanced OS fingerprinting |
| **Xprobe2** | Remote OS detection |
| **p0f** | Passive OS fingerprinting |

#### Banner Grabbing Countermeasures

| Countermeasure | Description |
|----------------|-------------|
| **Disable Banners** | Remove service version information |
| **Modify Banners** | Display fake or generic information |
| **Use TCP Wrappers** | Control access to services |
| **Implement IDS** | Detect banner grabbing attempts |

---

### 6. Scanning Beyond IDS and Firewall

#### IDS/Firewall Evasion Techniques

| Technique | Description |
|-----------|-------------|
| **Packet Fragmentation** | Split probe packets into smaller fragments |
| **Source Routing** | Specify routing path for packets |
| **Source Port Manipulation** | Change source port to common ports |
| **IP Address Decoy** | Use decoy IP addresses |
| **IP Address Spoofing** | Change source IP address |
| **Custom Packets** | Send custom crafted packets |
| **Randomizing Host Order** | Scan hosts in random order |
| **Bad Checksums** | Send packets with bad checksums |
| **Proxy Servers** | Use chain of proxy servers |
| **Anonymizers** | Use anonymizing services |

#### Packet Fragmentation

| Feature | Description |
|---------|-------------|
| **How it works** | Split probe packet into smaller fragments |
| **IDS behavior** | IDS may skip fragmented packets during scans |
| **Tools** | Nmap, fragroute |
| **Result** | Fragments reassembled at destination host |

#### Proxy Servers and Chaining

| Feature | Description |
|---------|-------------|
| **Purpose** | Hide actual source of scan |
| **Proxy Chaining** | Use multiple proxies for increased anonymity |
| **Anonymity** | More proxies = greater anonymity |
| **Tools** | Proxychains, Tor |

#### Anonymizers

| Feature | Description |
|---------|-------------|
| **Purpose** | Bypass Internet censors, evade IDS/firewall |
| **Tools** | Tor, VPN services, anonymous proxy servers |

---

### 7. Draw Network Diagram

#### Network Diagram Tools

| Tool | Features |
|------|----------|
| **Nmap** | Network mapping and topology discovery |
| **Network Topology Mapper** | Automated network diagram creation |
| **SolarWinds Network Topology Mapper** | Comprehensive network mapping |
| **The Dude** | Network monitoring and mapping |

---

## Module 4: System Enumeration

### 1. Enumeration Concepts

#### What is Enumeration?

Enumeration is the process of extracting usernames, machine names, network resources, shares, and services from a system or network. It involves creating active connections with the system and sending directed queries to gain more information about the target.

#### Enumeration Objectives

| Objective | Description |
|-----------|-------------|
| **Extract Usernames** | Get valid usernames for password attacks |
| **Identify Network Resources** | Find shared resources, printers, and services |
| **Discover Services** | Identify running services and their versions |
| **Find Vulnerabilities** | Identify security weaknesses for exploitation |

#### Enumeration Techniques

| Technique | Description |
|-----------|-------------|
| **Extract Usernames from Email IDs** | Parse email addresses (username@domain) |
| **Default Passwords** | Use manufacturer default passwords |
| **Brute Force Active Directory** | Enumerate valid usernames via logon hours feature |
| **DNS Zone Transfer** | Extract DNS names and IP addresses |
| **Extract User Groups** | Get Windows Active Directory group information |
| **SNMP Enumeration** | Extract usernames via SNMP community strings |

---

### 2. NetBIOS Enumeration

#### NetBIOS Information

| Feature | Description |
|---------|-------------|
| **What is NetBIOS** | API for client software to access LAN resources |
| **Windows Use** | File and printer sharing |
| **Ports Used** | UDP 137 (name services), UDP 138 (datagram), TCP 139 (session) |
| **Why Targeted** | Easy to exploit, runs on Windows systems even when not in use |

#### NetBIOS Enumeration Information

| Information | Description |
|-------------|-------------|
| **List of Computers** | Computers belonging to a domain |
| **List of Shares** | Shares on individual hosts in network |
| **Policies and Passwords** | Security policies and password policies |

#### NetBIOS Enumeration Tools

| Tool | Features |
|------|----------|
| **nbtstat** | Windows NetBIOS information utility |
| **Nbtscan** | NetBIOS information scanner |
| **SuperScan** | Network scanner with NetBIOS enumeration |
| **Legion** | NetBIOS and SMB enumeration tool |

#### nbtstat Commands

| Command | Description |
|---------|-------------|
| `nbtstat -A <IP>` | Display NetBIOS name table for remote computer |
| `nbtstat -n` | Display local NetBIOS name table |
| `nbtstat -c` | Display contents of NetBIOS name cache |
| `nbtstat -r` | Display NetBIOS name resolution statistics |

---

### 3. SNMP Enumeration

#### SNMP Components

| Component | Description |
|-----------|-------------|
| **SNMP Manager** | System that manages SNMP agents |
| **SNMP Agent** | Software on managed device |
| **MIB** | Management Information Base - virtual database |
| **Commands** | GetRequest, GetNextRequest, GetResponse, SetRequest, Trap |

#### SNMP Commands

| Command | Description |
|---------|-------------|
| **GetRequest** | Manager requests information from agent |
| **GetNextRequest** | Manager retrieves data from array/table |
| **GetResponse** | Agent satisfies manager's request |
| **SetRequest** | Manager modifies parameter value |
| **Trap** | Agent informs manager of event |

#### SNMP Enumeration Tools

| Tool | Features |
|------|----------|
| **Snmpwalk** | SNMP MIB tree walker |
| **Snmpget** | Get SNMP information |
| **SolarWinds SNMP Tool** | Comprehensive SNMP management |
| **Paessler SNMP Tester** | SNMP testing tool |

---

### 4. LDAP Enumeration

#### LDAP Information

| Feature | Description |
|---------|-------------|
| **What is LDAP** | Lightweight Directory Access Protocol |
| **Purpose** | Access and maintain distributed directory services |
| **Default Port** | TCP 389 (LDAP), TCP 636 (LDAPS) |
| **Information Gathered** | User accounts, groups, organizational units |

#### LDAP Enumeration Tools

| Tool | Features |
|------|----------|
| **ldapsearch** | Command-line LDAP search |
| **ADExplorer** | Active Directory explorer |
| **Softerra LDAP Browser** | LDAP directory browser |
| **JXplorer** | LDAP browser and editor |

---

### 5. NTP and NFS Enumeration

#### NTP Enumeration

| Feature | Description |
|---------|-------------|
| **What is NTP** | Network Time Protocol |
| **Purpose** | Synchronize computer clocks |
| **Default Port** | UDP 123 |
| **Information Gathered** | Network information, connected clients |

#### NTP Enumeration Commands

| Command | Description |
|---------|-------------|
| `ntpdc -c monlist <IP>` | Get monitor list |
| `ntpq -p <IP>` | Query NTP peers |

#### NFS Enumeration

| Feature | Description |
|---------|-------------|
| **What is NFS** | Network File System |
| **Purpose** | Remote file access and management |
| **Default Port** | TCP 2049 |
| **Information Gathered** | List of clients, exported directories |

#### NFS Enumeration Tools

| Tool | Features |
|------|----------|
| **showmount** | Show NFS exports |
| **rpcinfo** | Show RPC information |
| **Nmap** | NFS enumeration scripts |

---

### 6. SMTP and DNS Enumeration

#### SMTP Enumeration

| Feature | Description |
|---------|-------------|
| **What is SMTP** | Simple Mail Transfer Protocol |
| **Purpose** | Email transmission |
| **Default Ports** | TCP 25, 2525, 587 |
| **Commands** | VRFY, EXPN, RCPT TO |

#### SMTP Enumeration Commands

| Command | Description |
|---------|-------------|
| **VRFY** | Verify if a username exists |
| **EXPN** | Expand mailing list |
| **RCPT TO** | Check recipient address |

#### SMTP Enumeration Tools

| Tool | Features |
|------|----------|
| **Telnet** | Manual SMTP enumeration |
| **Netcat** | SMTP enumeration |
| **SWAKS** | SMTP with authentication |

#### DNS Enumeration Using Zone Transfer

| Feature | Description |
|---------|-------------|
| **What is Zone Transfer** | Transfer DNS zone file from primary to secondary server |
| **Purpose** | Replicate DNS data across servers |
| **Vulnerability** | If misconfigured, allows attacker to get entire DNS zone |
| **Tools** | dig, nslookup, recon |

#### Services and Ports to Enumerate

| Port | Protocol | Service | Vulnerability |
|------|----------|---------|---------------|
| 53 | TCP/UDP | DNS | Zone transfer, DNS exploits |
| 135 | TCP | Microsoft RPC Endpoint Mapper | DoS attacks |
| 500 | UDP | ISAKMP/IKE | VPN vulnerabilities |
| 20/21 | TCP | FTP | Brute force, traffic sniffing |
| 69 | UDP | TFTP | Malware installation |
| 179 | TCP | BGP | Routing attacks |
| 22 | TCP | SSH | Brute force, port forwarding |
| 23 | TCP | Telnet | Banner grabbing, brute force |

---

### 7. Enumeration Countermeasures

| Countermeasure | Description |
|----------------|-------------|
| **Disable NetBIOS** | Disable NetBIOS if not needed |
| **Configure SNMP Properly** | Use strong community strings, restrict access |
| **Secure LDAP** | Use LDAPS, restrict anonymous access |
| **Configure NFS Properly** | Restrict exports, use authentication |
| **Secure SMTP** | Disable VRFY/EXPN, use authentication |
| **Restrict Zone Transfer** | Allow only authorized servers |
| **Monitor Enumeration** | Detect and alert on enumeration attempts |
| **Educate Users** | Train on password security |

---

## Module 5: Vulnerability Analysis

### 1. Vulnerability Analysis Concepts

#### What is Vulnerability Research?

The process of discovering, analyzing, and documenting security vulnerabilities in software, hardware, and systems.

#### Resources for Vulnerability Research

| Resource | Purpose |
|----------|---------|
| **Microsoft Vulnerability Research (MSVR)** | Microsoft security updates |
| **Exploit Database** | Public exploit database |
| **CVE (Common Vulnerabilities and Exposures)** | Standardized vulnerability identification |
| **CWE (Common Weakness Enumeration)** | Common software weaknesses |
| **NVD (National Vulnerability Database)** | Vulnerability database |
| **SecurityFocus** | Security news and advisories |
| **Dark Reading** | Security news and analysis |

#### What is Vulnerability Assessment?

A systematic examination of a system's ability to withstand assault, identifying, measuring, and classifying security vulnerabilities.

#### Vulnerability Scoring Systems

| System | Description |
|---------|-------------|
| **CVSS (Common Vulnerability Scoring System)** | Industry standard for vulnerability scoring (0-10) |
| **CVE (Common Vulnerabilities and Exposures)** | Standardized identification system |
| **CWE (Common Weakness Enumeration)** | Standardized weakness categorization |
| **OWASP Risk Rating** | Web application risk assessment |

---

### 2. Vulnerability Management Life Cycle

| Phase | Description | Activities |
|-------|-------------|------------|
| **1. Identify Assets and Create Baseline** | Identify critical assets and prioritize | Gather system information, create baseline |
| **2. Vulnerability Scan** | Perform scans to identify vulnerabilities | Network scans, compliance template scans |
| **3. Risk Assessment** | Assess and prioritize risks | Determine risk level (high, moderate, low) |
| **4. Remediation** | Apply fixes to vulnerable systems | Patch, configure, update |
| **5. Verification** | Re-scan to verify remediation | Ticketing systems, scanners, reports |
| **6. Monitor** | Continuous monitoring for new vulnerabilities | IDS/IPS, firewalls, continuous scanning |

---

### 3. Vulnerability Classification and Assessment Types

#### Vulnerabilities Classification

| Type | Description |
|------|-------------|
| **Operating System Vulnerabilities** | Weaknesses in OS |
| **Application Vulnerabilities** | Weaknesses in applications |
| **Network Vulnerabilities** | Weaknesses in network protocols/services |
| **Configuration Vulnerabilities** | Misconfigurations |
| **Human Vulnerabilities** | Social engineering, user errors |

#### Types of Vulnerability Assessment

| Type | Description | Example |
|------|-------------|---------|
| **Active Assessment** | Uses network scanners | Nmap, Nessus |
| **Passive Assessment** | Sniffs network traffic | Wireshark, passive scanners |
| **External Assessment** | Examines network from outside | External vulnerability scan |
| **Internal Assessment** | Examines internal network | Internal vulnerability scan |
| **Host-based Assessment** | Configuration-level checks | Local vulnerability scanners |
| **Network-based Assessment** | Network security assessment | Network vulnerability scanners |
| **Application Assessment** | Web application testing | OWASP ZAP, Burp Suite |
| **Database Assessment** | Database security testing | Database scanners |
| **Wireless Network Assessment** | Wireless security testing | Wireless scanners |
| **Distributed Assessment** | Multi-location assessment | Coordinated scans |
| **Credentialed Assessment** | Authenticated assessment | Login-based scanning |
| **Non-Credentialed Assessment** | Unauthenticated assessment | External-only scanning |
| **Manual Assessment** | Manual research and ranking | Manual analysis |
| **Automated Assessment** | Uses automated tools | Nessus, Qualys |

---

### 4. Vulnerability Assessment Tools

| Tool | Type | Features |
|------|------|----------|
| **Nessus Professional** | Commercial | Comprehensive vulnerability scanning |
| **Qualys Vulnerability Management** | Commercial | Cloud-based vulnerability management |
| **GFI LanGuard** | Commercial | Network security scanning |
| **OpenVAS** | Open Source | Vulnerability scanning and management |
| **Nikto** | Open Source | Web server scanner |
| **OWASP ZAP** | Open Source | Web application security scanner |
| **Burp Suite** | Commercial | Web application security testing |
| **Acunetix** | Commercial | Web vulnerability scanner |
| **Retina** | Commercial | Network security scanning |
| **Languard Network Security Scanner** | Commercial | Network vulnerability scanning |

---

### 5. Vulnerability Assessment Reports

| Report Type | Content |
|-------------|---------|
| **Security Vulnerability Report** | Detailed vulnerability information |
| **Security Vulnerability Summary** | High-level summary of findings |
| **Executive Summary** | Business-focused summary |
| **Technical Details** | Technical vulnerability details |
| **Remediation Recommendations** | Steps to fix vulnerabilities |

---

## Module 6: System Hacking

### 1. System Hacking Concepts

#### CEH Hacking Methodology

| Phase | Description |
|-------|-------------|
| **1. Footprinting** | Accumulating data about network environment |
| **2. Scanning** | Identifying active hosts, open ports, services |
| **3. Enumeration** | Gathering user lists, routing tables, security flaws |
| **4. Vulnerability Analysis** | Examining system ability to withstand assault |
| **5. System Hacking** | Gaining access, escalating privileges, maintaining access |

#### System Hacking Goals

| Goal | Description |
|------|-------------|
| **Gain Access** | Obtain unauthorized access to target system |
| **Escalate Privileges** | Gain higher-level privileges |
| **Maintain Access** | Establish persistence on compromised system |
| **Clear Tracks** | Remove evidence of compromise |

---

### 2. Gaining Access

#### Techniques for Gaining Access

| Technique | Description |
|-----------|-------------|
| **Password Cracking** | Crack passwords using various methods |
| **Buffer Overflow** | Exploit buffer overflow vulnerabilities |
| **Vulnerability Exploitation** | Exploit known vulnerabilities |

#### Microsoft Authentication

| Type | Description |
|------|-------------|
| **NTLM Authentication** | Default authentication using challenge/response |
| **Kerberos Authentication** | Strong authentication using secret-key cryptography |

#### Security Accounts Manager (SAM) Database

| Feature | Description |
|---------|-------------|
| **Purpose** | Manage user accounts and passwords in hashed format |
| **Storage** | Registry file with exclusive filesystem lock |
| **Security** | Passwords stored in hashed format, not plaintext |
| **SYSKEY** | Partially encrypts password hashes (Windows NT 4.0+) |

#### Password Cracking Types

| Type | Description |
|------|-------------|
| **Dictionary Attack** | Use dictionary of common passwords |
| **Brute Force Attack** | Try all possible combinations |
| **Rainbow Table Attack** | Use pre-computed hash tables |
| **Hybrid Attack** | Combination of dictionary and brute force |

#### Password Recovery Tools

| Tool | Features |
|------|----------|
| **Ophcrack** | Rainbow table-based password cracker |
| **John the Ripper** | Fast password cracker |
| **Hashcat** | GPU-accelerated password recovery |
| **Cain & Abel** | Windows password recovery tool |

#### Tools to Extract Password Hashes

| Tool | Features |
|------|----------|
| **Pwdump** | Extract password hashes from Windows SAM |
| **FGDump** | Extract password hashes and LSA secrets |
| **Mimikatz** | Extract passwords and hashes from memory |
| **LaZagne** | Retrieve passwords from various applications |

---

### 3. Escalating Privileges

#### Types of Privilege Escalation

| Type | Description | Example |
|------|-------------|---------|
| **Horizontal Privilege Escalation** | Access resources of user with similar permissions | User A accesses User B's bank account |
| **Vertical Privilege Escalation** | Access resources of user with higher privileges | Standard user accesses admin functions |

#### Privilege Escalation Tools

| Tool | Features |
|------|----------|
| **Metasploit** | Privilege escalation modules |
| **Windows Exploit Suggester** | Suggest Windows exploits |
| **LinPEAS** | Linux privilege escalation audit |
| **WinPEAS** | Windows privilege escalation audit |

---

### 4. Maintaining Access

#### Techniques for Maintaining Access

| Technique | Description |
|-----------|-------------|
| **Backdoors** | Install backdoor for remote access |
| **Rootkits** | Install rootkit to hide presence |
| **Steganography** | Hide malicious files |
| **NTFS Data Stream (ADS)** | Hide files in alternate data streams |

#### Types of Rootkits

| Type | Description |
|------|-------------|
| **Kernel-mode Rootkits** | Operate at kernel level |
| **User-mode Rootkits** | Operate at user level |
| **Bootkit** | Infect master boot record |
| **Firmware Rootkits** | Infect system firmware |

---

### 5. Covering Tracks

#### Techniques for Covering Tracks

| Technique | Description |
|-----------|-------------|
| **Disabling Auditing** | Disable system auditing features |
| **Clearing Logs** | Delete system log entries |
| **Manipulating Logs** | Modify logs to hide activities |
| **Deleting Files** | Securely delete files |
| **Disabling Windows Functionality** | Disable timestamps, hibernation, restore points |

#### Log Files

| Log File | Content |
|----------|---------|
| **SECEVENT.EVT** | Failed logins, unauthorized file access |
| **SYSEVENT.EVT** | Driver failures, system errors |
| **APPEVENT.EVT** | Application errors |

#### Tools for Clearing Logs

| Tool | Features |
|------|----------|
| **Clear_Event_Viewer_Logs.bat** | Clear Windows event logs |
| **Meterpreter clearev** | Clear logs via Meterpreter |
| **PowerShell wevtutil** | Clear logs via PowerShell |
| **Cipher.exe** | Securely delete data |

---

### 6. Metasploit Framework

#### What is Metasploit?

A penetration testing toolkit, exploit development platform, and research tool that includes hundreds of working remote exploits.

#### Why Metasploit?

- Complete framework providing infrastructure for automated tasks
- Allows ethical hackers to easily build attack vectors
- Supports automated exploitation using known vulnerabilities

#### Metasploit Architecture

| Component | Description |
|-----------|-------------|
| **Payloads** | Code run on target system (meterpreter, command shell) |
| **Exploits** | Organized for target system (android, linux, windows, openbsd) |
| **Encoders** | Encode exploit to bypass signature-based antivirus |
| **Auxiliary** | Supporting modules (scanners, crawlers, fuzzers) |
| **Post-Modules** | Post-exploitation (gather information, escalate privileges) |

#### Metasploit Interfaces

| Interface | Type | Description |
|-----------|------|-------------|
| **Msfconsole** | Command-line interactive | Main interface |
| **Msfcli** | Command-line non-interactive | Scripting interface |
| **Armitage** | GUI | Graphical interface for Metasploit |

#### Armitage

- Scriptable tool for Metasploit
- Visualizes targets
- Recommends exploits
- Exposes advanced post-exploitation features

---

## Module 7: Introduction to Incident Response and Digital Forensics

### 1. Incident Response Concepts

#### What is Incident Response?

The approach to managing any security incidents or breach that detects, responds, and recovers from security incidents in a structured and organized manner.

#### Incident Response Goals

| Goal | Description |
|------|-------------|
| **Minimize Damage** | Reduce impact of security incident |
| **Reduce Recovery Time** | Restore normal operations quickly |
| **Restore Operations** | Get systems back to normal functioning |

#### Related Terms

| Term | Definition |
|------|------------|
| **Incident** | Any anomaly that violates an organization's security policy |
| **Anomaly** | Something different, abnormal, or peculiar |
| **Forensics** | Application of scientific knowledge to legal problems |
| **Computer Forensics** | Application of scientific knowledge to legal problems involving computer-related evidence |

---

### 2. Incident Response Team Elements

#### Main Elements of IRT

| Role | Responsibilities |
|------|------------------|
| **Director** | Senior management, authority to carry out IR activities, reports to top management |
| **Lead Investigator** | Ensures activities executed correctly, prepares incident report, interfaces with law enforcement |
| **Forensic Technicians** | Carry out IR tasks, analyze evidence, report findings |
| **Response Handler (1st Responder)** | First on scene, secures crime scene, collects evidence |
| **Evidence Handler** | Protects evidence, maintains chain of custody |
| **Legal Advisor** | Provides legal guidance, helps decide legal action |
| **Dispatchers** | Manages incident hotline, receives calls, assigns tracking numbers |

---

### 3. Incident Response Life Cycle

#### Phase 1: Preparation

| Activity | Description |
|----------|-------------|
| **Form Strategy** | Create incident response strategy |
| **Design Procedure** | Develop procedures for incident handling |
| **Gather Resources** | Collect tools and resources |
| **Practice** | Regular training and drills |
| **Set Security Control** | Implement security controls |
| **Risk Assessment** | Perform risk assessments |

#### Preparation Resources

| Resource Type | Examples |
|---------------|----------|
| **Incident Handler Communications** | Contact info, on-call info, issue tracking system, smartphones |
| **Incident Analysis Hardware** | Forensic workstation, backup devices, laptops |
| **Incident Analysis Resources** | Cryptography hashes, baselines |
| **Incident Mitigation Software** | Clean OS for restoration |

#### Phase 2: Detection and Analysis

| Activity | Description |
|----------|-------------|
| **Identify Incidents** | Detect security incidents |
| **Analyze Incidents** | Analyze and validate incidents |
| **Categorize Incidents** | Classify incidents by type and severity |
| **Prioritize Incidents** | Prioritize based on impact |

#### Common Attack Vectors

| Vector | Description |
|--------|-------------|
| **External/Removable Media** | USB flash drives, peripherals |
| **Web** | Websites, web-based applications |
| **Email** | Email messages, attachments |
| **Impersonation** | Spoofing, man-in-the-middle, rogue wireless access points |
| **Loss or Theft** | Loss or theft of equipment |
| **Improper Usage** | Violation of acceptable usage policies |

#### Signs of an Incident

| Type | Description | Examples |
|------|-------------|----------|
| **Precursors** | Signs that an incident may occur | Vulnerability scanner usage, new exploit announcements, threat notifications |
| **Indicators** | Signs that an incident has occurred | Antivirus alerts, IDS alerts, unusual system behavior |

#### Incident Analysis Recommendations

| Recommendation | Description |
|----------------|-------------|
| **Profile Networks and Systems** | Understand normal network and system behavior |
| **Create Log Retention Policy** | Establish log retention policies |
| **Perform Event Correlation** | Correlate events from multiple sources |
| **Keep Host Clocks Synchronized** | Ensure accurate timestamps |
| **Maintain Knowledge Base** | Maintain incident information database |
| **Run Packet Sniffers** | Collect additional network data |
| **Filter Data** | Filter data to identify relevant information |

#### Phase 3: Containment, Eradication, and Recovery

| Phase | Activities |
|-------|------------|
| **Containment** | Prevent spread, choose containment strategy |
| **Evidence Gathering** | Collect and preserve evidence |
| **Identify Attacking Hosts** | Research attacking hosts |
| **Eradication** | Remove malware, disable accounts, mitigate vulnerabilities |
| **Recovery** | Restore systems, confirm functionality, remediate vulnerabilities |

#### Choosing Containment Strategy

| Criteria | Considerations |
|----------|----------------|
| **Potential Damage** | Potential damage to and theft of resources |
| **Evidence Preservation** | Need for evidence preservation |
| **Service Availability** | Impact on service availability |
| **Time and Resources** | Time and resources needed |
| **Effectiveness** | Effectiveness of the strategy |

#### Phase 4: Post-Incident Activities

| Activity | Description |
|----------|-------------|
| **Lessons Learned** | Analyze what happened, how well staff performed, what can be improved |
| **Questions to Answer** | What happened? How well did staff perform? What information was needed? What corrective actions can prevent similar incidents? |

---

### 4. Digital Forensics

#### What is Digital Forensics?

A branch of forensic science encompassing the recovery and investigation of material found in digital devices.

#### Digital Forensic Goals

| Goal | Question Answered |
|------|-------------------|
| **What happened** | What happened to the system? |
| **How** | How was it compromised? |
| **Who** | Who is the attacker? |
| **When** | When did it happen? |
| **Where** | Where did it happen? |
| **Why** | Why did it happen? |

#### Analysis Approaches

| Approach | Description |
|----------|-------------|
| **Live Analysis** | Analyze system while it's running |
| **Dead Analysis** | Analyze powered-off system |
| **Hybrid Analysis** | Combination of live and dead analysis |

#### Digital Forensic Process

| Phase | Description |
|-------|-------------|
| **Acquisition** | Collect digital evidence |
| **Analysis** | Analyze evidence |
| **Documentation** | Document findings |
| **Presentation** | Present findings |

---

## Module 8: Memory Acquisition and Analysis

### 1. Memory Acquisition

#### What is Memory Acquisition?

Copying the contents of volatile memory to non-volatile storage for forensic analysis.

#### Memory Acquisition Formats

| Format | Extension | Description | Tool |
|--------|-----------|-------------|------|
| **RAW Format** | .raw, .bin, .dd | Raw memory dump | FTK imager, WinPMEM |
| **Hibernation File** | hiberfil.sys | Windows hibernation file | Volatility |
| **Page File** | pagefile.sys | Windows page file | Moonsols, Rekall |
| **VMware Snapshot** | .vmsn, .vmem | VMware virtual machine snapshot | VMware |
| **Crash Dump** | .dmp | Windows crash dump | Windows |

---

### 2. Memory Structure

#### Memory Components

| Component | Description |
|-----------|-------------|
| **Process** | Instance of a program executed in system |
| **Process Metadata** | Process name, executable path, parent process, start time |
| **User Mode** | Application processes, cannot modify paging |
| **Kernel Mode** | System-level operations, sets up memory space |

#### Why Memory Forensics?

Memory can contain valuable evidence:
- Running processes
- Executed console commands
- Passwords in clear text
- Unencrypted data
- Instant messages
- IP addresses
- Trojan horses

---

### 3. Memory Analysis Tools

| Tool | Features |
|------|----------|
| **Memoryze** | Memory acquisition and analysis |
| **Redline** | Memory analysis by Mandiant |
| **Volatility Framework** | Free memory forensics framework |

#### Volatility Framework

- Free memory forensics framework
- Supports Windows, Mac, and Linux
- Works with plugins for specific tasks
- Each plugin performs specific task with memory dump

#### Volatility Plugins

| Plugin | Description | Usage |
|--------|-------------|-------|
| **imageinfo** | Identify OS, service pack, architecture | `vol.py -f <ImageFile> imageinfo` |
| **kdbgscan** | Identify correct profile and KDBG address | `vol.py -f <ImageFile> --profile=<profile> kdbgscan` |
| **pslist** | List processes | `vol.py -f <ImageFile> --profile=<profile> pslist` |
| **pstree** | List processes in tree view | `vol.py -f <ImageFile> --profile=<profile> pstree` |
| **psscan** | List all processes (active, terminated, hidden) | `vol.py -f <ImageFile> --profile=<profile> psscan` |
| **psxview** | Compare different process-viewing techniques | `vol.py -f <ImageFile> --profile=<profile> psxview` |
| **handles** | Review process handles | `vol.py -f <ImageFile> --profile=<profile> handles -p <PID>` |
| **filescan** | Scan for file objects | `vol.py -f <ImageFile> --profile=<profile> filescan` |
| **procexedump** | Dump process executable | `vol.py -f <ImageFile> --profile=<profile> procexedump -p <PID>` |
| **memdump** | Dump process memory | `vol.py -f <ImageFile> --profile=<profile> memdump -p <PID>` |
| **connections** | Display TCP connections (XP/2003 only) | `vol.py -f <ImageFile> --profile=<profile> connections` |
| **connscan** | Scan for connections (including terminated) | `vol.py -f <ImageFile> --profile=<profile> connscan` |
| **netscan** | Check network traces (Vista+) | `vol.py -f <ImageFile> --profile=<profile> netscan` |

---

## Module 9: Data Hiding and Steganography

### 1. Data Hiding Methods

| Method | Description |
|--------|-------------|
| **Encryption** | Cryptographically protect data |
| **Password Protection** | Protect with passwords |
| **File Attributes Manipulation** | Hide using file attributes |
| **Alternate Data Streams (ADS)** | Hide in NTFS alternate streams |
| **Metadata Hiding** | Hide in file metadata |
| **Covert Channel** | Hidden communication channel |

---

### 2. Steganography

#### What is Steganography?

The art and science of hidden communication - hiding data in plain view in pictures, graphics, or text without revealing its existence.

#### Steganography History

| Technique | Description |
|-----------|-------------|
| **Wax Tablets** | Secret message covered with wax (Ancient Greece) |
| **Invisible Ink** | Messages written with invisible ink (WWII) |
| **Null Cipher** | Messages hidden in normal text |

#### Types of Steganography

| Type | Description |
|------|-------------|
| **Image** | Hide message behind image |
| **Audio** | Hide message in audio file |
| **Text** | Hide text in text file (ADS) |
| **Email** | Encode in email content |
| **Whitespace** | Hide in whitespace of text |

#### Least Significant Bit (LSB) Replacement

| Feature | Description |
|---------|-------------|
| **Concept** | Replace rightmost bit (LSB) of each byte |
| **Method** | Binary data of message inserted into LSB of each pixel |
| **Advantage** | Little change to overall file |
| **Principle** | Similar to lossy compression |

#### Steganography Tools

| Tool | Type | Features |
|------|------|----------|
| **Steghide** | Image/Audio | Hides data in JPEG, BMP, WAV, AU |
| **Quickstego** | Image | Simple image steganography |
| **MP3Stegz** | Audio | Hides data in MP3 files |
| **SNOW** | Text | Hides data in whitespace |
| **Crypture** | General | File encryption and hiding |
| **Xiao Steganography** | Image | Image steganography |

---

### 3. File Attributes Manipulation

#### Common File Attributes (Windows)

| Attribute | Description |
|-----------|-------------|
| **Read-only (R)** | File cannot be modified |
| **Hidden (H)** | File not displayed in directory listings |
| **System (S)** | System file |
| **Archive (A)** | File marked for backup |

#### File Attributes Commands

| Command | Description |
|---------|-------------|
| `attrib +h +s file.txt` | Set file as hidden and system |
| `attrib -h -s file.txt` | Remove hidden and system attributes |
| `attrib file.txt` | View file attributes |

---

### 4. File Signature Manipulation

#### What is File Signature?

A specific sequence of bytes at the beginning of a file that identifies its format (also called magic number or file header).

#### File Signature Manipulation

| Action | Description |
|--------|-------------|
| **Alter Magic Number** | Change file signature to mimic another format |
| **Change Extension** | Change file extension to match faked signature |
| **Hide Executable** | Hide executable as image or other file type |

#### Detection Tools

| Tool | Features |
|------|----------|
| **TrID** | Detect file types based on content |
| **Binwalk** | Firmware or deep binary analysis |
| **Autopsy** | Forensic suite |
| **FTK** | Forensic toolkit |
| **EnCase** | Forensic software |
| **file (Linux)** | Uses magic numbers to identify files |

---

### 5. Alternate Data Streams (ADS)

#### What is ADS?

A feature of NTFS that allows a file to contain more than one stream of data - main content and hidden alternate streams.

#### ADS Characteristics

| Feature | Description |
|---------|-------------|
| **Visibility** | Not visible in File Explorer or command prompt |
| **Usage** | Perfect for hiding data, malware, or backdoors |
| **Example** | `normal.txt:hidden.txt` |

#### ADS Uses

| Use Type | Description |
|----------|-------------|
| **Legitimate** | Metadata storage, Mac resource fork compatibility |
| **Malicious** | Hiding malware, backdoors, data |

---

### 6. Metadata Hiding

#### What is Metadata?

"Data about data" - information that describes or gives context to actual file content.

#### Common File Types with Metadata

| File Type | Metadata Examples |
|-----------|-------------------|
| **Images** | Camera info, GPS location, date/time |
| **Documents** | Author, revision history, comments |
| **Audio** | Artist, album, year, genre |
| **Video** | Duration, codec, resolution |

#### Metadata Manipulation

| Tool | Features |
|------|----------|
| **ExifTool** | Read/write metadata |
| **Metagoofil** | Metadata extraction |
| **FOCA** | Metadata analysis |

---

### 7. Covert Channel

#### What is Covert Channel?

A type of computer security attack that creates a capability to transfer information between processes that are not supposed to communicate by the computer security policy.

#### Covert Channel Example

| Scenario | Description |
|----------|-------------|
| **Alice (TOP SECRET)** | Creates file to signal "1", removes to signal "0" |
| **Bob (CONFIDENTIAL)** | Checks file every minute |
| **Result** | Alice can leak TOP SECRET info to Bob! |

#### Covert Channel Conditions

| Condition | Description |
|-----------|-------------|
| **Shared Resource** | Sender and receiver have shared resource |
| **Observable Property** | Sender can vary property that receiver can observe |
| **Synchronization** | Communication can be synchronized |

---

## Module 10: Cryptography

### 1. Cryptography Concepts

#### Objectives of Cryptography

| Objective | Description |
|-----------|-------------|
| **Confidentiality** | Assurance information is accessible only to authorized users |
| **Integrity** | Trustworthiness of data - preventing improper changes |
| **Authentication** | Assurance communication is genuine |
| **Non-repudiation** | Guarantee sender cannot deny sending, recipient cannot deny receiving |

---

### 2. Types of Cryptography

| Type | Description | Key Usage |
|------|-------------|-----------|
| **Symmetric Encryption** | Same key for encryption and decryption | Single shared key |
| **Asymmetric Encryption** | Different keys for encryption and decryption | Public and private key pair |

#### Strengths and Weaknesses

| Type | Strengths | Weaknesses |
|------|-----------|------------|
| **Symmetric** | Fast, efficient for large data | Key distribution problem |
| **Asymmetric** | Solves key distribution problem | Slower, computationally expensive |

---

### 3. Ciphers

#### Ciphers Classification

| Classification | Type | Examples |
|----------------|------|----------|
| **Based on Key** | Symmetric-key | DES, AES, IDEA |
| | Asymmetric-key | RSA, Diffie-Hellman, El Gamal |
| **Based on Input** | Block cipher | DES, AES, IDEA |
| | Stream cipher | RC4, SEAL |

#### Modern Ciphers

| Cipher | Type | Features |
|--------|------|----------|
| **DES** | Block cipher | 56-bit key, now considered weak |
| **AES** | Block cipher | 128/192/256-bit keys, current standard |
| **RC4** | Stream cipher | Fast, but has vulnerabilities |
| **RC5/RC6** | Block cipher | Variable block size, key size |

#### Asymmetric Ciphers

| Cipher | Features |
|--------|----------|
| **RSA** | Public-key cryptosystem, based on factoring large primes |
| **Diffie-Hellman** | Key exchange protocol, allows secure key exchange |
| **DSA** | Digital Signature Algorithm, for digital signatures |
| **El Gamal** | Public-key cryptosystem, based on discrete logarithm |

---

### 4. Hash Functions

#### Message Digest (One-way Hash)

| Function | Features |
|----------|----------|
| **MD5** | 128-bit hash, now considered weak |
| **SHA-1** | 160-bit hash, now considered weak |
| **SHA-2** | 224/256/384/512-bit hash, current standard |

#### Hash Function Properties

| Property | Description |
|----------|-------------|
| **One-way** | Cannot reverse hash to original message |
| **Collision-resistant** | Difficult to find two messages with same hash |
| **Pre-image resistant** | Difficult to find message from hash |
| **Fixed output** | Always produces fixed-length output |

---
