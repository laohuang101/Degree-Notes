# System and Network Administration (112025-MGR) - Complete Study Guide

## Table of Contents

- [Main Quiz Questions](#main-quiz-questions)
- [Chapter 1: Linux Fundamentals](#chapter-1-linux-fundamentals)
- [Chapter 2: Virtualization](#chapter-2-virtualization)
- [Chapter 3: Storage and File Systems](#chapter-3-storage-and-file-systems)
- [Chapter 4: OSI Model and Networking](#chapter-4-osi-model-and-networking)
- [Chapter 5: DHCP and DNS](#chapter-5-dhcp-and-dns)
- [Chapter 6: Email Systems](#chapter-6-email-systems)
- [Chapter 7: LDAP and Authentication](#chapter-7-ldap-and-authentication)
- [Chapter 8: Cryptography Basics](#chapter-8-cryptography-basics)

---

## Main Quiz Questions

### Question 1: DNS Record Types
**Question:** Which of the following DNS record types is used to define mail servers for a domain?

| Option | Answer |
|--------|--------|
| A. MX | ✅ **Correct** |
| B. NS | Incorrect |
| C. CNAME | Incorrect |
| D. A | Incorrect |

**Explanation:** MX (Mail Exchange) records specifically define the mail servers responsible for accepting email messages on behalf of a domain name. NS records define name servers, CNAME records define aliases, and A records map hostnames to IPv4 addresses.

---

### Question 2: Email Reading Protocols
**Question:** Which of the following protocols are used to read emails from a server?

- i. SMTP
- ii. POP3
- iii. IMAP
- iv. MSA

| Option | Answer |
|--------|--------|
| A. i, ii, and iii | Incorrect |
| B. i and iii | Incorrect |
| C. i and ii | Incorrect |
| D. ii and iii | ✅ **Correct** |

**Explanation:** POP3 (Post Office Protocol version 3) and IMAP (Internet Message Access Protocol) are both used for retrieving email messages from a mail server. SMTP (Simple Mail Transfer Protocol) and MSA (Mail Submission Agent) are used for sending emails, not reading them.

---

### Question 3: Linux Bootloader Purpose
**Question:** What is the primary purpose of the Linux bootloader?

| Option | Answer |
|--------|--------|
| A. To load the Linux kernel into memory | ✅ **Correct** |
| B. To manage user authentication | Incorrect |
| C. To start the init process | Incorrect |
| D. To provide a graphical user interface | Incorrect |

**Explanation:** The bootloader (such as GRUB) is responsible for loading the Linux kernel into memory and handing over control to it. The init process starts after the kernel loads, and user authentication is handled by system services like PAM.

---

### Question 4: File Write Permission Issue
**Question:** A user reports that they are unable to write to a file named report.txt on a Linux system, despite the file showing that it exists when listing files with ls. What could be the most likely cause of this issue?

| Option | Answer |
|--------|--------|
| A. The file report.txt is a directory, not a file | Incorrect |
| B. The disk containing report.txt is full | Incorrect |
| C. The group does not have write permissions on report.txt | Incorrect |
| D. The user does not have write permissions on report.txt | ✅ **Correct** |

**Explanation:** The most likely cause is that the user lacks write permissions on the file. In Linux, file permissions are controlled at the user, group, and other levels. Even if the file exists, without write permission, the user cannot modify it.

---

### Question 5: Syslog Configuration
**Question:** What does the configuration line `mail.info /var/log/maillog` mean?

| Option | Answer |
|--------|--------|
| A. All mail logs are ignored | Incorrect |
| B. Mail logs are sent to a remote server | Incorrect |
| C. Informational and higher-priority mail logs go to /var/log/maillog | ✅ **Correct** |
| D. Only error-level mail logs are stored | Incorrect |

**Explanation:** In syslog configuration, `mail.info` means mail facility logs at priority "info" and higher (info, notice, warning, err, crit, alert, emerg) are directed to `/var/log/maillog`. This captures all but the lowest priority mail logs.

---

### Question 6: Privilege Escalation Logs
**Question:** Which of the following logs would you check to investigate privilege escalation?

| Option | Answer |
|--------|--------|
| A. Firewall logs | Incorrect |
| B. System logs | Incorrect |
| C. Authorization logs | ✅ **Correct** |
| D. Authentication logs | Incorrect |

**Explanation:** Authorization logs (often found in `/var/log/auth.log` or `/var/log/secure`) track privilege escalation events such as sudo usage, su attempts, and permission changes. Authentication logs track login attempts, not privilege changes.

---

### Question 7: Brute-Force Detection
**Question:** Which log type is most useful for detecting brute-force login attempts?

| Option | Answer |
|--------|--------|
| A. Network logs | Incorrect |
| B. Database logs | Incorrect |
| C. Authentication logs | ✅ **Correct** |
| D. Audit logs | Incorrect |

**Explanation:** Authentication logs track failed login attempts and authentication events, making them the primary source for detecting brute-force attacks. Multiple failed attempts from the same source IP indicate potential brute-force activity.

---

### Question 8: Proxy Firewall
**Question:** What is a proxy firewall?

| Option | Answer |
|--------|--------|
| A. A firewall that inspects traffic at the application layer and acts as an intermediary | ✅ **Correct** |
| B. A firewall that only runs on endpoint devices | Incorrect |
| C. A firewall that filters traffic based on IP and port only | Incorrect |
| D. A firewall that blocks all outbound traffic | Incorrect |

**Explanation:** A proxy firewall operates at the application layer (Layer 7), acting as an intermediary between clients and servers. It inspects full application content and can make intelligent decisions based on the actual data being transmitted.

---

### Question 9: Virtualization Benefits
**Question:** Which of the following are BENEFITS of virtualization?

- i. High availability and disaster recovery
- ii. Increased hardware costs
- iii. Remote access and scalability
- iv. Reduced flexibility

| Option | Answer |
|--------|--------|
| A. i and ii | Incorrect |
| B. i and iii | ✅ **Correct** |
| C. i, iii, and iv | Incorrect |
| D. ii and iv | Incorrect |

**Explanation:** High availability/disaster recovery and remote access/scalability are key benefits of virtualization. Increased hardware costs and reduced flexibility are disadvantages, not benefits.

---

### Question 10: DNS A Record
**Question:** What does a DNS "A" record do?

| Option | Answer |
|--------|--------|
| a. Converts a hostname to an IPv4 address | ✅ **Correct** |
| b. Maps a domain to a mail server | Incorrect |
| c. Identifies the authoritative name server | Incorrect |
| d. Defines an alias for a host | Incorrect |

**Explanation:** An A (Address) record maps a hostname to an IPv4 address. MX records map to mail servers, NS records identify name servers, and CNAME records define aliases.

---

### Question 11: Mail Delivery Agent (MDA)
**Question:** What is the role of the Mail Delivery Agent (MDA)?

| Option | Answer |
|--------|--------|
| a. Sends email to the internet | Incorrect |
| b. Resolves domain names | Incorrect |
| c. Delivers email to the recipient's mailbox | ✅ **Correct** |
| d. Authenticates the sender | Incorrect |

**Explanation:** The MDA is responsible for the final delivery of email messages to the recipient's mailbox on the local mail server. MTAs transfer emails between servers, and MUAs are client applications used by users.

---

### Question 12: Syslogd Role
**Question:** Which of the following best describes the role of syslogd?

| Option | Answer |
|--------|--------|
| A. Encrypts log files for security | Incorrect |
| B. Collects, processes, and routes log messages | ✅ **Correct** |
| C. Deletes old log files automatically | Incorrect |
| D. Monitors network bandwidth usage | Incorrect |

**Explanation:** The syslogd daemon is the system logging service that collects log messages from various system components and applications, processes them, and routes them to appropriate destinations (files, remote servers, etc.).

---

### Question 13: Application Layer Firewall
**Question:** Which firewall type operates at the application layer and inspects full content?

| Option | Answer |
|--------|--------|
| A. Proxy firewall | ✅ **Correct** |
| B. Packet filtering firewall | Incorrect |
| C. Stateful firewall | Incorrect |
| D. Network layer firewall | Incorrect |

**Explanation:** Proxy firewalls operate at Layer 7 (Application layer) and can inspect the full content of traffic. Packet filtering operates at Layer 3/4, stateful firewalls track connection state, and network layer firewalls are basic packet filters.

---

### Question 14: Alert Types
**Question:** Which alert type occurs when a real attack is detected and blocked?

| Option | Answer |
|--------|--------|
| A. False Negative | Incorrect |
| B. True Negative | Incorrect |
| C. False Positive | Incorrect |
| D. True Positive | ✅ **Correct** |

**Explanation:** A True Positive occurs when an intrusion detection system correctly identifies and blocks a real attack. False Positives are benign events flagged as attacks, False Negatives are attacks missed, and True Negatives are benign events correctly identified as safe.

---

### Question 15: Symmetric Encryption
**Question:** Which encryption method uses the same key for encryption and decryption?

| Option | Answer |
|--------|--------|
| A. Hashing | Incorrect |
| B. Symmetric encryption | ✅ **Correct** |
| C. Asymmetric encryption | Incorrect |
| D. Digital signature | Incorrect |

**Explanation:** Symmetric encryption uses a single shared key for both encryption and decryption. Asymmetric encryption uses a key pair (public and private), hashing is one-way, and digital signatures use asymmetric keys for authentication.

---

### Question 16: SSL/TLS Encryption Tool
**Question:** Which tool adds SSL/TLS encryption to legacy applications without modifying their code?

| Option | Answer |
|--------|--------|
| A. SCP | Incorrect |
| B. stunnel | ✅ **Correct** |
| C. SFTP | Incorrect |
| D. SSH | Incorrect |

**Explanation:** stunnel is a proxy that adds SSL/TLS encryption to arbitrary TCP connections, allowing legacy applications to communicate securely without code modifications. SCP and SFTP are file transfer protocols, SSH is for secure shell access.

---

### Question 17: Hashing Characteristics
**Question:** Which statements about hashing are correct?

- i. It is a one-way function
- ii. Used for password storage
- iii. Can be reversed with the correct key
- iv. Ensures data integrity

| Option | Answer |
|--------|--------|
| A. ii and iii only | Incorrect |
| B. i, ii, and iv only | ✅ **Correct** |
| C. i and ii only | Incorrect |
| D. All of the above | Incorrect |

**Explanation:** Hashing is one-way (i), commonly used for password storage (ii), and ensures data integrity (iv). Statement iii is false because hashing cannot be reversed by any key - that's what makes it one-way.

---

### Question 18: FCAPS Component
**Question:** Which FCAPS component focuses on detecting and correcting network issues?

| Option | Answer |
|--------|--------|
| A. Performance Management | Incorrect |
| B. Fault Management | ✅ **Correct** |
| C. Accounting Management | Incorrect |
| D. Configuration Management | Incorrect |

**Explanation:** Fault Management in FCAPS focuses on detecting, isolating, and correcting network faults. Performance Management monitors performance, Accounting Management tracks usage, and Configuration Management manages network configurations.

---

### Question 19: Acceptable Use Policy Components
**Question:** Which key components should be included in an Acceptable Use Policy?

- i. Access Policy
- ii. Accountability Policy
- iii. Authentication Policy
- iv. Privacy Policy

| Option | Answer |
|--------|--------|
| A. i and ii only | Incorrect |
| B. i, ii, iii, and iv | ✅ **Correct** |
| C. i, ii, and iii only | Incorrect |
| D. ii and iv only | Incorrect |

**Explanation:** A comprehensive Acceptable Use Policy should include all four components: Access Policy (what can be accessed), Accountability Policy (tracking usage), Authentication Policy (how users prove identity), and Privacy Policy (how data is protected).

---

### Question 20: PKI Components
**Question:** Which of the following are components of PKI?

- i. Certificate Authority
- ii. Digital Certificates
- iii. Public and Private Keys
- iv. Symmetric Key Exchange

| Option | Answer |
|--------|--------|
| A. ii and iv only | Incorrect |
| B. i, ii, and iii only | ✅ **Correct** |
| C. i and ii only | Incorrect |
| D. All of the above | Incorrect |

**Explanation:** PKI (Public Key Infrastructure) includes Certificate Authorities (i), Digital Certificates (ii), and Public/Private Key pairs (iii). Symmetric Key Exchange (iv) is not a PKI component as PKI is based on asymmetric cryptography.

---

### Question 21: Symmetric Encryption Characteristics
**Question:** Which statements about symmetric encryption are true?

- i. Uses one key for both encryption and decryption
- ii. Faster than asymmetric encryption
- iii. Requires secure key exchange
- iv. Cannot be reversed

| Option | Answer |
|--------|--------|
| A. i, ii, and iii only | ✅ **Correct** |
| B. i and ii only | Incorrect |
| C. All of the above | Incorrect |
| D. i and iv only | Incorrect |

**Explanation:** Symmetric encryption uses one key (i), is faster than asymmetric (ii), and requires secure key exchange (iii). Statement iv is false because symmetric encryption can be reversed with the correct key.

---

### Question 22: Policy-Based Management
**Question:** Policy-Based Management is best described as:

| Option | Answer |
|--------|--------|
| A. A method for encrypting network traffic | Incorrect |
| B. A protocol for secure communication | Incorrect |
| C. A tool for monitoring bandwidth usage | Incorrect |
| D. A framework for defining goals and responses for system administration | ✅ **Correct** |

**Explanation:** Policy-Based Management is a framework that allows administrators to define policies (goals and responses) that govern how systems are managed and maintained, ensuring consistency and compliance across the infrastructure.

---

### Question 23: Log Policy Matching
**Question:** Match policy with description:

| Policy | Description | Match |
|--------|-------------|-------|
| Rotation | Rename and age log files daily | ✅ |
| Retention | Keep logs for 1-2 months for security evidence | ✅ |
| Archiving | Store logs on tape or permanent media | ✅ |

**Explanation:**
- **Log Rotation**: Periodically renaming and aging log files to prevent them from becoming too large
- **Log Retention**: Defining how long logs are kept before deletion for compliance and security purposes
- **Log Archiving**: Moving old logs to permanent storage for long-term preservation

---

### Question 24: LDAP Components
**Question:** Match the LDAP component with its role:

| Component | Role | Match |
|-----------|------|-------|
| ou | Represents organizational unit like users/groups | ✅ |
| cn | Identifies a specific user or group name | ✅ |
| dc | Maps domain names to directory entries | ✅ |

**Explanation:**
- **ou** (Organizational Unit): Represents containers in the directory hierarchy for organizing objects
- **cn** (Common Name): Identifies individual objects like users or groups
- **dc** (Domain Component): Represents parts of a domain name (e.g., dc=example,dc=com)

---

### Question 25: Security Terms
**Question:** Match each term with its description:

| Term | Description | Match |
|------|-------------|-------|
| TLS | Modern secure protocol replacing SSL | ✅ |
| Certificate Authority | Issues trusted digital certificates | ✅ |
| SSL | Obsolete protocol, vulnerable | ✅ |
| HTTPS | HTTP secured with TLS | ✅ |
| Self-Signed Certificate | Issuer and subject are the same | ✅ |

**Explanation:**
- **TLS** (Transport Layer Security): The modern successor to SSL for secure communications
- **Certificate Authority (CA)**: Trusted entity that issues and validates digital certificates
- **SSL** (Secure Sockets Layer): Older protocol now deprecated due to security vulnerabilities
- **HTTPS**: HTTP protocol secured with TLS/SSL encryption
- **Self-Signed Certificate**: Certificate where the issuer and subject are identical, not trusted by default

---

### Question 26: Algorithm Types
**Question:** Match each algorithm type with its characteristic:

| Algorithm Type | Characteristic | Match |
|----------------|----------------|-------|
| Asymmetric | Uses a public and private key pair | ✅ |
| Block Cipher | Encrypts fixed-size blocks of data | ✅ |
| Symmetric | Uses one key for both encryption and decryption | ✅ |
| Hashing | Irreversible, used for integrity checks | ✅ |

**Explanation:**
- **Asymmetric Encryption**: Uses key pairs (public/private) where one encrypts and the other decrypts
- **Block Cipher**: Processes data in fixed-size blocks (e.g., 128-bit blocks in AES)
- **Symmetric Encryption**: Single shared key for both encryption and decryption
- **Hashing**: One-way function producing fixed-size output, cannot be reversed

---

### Question 27: Security Concepts
**Question:** Match security concept with example:

| Concept | Example | Match |
|---------|---------|-------|
| DMZ | Hosts public-facing servers | ✅ |
| UTM | Combines firewall, antivirus, VPN | ✅ |
| IPS | Blocks malicious traffic automatically | ✅ |

**Explanation:**
- **DMZ** (Demilitarized Zone): Isolated network segment for public-facing services to protect internal networks
- **UTM** (Unified Threat Management): Single appliance combining multiple security features (firewall, antivirus, VPN, etc.)
- **IPS** (Intrusion Prevention System): Actively detects and blocks malicious traffic in real-time

---

### Question 28: Storage Interfaces
**Question:** Match the storage interface with the use case:

| Interface | Use Case | Match |
|-----------|----------|-------|
| NVMe | High-performance computing, gaming rigs | ✅ |
| USB | Removable media, thumb drives | ✅ |
| SATA | Consumer laptops, budget desktops | ✅ |
| SAS | Enterprise-grade servers, scalable storage | ✅ |

**Explanation:**
- **NVMe**: High-speed protocol for flash storage, ideal for performance-critical applications
- **USB**: Universal interface for portable, removable storage devices
- **SATA**: Common interface for consumer storage (HDDs and SSDs)
- **SAS**: Enterprise-grade interface supporting high availability and scalability in servers

---

### Question 29: Email System Architecture
**Question:** Explain the architecture of a modern email system by describing the roles of the key agents involved in sending and receiving email.

**Answer:**

A modern email system involves several key components working together:

**1. MUA (Mail User Agent)**
- The email client application (e.g., Outlook, Thunderbird, Gmail web interface)
- Used by users to compose, read, and manage emails
- Think of it as your personal mailbox at home

**2. MSA (Mail Submission Agent)**
- Accepts emails from the MUA for sending
- Often part of the MTA in modern systems
- Like the post office where you drop off outgoing mail

**3. MTA (Mail Transfer Agent)**
- Transfers emails between mail servers across the internet
- Uses SMTP to route emails to their destination
- Acts like postal trucks and distribution centers moving mail between cities
- Examples: Postfix, Sendmail, Exim

**4. MDA (Mail Delivery Agent)**
- Delivers the final email to the recipient's mailbox on the server
- Sorts incoming mail into the right mailbox
- Like the local postal carrier who delivers mail to your house

**5. POP3/IMAP (Retrieval Protocols)**
- Allow users to retrieve emails from the server to their MUA
- POP3: Downloads and often removes from server
- IMAP: Keeps emails synchronized across devices

**Example Flow:**
1. User writes email in Gmail (MUA)
2. Gmail sends to Gmail's submission server (MSA)
3. Google's MTA routes it to recipient's mail server
4. Recipient's MDA places it in their mailbox
5. Recipient retrieves it using IMAP to their email client

---

### Question 30: Symmetric vs Asymmetric Encryption
**Question:** Compare symmetric and asymmetric encryption in terms of their definitions, working mechanisms, advantages, disadvantages, and examples of commonly used algorithms.

**Answer:**

| Aspect | Symmetric Encryption | Asymmetric Encryption |
|--------|---------------------|----------------------|
| **Definition** | Uses a single shared key for both encryption and decryption | Uses a pair of mathematically related keys (public and private) |
| **Working Mechanism** | - Sender and receiver share the same secret key<br>- Key must be exchanged securely beforehand<br>- Same key encrypts and decrypts | - Public key encrypts, private key decrypts (or vice versa)<br>- Public key can be freely distributed<br>- Private key must be kept secret |
| **Advantages** | - Much faster (100-1000x faster than asymmetric)<br>- Less computational overhead<br>- Efficient for large data encryption<br>- Simpler implementation | - No need for secure key exchange<br>- Enables digital signatures<br>- Supports non-repudiation<br>- Better for key distribution |
| **Disadvantages** | - Secure key exchange is challenging<br>- Key management becomes complex with many users<br>- Doesn't support digital signatures<br>- Each pair needs unique key | - Much slower computationally<br>- Larger key sizes required<br>- More complex implementation<br>- Vulnerable to certain attacks if not implemented correctly |
| **Common Algorithms** | - AES (Advanced Encryption Standard)<br>- DES/3DES (Data Encryption Standard)<br>- RC4 (Rivest Cipher 4)<br>- Blowfish<br>- ChaCha20 | - RSA (Rivest-Shamir-Adleman)<br>- ECC (Elliptic Curve Cryptography)<br>- Diffie-Hellman (key exchange)<br>- DSA (Digital Signature Algorithm)<br>- ElGamal |
| **Key Size** | Typically 128, 192, or 256 bits | Typically 2048-4096 bits (RSA) or 256-521 bits (ECC) |
| **Typical Use Cases** | - Encrypting large files<br>- Encrypting data streams<br>- Disk encryption<br>- Secure communication sessions | - Secure key exchange<br>- Digital signatures<br>- SSL/TLS certificates<br>- SSH authentication |
| **Analogy** | Like a shared secret password between two people | Like a mailbox where anyone can drop mail (public key) but only the owner has the key to open it (private key) |

**Hybrid Approach:**
Most modern systems (like SSL/TLS) use both:
1. Asymmetric encryption to securely exchange a symmetric key
2. Symmetric encryption for the actual data transfer (faster)

---

## Chapter 1: Linux Fundamentals

### Question 1: Linux Origins
**Question:** What is Linux primarily based on?

| Option | Answer |
|--------|--------|
| a. DOS | Incorrect |
| b. UNIX | ✅ **Correct** |
| c. Windows NT | Incorrect |
| d. macOS | Incorrect |

**Explanation:** Linux was created by Linus Torvalds in 1991 as a UNIX-like operating system. While it's not UNIX, it follows UNIX design principles and is POSIX-compliant, sharing the same philosophy and many commands.

---

### Question 2: Linux Features
**Question:** Which of the following is NOT a feature of Linux?

| Option | Answer |
|--------|--------|
| a. Open Source | Incorrect |
| b. Free | Incorrect |
| c. Closed-source kernel | ✅ **Correct** |
| d. Customizable | Incorrect |

**Explanation:** Linux is open source, free to use and modify, and highly customizable. The kernel is open source, not closed source. This is one of Linux's fundamental principles.

---

## Chapter 2: Virtualization

### Question 1: Virtualization Purpose
**Question:** What is the main purpose of virtualization?

| Option | Answer |
|--------|--------|
| a. To allow multiple users to share a single physical resource | ✅ **Correct** |
| b. To install multiple operating systems on one machine | Incorrect |
| c. To reduce software licensing costs | Incorrect |
| d. To increase physical hardware usage | Incorrect |

**Explanation:** While installing multiple OSes is a benefit, the main purpose is resource sharing - allowing multiple users or workloads to share physical hardware efficiently through virtual machines.

---

### Question 2: Physical Machine Name
**Question:** What is the term for the physical machine that hosts virtual machines?

| Option | Answer |
|--------|--------|
| a. Guest Machine | Incorrect |
| b. Hypervisor | Incorrect |
| c. Host Machine | ✅ **Correct** |
| d. Virtual Monitor | Incorrect |

**Explanation:** The physical machine is called the Host Machine. The virtual machines running on it are called Guest Machines. The software that manages this is the Hypervisor.

---

### Question 3: Hypervisor Definition
**Question:** What is a hypervisor?

| Option | Answer |
|--------|--------|
| a. A Linux kernel module | Incorrect |
| b. A virtual OS | Incorrect |
| c. A network monitor | Incorrect |
| d. Software that creates and runs virtual machines | ✅ **Correct** |

**Explanation:** A hypervisor (or Virtual Machine Monitor - VMM) is software that creates and manages virtual machines, allocating physical resources to each VM.

---

### Question 4: Virtualization Benefits
**Question:** Which of the following is NOT a benefit of virtualization?

| Option | Answer |
|--------|--------|
| a. Remote access and scalability | Incorrect |
| b. High availability and disaster recovery | Incorrect |
| c. Running multiple operating systems | Incorrect |
| d. Increased hardware costs | ✅ **Correct** |

**Explanation:** Increased hardware costs is a disadvantage, not a benefit. Virtualization actually reduces hardware costs through better resource utilization. The other options are all benefits.

---

### Question 5: Resource Allocation Benefit
**Question:** Which benefit of virtualization supports flexible resource allocation?

| Option | Answer |
|--------|--------|
| a. Frequent updates | Incorrect |
| b. Enhanced development productivity | Incorrect |
| c. Logical naming of resources | Incorrect |
| d. Pay-per-use infrastructure | ✅ **Correct** |

**Explanation:** Pay-per-use infrastructure (common in cloud computing) allows flexible resource allocation - you only pay for what you use and can scale up or down as needed.

---

### Question 6: Bare-Metal Architecture
**Question:** What defines Bare-Metal Architecture (Type 1)?

| Option | Answer |
|--------|--------|
| a. Requires a host OS like Windows | Incorrect |
| b. Hypervisor installs directly on hardware | ✅ **Correct** |
| c. Uses container-based virtualization | Incorrect |
| d. Hypervisor runs on top of an OS | Incorrect |

**Explanation:** Type 1 (Bare-Metal) hypervisors install directly on the hardware without a host OS, providing better performance and efficiency. Examples: VMware ESXi, Microsoft Hyper-V, Xen.

---

### Question 7: Hosted Architecture
**Question:** Which architecture installs virtualization software as an application on an existing OS?

| Option | Answer |
|--------|--------|
| a. Cloud Architecture | Incorrect |
| b. Bare-Metal Architecture | Incorrect |
| c. Hosted Architecture | ✅ **Correct** |
| d. Hybrid Architecture | Incorrect |

**Explanation:** Type 2 (Hosted) hypervisors run as applications on top of a host OS. Examples: VMware Workstation, VirtualBox, Parallels Desktop.

---

### Question 8: Bare-Metal Hypervisor Example
**Question:** Which of the following is an example of a Bare-Metal hypervisor?

| Option | Answer |
|--------|--------|
| a. VMware Workstation | Incorrect |
| b. Xen | ✅ **Correct** |
| c. Microsoft Virtual PC | Incorrect |
| d. Parallels Desktop | Incorrect |

**Explanation:** Xen is a Type 1 bare-metal hypervisor. The other options are Type 2 hosted hypervisors that run on top of an OS.

---

### Question 9: Distribution Selection
**Question:** Which factor is most important when choosing a Linux distribution for virtualization?

| Option | Answer |
|--------|--------|
| a. Number of pre-installed games | Incorrect |
| b. Performance optimization | ✅ **Correct** |
| c. GUI design | Incorrect |
| d. Default wallpaper | Incorrect |

**Explanation:** Performance optimization is critical for virtualization as the host needs to efficiently manage resources for multiple VMs. Other factors like GUI are less important.

---

### Question 10: Local Virtualization
**Question:** Which virtualization type installs on a local machine?

| Option | Answer |
|--------|--------|
| a. Citrix XenDesktop | Incorrect |
| b. IBM VM/370 | Incorrect |
| c. VMware Workstation | ✅ **Correct** |
| d. XenServer | Incorrect |

**Explanation:** VMware Workstation is a Type 2 hypervisor designed for local desktop virtualization. The others are enterprise or cloud-based solutions.

---

### Question 11: First Hypervisor Project
**Question:** Who led the project for the first full virtualization hypervisor?

| Option | Answer |
|--------|--------|
| a. Linus Torvalds | Incorrect |
| b. Robert Jay Creasy | ✅ **Correct** |
| c. Dennis Ritchie | Incorrect |
| d. Bill Gates | Incorrect |

**Explanation:** Robert Jay Creasy led the IBM VM/370 project, which was the first full virtualization hypervisor developed in the 1960s-1970s.

---

### Question 12: VMM Function
**Question:** What does the VMM do in a virtualized system?

| Option | Answer |
|--------|--------|
| a. Encrypts network traffic | Incorrect |
| b. Controls system resources and provides virtual environments | ✅ **Correct** |
| c. Installs operating systems | Incorrect |
| d. Manages user accounts | Incorrect |

**Explanation:** The Virtual Machine Monitor (VMM) or hypervisor controls physical resources (CPU, memory, storage) and allocates them to virtual machines, creating isolated virtual environments.

---

## Chapter 3: Storage and File Systems

### Question 1: Boot Disk Purpose
**Question:** What is the primary role of a boot disk?

| Option | Answer |
|--------|--------|
| a. To store user data | Incorrect |
| b. To manage network connections | Incorrect |
| c. To load and run an operating system | ✅ **Correct** |
| d. To connect external devices | Incorrect |

**Explanation:** A boot disk contains the bootloader and operating system files needed to start the computer. It's the disk from which the system boots.

---

### Question 2: Storage Interfaces
**Question:** Which of the following is NOT a type of storage interface?

| Option | Answer |
|--------|--------|
| a. SCSI | Incorrect |
| b. SATA | Incorrect |
| c. NVMe | Incorrect |
| d. BIOS | ✅ **Correct** |

**Explanation:** BIOS is firmware that handles hardware initialization during boot, not a storage interface. SCSI, SATA, and NVMe are all storage interface standards.

---

### Question 3: Partitioning Scheme
**Question:** Which partitioning scheme supports disks larger than 2TB and unlimited partitions?

| Option | Answer |
|--------|--------|
| a. FAT32 | Incorrect |
| b. MBR | Incorrect |
| c. GPT | ✅ **Correct** |
| d. NTFS | Incorrect |

**Explanation:** GPT (GUID Partition Table) supports disks larger than 2TB and up to 128 partitions (theoretically unlimited). MBR is limited to 2TB and 4 primary partitions. FAT32 and NTFS are file systems, not partitioning schemes.

---

### Question 4: Linux File System
**Question:** In Linux, which file system is most commonly used today?

| Option | Answer |
|--------|--------|
| a. HFS+ | Incorrect |
| b. ext3/ext4 | ✅ **Correct** |
| c. FAT32 | Incorrect |
| d. NTFS | Incorrect |

**Explanation:** ext4 (and its predecessor ext3) is the most commonly used file system in Linux. HFS+ is macOS, FAT32 is cross-platform but limited, NTFS is Windows-native (though Linux can read it).

---

### Question 5: Storage Terms
**Question:** Match the term in the name with its correct description.

| Term | Description | Match |
|------|-------------|-------|
| SATA | Serial ATA - Serial interface for storage devices | ✅ |
| GPT | GUID Partition Table - Modern partitioning scheme | ✅ |
| BIOS | Basic Input/Output System - Firmware for hardware initialization | ✅ |
| GRUB | Grand Unified Bootloader - Boot loader for Linux | ✅ |
| ext4 | Fourth Extended Filesystem - Common Linux filesystem | ✅ |

**Explanation:**
- **SATA**: Serial Advanced Technology Attachment - Serial interface connecting storage devices
- **GPT**: GUID Partition Table - Partitioning scheme replacing MBR
- **BIOS**: Basic Input/Output System - Firmware that initializes hardware during boot
- **GRUB**: GRand Unified Bootloader - The default bootloader for most Linux distributions
- **ext4**: Fourth extended filesystem - Journaling filesystem and default for many Linux distributions

---

## Chapter 4: OSI Model and Networking

### Question 1: Transport Layer
**Question:** Which OSI layer is responsible for reliable end-to-end communication and error recovery?

| Option | Answer |
|--------|--------|
| a. Session | Incorrect |
| b. Network | Incorrect |
| c. Data Link | Incorrect |
| d. Transport | ✅ **Correct** |

**Explanation:** Layer 4 (Transport) provides reliable end-to-end communication, flow control, error recovery, and segmentation. TCP operates at this layer.

---

### Question 2: Network Layer Protocol
**Question:** Which protocol operates at the Network layer and is responsible for logical addressing and routing?

| Option | Answer |
|--------|--------|
| a. FTP | Incorrect |
| b. IP | ✅ **Correct** |
| c. ARP | Incorrect |
| d. TCP | Incorrect |

**Explanation:** IP (Internet Protocol) operates at Layer 3 (Network) and handles logical addressing (IP addresses) and routing packets between networks. ARP operates at Layer 2, TCP at Layer 4, FTP at Layer 7.

---

### Question 3: Presentation Layer
**Question:** What is the main function of the Presentation layer in the OSI model?

| Option | Answer |
|--------|--------|
| a. Encrypting and formatting data | ✅ **Correct** |
| b. Routing packets | Incorrect |
| c. Providing MAC addresses | Incorrect |
| d. Managing sessions | Incorrect |

**Explanation:** Layer 6 (Presentation) handles data formatting, encryption/decryption, compression, and character encoding to ensure data from the application layer is readable by the receiving system.

---

### Question 4: Connectionless Protocol
**Question:** Which of the following is a connectionless protocol used for fast, unreliable communication?

| Option | Answer |
|--------|--------|
| a. TCP | Incorrect |
| b. ICMP | Incorrect |
| c. UDP | ✅ **Correct** |
| d. SMTP | Incorrect |

**Explanation:** UDP (User Datagram Protocol) is connectionless - it sends packets without establishing a connection first. This makes it faster but less reliable (no guaranteed delivery or ordering).

---

### Question 5: OSI Layer Functions
**Question:** Match the OSI Layer with Its Function

| Layer | Function | Match |
|-------|----------|-------|
| Layer 5 (Session) | Establishes, manages, and terminates sessions between applications | ✅ |
| Layer 3 (Network) | Logical addressing and routing of packets between networks | ✅ |
| Layer 1 (Physical) | Transmission of raw bits over physical medium (cables, wireless) | ✅ |

**Explanation:**
- **Layer 5 (Session)**: Manages dialogues/connections between applications
- **Layer 3 (Network)**: Handles routing and logical addressing (IP)
- **Layer 1 (Physical)**: Defines electrical, mechanical, and procedural specifications for physical transmission

---

### Question 6: Protocol Layers
**Question:** Match the Protocol with Its OSI Layer

| Protocol | OSI Layer | Match |
|----------|-----------|-------|
| IP | Layer 3 (Network) | ✅ |
| TCP | Layer 4 (Transport) | ✅ |
| HTTP | Layer 7 (Application) | ✅ |

**Explanation:**
- **IP**: Internet Protocol - Network layer for routing and addressing
- **TCP**: Transmission Control Protocol - Transport layer for reliable, connection-oriented communication
- **HTTP**: Hypertext Transfer Protocol - Application layer for web communication

---

## Chapter 5: DHCP and DNS

### Question 1: DHCP Improvement
**Question:** What key improvement did DHCP introduce over BOOTP?

| Option | Answer |
|--------|--------|
| a. Dynamic IP leasing | ✅ **Correct** |
| b. Static IP assignment | Incorrect |
| c. MAC-to-IP mapping only | Incorrect |
| d. Manual configuration | Incorrect |

**Explanation:** DHCP introduced dynamic IP address leasing, allowing automatic assignment and reuse of IP addresses. BOOTP only supported static mapping, requiring manual configuration for each device.

---

### Question 2: DHCP Ports
**Question:** Which ports are used by DHCP for communication?

| Option | Answer |
|--------|--------|
| a. UDP 53 and 123 | Incorrect |
| b. UDP 67 and 68 | ✅ **Correct** |
| c. TCP 80 and 443 | Incorrect |
| d. TCP 25 and 110 | Incorrect |

**Explanation:** DHCP uses UDP port 67 for DHCP server (listening) and UDP port 68 for DHCP client. UDP 53/123 are DNS/NTP, TCP 80/443 are HTTP/HTTPS, TCP 25/110 are SMTP/POP3.

---

### Question 3: DNS A Record
**Question:** What does a DNS "A" record do?

| Option | Answer |
|--------|--------|
| a. Identifies the authoritative name server | Incorrect |
| b. Maps a domain to a mail server | Incorrect |
| c. Converts a hostname to an IPv4 address | ✅ **Correct** |
| d. Defines an alias for a host | Incorrect |

**Explanation:** An A (Address) record maps a hostname to an IPv4 address. NS records identify name servers, MX records map to mail servers, and CNAME records define aliases.

---

### Question 4: DNS MX Record
**Question:** Which DNS record type is used to define mail servers for a domain?

| Option | Answer |
|--------|--------|
| a. MX | ✅ **Correct** |
| b. CNAME | Incorrect |
| c. TXT | Incorrect |
| d. NS | Incorrect |

**Explanation:** MX (Mail Exchange) records define the mail servers that accept email for a domain. Multiple MX records can exist with priority values.

---

### Question 5: DHCP Evolution
**Question:** Match the DHCP Era with Its Characteristics

| Protocol | Characteristics | Match |
|----------|-----------------|-------|
| RARP | Reverse ARP - Maps MAC to IP, very limited | ✅ |
| BOOTP | Bootstrap Protocol - Static mapping, requires manual config | ✅ |
| DHCP | Dynamic Host Configuration Protocol - Dynamic IP leasing | ✅ |

**Explanation:**
- **RARP**: Early protocol mapping MAC addresses to IP addresses, limited functionality
- **BOOTP**: Improvement over RARP with static configuration, still required manual setup
- **DHCP**: Full-featured protocol with dynamic IP assignment, lease management, and automatic configuration

---

### Question 6: DNS Record Types
**Question:** Match the DNS Record Type with Its Function

| Record Type | Function | Match |
|-------------|----------|-------|
| CNAME | Canonical Name - Defines an alias for a hostname | ✅ |
| NS | Name Server - Identifies authoritative DNS servers | ✅ |
| SOA | Start of Authority - Defines zone parameters and primary NS | ✅ |

**Explanation:**
- **CNAME**: Creates alias names pointing to other hostnames (e.g., www pointing to example.com)
- **NS**: Specifies which name servers are authoritative for a domain
- **SOA**: Contains authoritative information about a DNS zone, including primary name server, email of administrator, and timing parameters

---

## Chapter 6: Email Systems

### Question 1: Inter-Server Email Transfer
**Question:** Which component is responsible for transferring email from one server to another across the internet?

| Option | Answer |
|--------|--------|
| a. MDA | Incorrect |
| b. DNS | Incorrect |
| c. MUA | Incorrect |
| d. MTA | ✅ **Correct** |

**Explanation:** The MTA (Mail Transfer Agent) transfers emails between mail servers across the internet using SMTP. Examples include Postfix, Sendmail, and Exim.

---

### Question 2: MDA Role
**Question:** What is the role of the Mail Delivery Agent (MDA)?

| Option | Answer |
|--------|--------|
| a. Authenticates the sender | Incorrect |
| b. Sends email to the internet | Incorrect |
| c. Resolves domain names | Incorrect |
| d. Delivers email to the recipient's mailbox | ✅ **Correct** |

**Explanation:** The MDA is responsible for the final delivery of emails to the recipient's mailbox on the local server. It sorts incoming mail and places it in the appropriate user mailbox.

---

### Question 3: Sending Email Protocol
**Question:** Which protocol is primarily used to send email from a client to a server?

| Option | Answer |
|--------|--------|
| a. SMTP | ✅ **Correct** |
| b. HTTP | Incorrect |
| c. IMAP | Incorrect |
| d. POP3 | Incorrect |

**Explanation:** SMTP (Simple Mail Transfer Protocol) is used for sending emails from clients to servers and between servers. IMAP and POP3 are for retrieving emails.

---

### Question 4: Email Agents
**Question:** Match the Email Agent with Its Role

| Agent | Role | Match |
|-------|------|-------|
| MTA | Mail Transfer Agent - Transfers emails between servers | ✅ |
| MSA | Mail Submission Agent - Accepts emails from clients for sending | ✅ |
| MUA | Mail User Agent - Email client used by users (e.g., Outlook, Gmail) | ✅ |

**Explanation:**
- **MTA**: Transfers emails between mail servers across networks (uses SMTP)
- **MSA**: Accepts emails from MUAs for submission to the mail system (uses SMTP)
- **MUA**: The email client application that users interact with to compose, read, and manage emails

---

## Chapter 7: LDAP and Authentication

### Question 1: LDAP Definition
**Question:** LDAP is best described as:

| Option | Answer |
|--------|--------|
| A. A file system hierarchy tool | Incorrect |
| B. A directory service created by Microsoft | Incorrect |
| C. A protocol for accessing and managing directory services | ✅ **Correct** |
| D. A database engine for storing tabular data | Incorrect |

**Explanation:** LDAP (Lightweight Directory Access Protocol) is a protocol for accessing and maintaining distributed directory information services over IP networks. Microsoft's implementation is Active Directory.

---

### Question 2: LDAP Directory Service
**Question:** Which of the following is a directory service that implements LDAP?

| Option | Answer |
|--------|--------|
| A. PostgreSQL | Incorrect |
| B. MySQL | Incorrect |
| C. OpenLDAP | ✅ **Correct** |
| D. MongoDB | Incorrect |

**Explanation:** OpenLDAP is an open-source implementation of LDAP. PostgreSQL and MySQL are relational databases, MongoDB is a NoSQL document database.

---

### Question 3: Distinguished Name
**Question:** In LDAP, the DN (Distinguished Name) represents:

| Option | Answer |
|--------|--------|
| A. The IP address of the server | Incorrect |
| B. The unique path to an object in the directory tree | ✅ **Correct** |
| C. The username and password pair | Incorrect |
| D. The schema definition file | Incorrect |

**Explanation:** The Distinguished Name (DN) is the unique identifier for an entry in the LDAP directory tree, representing the full path from the root to that entry (e.g., cn=John,ou=Users,dc=example,dc=com).

---

### Question 4: Common Name Attribute
**Question:** Which attribute is commonly used to represent a user's name in LDAP?

| Option | Answer |
|--------|--------|
| A. o | Incorrect |
| B. uid | Incorrect |
| C. cn | ✅ **Correct** |
| D. mail | Incorrect |

**Explanation:** cn (Common Name) is the attribute typically used for a person's name. uid is the user ID, o is organization, and mail is email address.

---

### Question 5: LDAP Port
**Question:** Which port is used for unencrypted LDAP communication?

| Option | Answer |
|--------|--------|
| A. 389 | ✅ **Correct** |
| B. 22 | Incorrect |
| C. 868 | Incorrect |
| D. 443 | Incorrect |

**Explanation:** LDAP uses port 389 for standard (unencrypted) communication and port 636 for LDAPS (LDAP over SSL). Port 22 is SSH, 443 is HTTPS.

---

### Question 6: LDAP Components
**Question:** Match the LDAP component with its role

| Component | Role | Match |
|-----------|------|-------|
| ou | Organizational Unit - Represents organizational unit like users/groups | ✅ |
| cn | Common Name - Identifies a specific user or group name | ✅ |
| dc | Domain Component - Maps domain names to directory entries | ✅ |

**Explanation:**
- **ou**: Organizational Unit - Container for organizing directory objects
- **cn**: Common Name - Name of an object (user, group, etc.)
- **dc**: Domain Component - Part of domain name (e.g., dc=example,dc=com)

---

### Question 7: AAA Functions
**Question:** Match the AAA function with its question

| Function | Question | Match |
|----------|----------|-------|
| Authorization | "What can you access?" | ✅ |
| Accounting | "What did you do, and when?" | ✅ |
| Authentication | "Who are you?" | ✅ |

**Explanation:**
- **Authentication**: Verifying identity (Who are you?)
- **Authorization**: Determining access rights (What can you access?)
- **Accounting**: Tracking usage (What did you do, and when?)

---

### Question 8: Authentication Frameworks
**Question:** Match the framework with its scope

| Framework | Scope | Match |
|-----------|-------|-------|
| Kerberos | Ticket-based authentication for SSO in enterprise networks | ✅ |
| SASL | Protocol/application layer authentication (e.g., IMAP, LDAP) | ✅ |
| PAM | OS/service level authentication (e.g., ssh, sudo) | ✅ |

**Explanation:**
- **Kerberos**: Network authentication protocol using tickets for single sign-on
- **SASL**: Simple Authentication and Security Layer - framework for adding authentication to connection-oriented protocols
- **PAM**: Pluggable Authentication Modules - flexible authentication framework for Linux/Unix services

---

## Chapter 8: Cryptography Basics

### Question 1: Encryption Definition
**Question:** A student sends a secret message to a friend. Before sending, the message is scrambled so nobody else can read it. What process is this?

| Option | Answer |
|--------|--------|
| a. Key Generation | Incorrect |
| b. Decryption | Incorrect |
| c. Encryption | ✅ **Correct** |
| d. Hashing | Incorrect |

**Explanation:** Encryption is the process of converting plaintext into ciphertext (scrambled data) so that only authorized parties can read it. Decryption reverses this process.

---

### Question 2: Decryption Definition
**Question:** Ali receives a scrambled message from his teacher. He uses the correct method and secret value to turn it back into readable text. What process is Ali performing?

| Option | Answer |
|--------|--------|
| a. Decryption | ✅ **Correct** |
| b. Firewall | Incorrect |
| c. Encryption | Incorrect |
| d. Algorithm | Incorrect |

**Explanation:** Decryption is the process of converting ciphertext back into plaintext using the correct key/algorithm. The "secret value" mentioned is the encryption key.

---

### Question 3: Symmetric Encryption
**Question:** Two classmates use the same secret code to lock and unlock their chat messages. What type of encryption are they using?

| Option | Answer |
|--------|--------|
| a. Asymmetric Encryption | Incorrect |
| b. Open Encryption | Incorrect |
| c. Public Encryption | Incorrect |
| d. Symmetric Encryption | ✅ **Correct** |

**Explanation:** Symmetric encryption uses a single shared secret key for both encryption and decryption. Both parties must have the same key to communicate securely.

---

### Question 4: Asymmetric Encryption
**Question:** A website allows everyone to use a public key to send secure data, but only the website owner can unlock it using a private key. What type of encryption is this?

| Option | Answer |
|--------|--------|
| a. Asymmetric Encryption | ✅ **Correct** |
| b. Simple Encryption | Incorrect |
| c. Symmetric Encryption | Incorrect |
| d. Manual Encryption | Incorrect |

**Explanation:** Asymmetric (public-key) encryption uses a key pair: a public key that anyone can use to encrypt, and a private key that only the owner has to decrypt. This enables secure communication without pre-shared secrets.

---

### Question 5: Key Definition
**Question:** A hacker tries to read protected data but fails because they do not know the secret value needed to unlock it. What is this secret value called?

| Option | Answer |
|--------|--------|
| a. Browser | Incorrect |
| b. Algorithm | Incorrect |
| c. Key | ✅ **Correct** |
| d. Server | Incorrect |

**Explanation:** A key is the secret value used in conjunction with an encryption algorithm to encrypt or decrypt data. Without the correct key, encrypted data cannot be read.

---

### Question 6: Certificate Authority
**Question:** A new employee at a company needs a digital identity to access secure internal systems. The employee submits a request to a trusted authority. The trusted entity that verifies the employee's identity is called a:

**Answer:** Certificate Authority (CA)

**Explanation:** A Certificate Authority is a trusted third-party entity that verifies the identity of individuals, organizations, or devices and issues digital certificates that confirm their identity.

---

### Question 7: Digital Certificate
**Question:** After verifying the employee's identity, the trusted authority issues a document that proves the employee is genuine and can be trusted online. This document is called a:

**Answer:** Digital Certificate

**Explanation:** A digital certificate is an electronic document that binds a public key to an identity (person, organization, device). It's issued by a Certificate Authority and serves as proof of identity in digital communications.

---

## Summary of Key Concepts

### DNS Records
- **A**: Hostname to IPv4 address
- **AAAA**: Hostname to IPv6 address
- **MX**: Mail exchange server
- **NS**: Name server
- **CNAME**: Alias/Canonical name
- **SOA**: Start of authority

### Email Components
- **MUA**: Mail User Agent (client)
- **MSA**: Mail Submission Agent
- **MTA**: Mail Transfer Agent (server-to-server)
- **MDA**: Mail Delivery Agent (final delivery)

### Virtualization Types
- **Type 1 (Bare-Metal)**: Hypervisor on hardware (ESXi, Xen)
- **Type 2 (Hosted)**: Hypervisor on OS (VMware Workstation, VirtualBox)

### OSI Model Layers (7-1)
7. **Application**: User interface, applications
6. **Presentation**: Data formatting, encryption
5. **Session**: Session management
4. **Transport**: End-to-end communication (TCP/UDP)
3. **Network**: Routing, logical addressing (IP)
2. **Data Link**: MAC addressing, error detection
1. **Physical**: Bits over physical medium

### Encryption Types
- **Symmetric**: One key, fast (AES, DES)
- **Asymmetric**: Key pair, enables key exchange (RSA, ECC)
- **Hashing**: One-way, integrity (SHA, MD5)

### AAA Framework
- **Authentication**: Who are you?
- **Authorization**: What can you access?
- **Accounting**: What did you do?

### LDAP Components
- **cn**: Common Name
- **ou**: Organizational Unit
- **dc**: Domain Component
- **uid**: User ID
- **dn**: Distinguished Name

---

**End of Study Guide**
