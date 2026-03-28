# Network and Linux Systems Administration Notes

## Table of Contents
1. [Virtualization and VM Concepts](#virtualization-and-vm-concepts)
2. [Linux Distributions](#linux-distributions)
3. [Network Concepts](#network-concepts)
4. [Hostname and FQDN](#hostname-and-fqdn)
5. [Linux Commands](#linux-commands)
6. [Users and Groups](#users-and-groups)
7. [Permissions and Ownership](#permissions-and-ownership)
8. [DNS (Domain Name System)](#dns-domain-name-system)
9. [DHCP (Dynamic Host Configuration Protocol)](#dhcp-dynamic-host-configuration-protocol)
10. [FTP (File Transfer Protocol)](#ftp-file-transfer-protocol)
11. [SSL/TLS](#ssltls)
12. [NFS (Network File System)](#nfs-network-file-system)
13. [SSH (Secure Shell)](#ssh-secure-shell)
14. [Firewalld](#firewalld)
15. [ACL (Access Control Lists)](#acl-access-control-lists)
16. [Syslog](#syslog)

---

## Virtualization and VM Concepts

### What is a Virtual Machine (VM)?
A Virtual Machine (VM) operates like a physical computer, providing an emulated environment of a physical computer system, capable of running an operating system and applications.

### Types of Hypervisors
- **Type 1 Hypervisor**: Runs directly on the hardware (bare-metal)
- **Type 2 Hypervisor**: Runs on top of a host operating system

### Advantages of Virtual Machines
1. **Simultaneous OS**: Multiple operating systems can run on one physical machine
2. **Isolated Memory**: VMs have their own memory and disk space
3. **Enhanced Security**: VMs provide greater security by isolating processes
4. **Resource Sharing**: VMs can share the host system's CPU, memory, and disk space
5. **Portability**: VMs can be easily moved between different physical machines
6. **Compatibility**: VMs allow you to run multiple operating systems on a single physical machine

### VirtualBox Guest Additions
Software packages installed within a VM that enhance functionality:
- **Shared Folders**: Allow seamless file transfer between host and guest
- **Improved Mouse Integration**: Provides smoother mouse movement
- **Shared Clipboard**: Enable copy and paste operations between host and guest

---

## Linux Distributions

### Rocky Linux
- Founded in 2021 by Gregory Kurtzer
- Community-driven, enterprise-ready
- Based on Red Hat Enterprise Linux (RHEL)
- 10-year lifecycle for each release
- Free alternative to CentOS

### Ubuntu Linux
- Introduced in 2004 by Canonical
- Based on Debian
- User-friendly alternative
- New version every six months
- Wide community support

### Advantages of Ubuntu
1. User-Friendly Interface
2. Regular Updates
3. Strong Community Support
4. High Security
5. Customization
6. Free and Open-Source
7. Compatibility

---

## Network Concepts

### Network Adapter Options in VirtualBox

1. **NAT (Network Address Translation)**
   - Default network mode
   - VM shares the host's IP address
   - Best for basic internet access

2. **NAT Network**
   - Similar to NAT but allows VM-to-VM communication
   - Suitable for scenarios requiring VM-to-VM communication

3. **Bridged Adapter**
   - VM gets direct access to the physical network
   - Acts as another device on the network
   - Ideal for scenarios where the VM needs to be fully accessible

4. **Internal Network**
   - Creates a private network shared among VMs only
   - Suitable for creating isolated network environments

5. **Host-Only Adapter**
   - VMs can communicate with the host and other VMs
   - Not with external networks
   - Useful for development environments

### Static IP vs Dynamic IP

#### Static IP Address
- Fixed IP address assigned manually
- Remains the same over time
- Ideal for servers, printers, and devices requiring constant access

#### Dynamic IP Address
- Assigned automatically by DHCP server
- Can change each time the device connects
- Suitable for general user devices

### Network Commands
- `ifconfig` - Display network interface information
- `ip addr` - Manage network interfaces and addresses
- `nmcli` - Display network interface information (after NetworkManager is installed)
- `route` - Display and manipulate routing table
- `netstat` - Display open and listening ports
- `ping` - Test network connectivity
- `traceroute` - Trace network path to a host
- `host` - Get host information
- `dig` - Perform DNS lookups
- `nslookup` - Lookup domain names and IP addresses
- `hostname` - Set or get the system hostname
- `ip link` - View and manage network links
- `ss` - Shows all listening TCP and UDP connections

---

## Hostname and FQDN

### What is a Hostname?
A hostname is a name given to a computer or device on a network, used to uniquely identify the device.

### Types of Hostnames
1. **Static Hostname**: Permanent name assigned to a machine
2. **Transient Hostname**: Can change frequently, usually assigned by DHCP server
3. **Pretty Hostname**: User-friendly version, can include special characters and spaces

### Fully Qualified Domain Name (FQDN)
A complete domain name that specifies an exact location in the DNS hierarchy.

**Structure:**
- **Subdomain**: Name of the individual device or service (e.g., `shaserver`)
- **Domain Name**: Sequence of labels identifying the domain (e.g., `bungkus.org`)
- **Top-Level Domain (TLD)**: Last segment (e.g., `.com`, `.org`, `.net`)

**Example:** `shaserver.bungkus.org`

---

## Linux Commands

### Common Commands

| Command | Description | Example |
|---------|-------------|---------|
| `cd` | Change directory | `cd /etc/network` |
| `ls` | List directory contents | `ls -l /etc/network` |
| `pwd` | Print working directory | `pwd` |
| `mkdir` | Create a new directory | `mkdir /var/log/Bungkus` |
| `mv` | Move or rename files/directories | `mv /var/log/Bungkus /var/log/NewYear` |
| `cp` | Copy files/directories | `cp /var/log/NewYear /var/log/NewYear.backup` |
| `rmdir` | Remove an empty directory | `rmdir /var/log/NewYear` |
| `rm` | Remove files/directories | `rm /var/log/network/messages.old` |
| `grep` | Search for a pattern in file | `grep eth0 /usr/share/man/` |
| `man` | Display the manual page | `man ip addr` |
| `history` | List previously executed commands | `history` |
| `clear` | Clear the terminal screen | `clear` |
| `echo` | Print text to the terminal | `echo "Hello world!"` |
| `exit` | Log out of the current shell | `exit` |
| `reboot` | Reboots the system | `reboot` |
| `file` | Checks a file's type | `file document.jpg` |
| `locate` | Find a file | `locate document.jpg` |
| `sudo find` | Another method to find a file | `sudo find / -name README` |
| `sudo` | Execute commands as root | `sudo dnf update` |
| `su` | Switch user | `su – root` |
| `nano` | Simple text editor | `nano /etc/network/interfaces` |
| `touch` | Creates a new empty file | `touch fileText1.txt` |
| `cat` | Display file contents | `cat /usr/share/man/` |
| `tail` | Display last lines of a file | `tail /usr/share/man/` |

### Linux Shell
The default shell program used when the user logs in. Common shells:
- **bash (Bourne Again Shell)**: Most common and widely used
- **zsh (Z shell)**: Known for command-line history, tab completion, and spell checking
- **sh (Bourne Shell)**: Original Unix shell
- **csh (C Shell)**: Based on C programming language
- **fish (Friendly Interactive Shell)**: Newer, easier to use

### Standard Streams

#### Standard Input (stdin)
- Default source from which a program reads its data
- By default, it's the keyboard
- Can redirect using the `<` operator

#### Standard Output (stdout)
- Default destination where a program writes its results
- By default, it's the terminal
- Can redirect using the `>` operator

#### Standard Error (stderr)
- Default destination for error messages and diagnostic information
- By default, it's also the terminal
- Can redirect using the `2>` operator

### IO Redirection Commands

| Command | Description | Example |
|---------|-------------|---------|
| `cmd < file` | Input of cmd is taken from a file | `grep pattern < file.txt` |
| `cmd > file` | Standard output redirected to file (overwrites) | `ls > directory_listing.txt` |
| `cmd 2>&1` | stderr redirected to same place as stdout | - |
| `cmd1 <(cmd2)` | Output of cmd2 is used as input file for cmd1 | `wc -l <(ps aux)` |
| `cmd > /dev/null` | Discards the stdout | `long_running_command > /dev/null &` |
| `cmd &> file` | Every output redirected to file | `command_that_might_fail &> combined_output.txt` |
| `cmd 1>&2` | stdout redirected to same place as stderr | - |
| `cmd >> file` | Appends stdout to end of file | - |
| `<<` | Here-string redirection | - |

### Pipes
The vertical bar (`|`) acts as a conduit between programs. The output of the first command is fed into the input of the second one.

**Example:** `ps aux | grep "apache"`

### Nano Shortcuts

| File Operations | Description |
|-----------------|-------------|
| Ctrl + O | Save the file |
| Ctrl + X | Exit Nano (prompt to save if modified) |
| Ctrl + R | Read a file into the current buffer |
| Ctrl + J | Justify the current paragraph |

| Navigation | Description |
|------------|-------------|
| Ctrl + Y | Scroll up one page |
| Ctrl + V | Scroll down one page |
| Alt + \ | Go to a specific line number |
| Alt + , | Go to the beginning of the current line |
| Alt + . | Go to the end of the current line |

| Editing | Description |
|---------|-------------|
| Ctrl + K | Cut/delete from cursor position to end of line |
| Ctrl + U | Uncut/restore the last cut text |
| Ctrl + 6 | Mark a block of text for copying or cutting |
| Alt + 6 | Copy the marked block of text |

| Search and Replace | Description |
|-------------------|-------------|
| Ctrl + W | Search for a string in the text |
| Alt + W | Search and replace a string in the text |
| Alt + R | Repeat the last search |

---

## Users and Groups

### User Management Commands

| Command | Description | Example |
|---------|-------------|---------|
| `who` | Show who is currently logged in | `who` |
| `whoami` | Provides information about the currently logged-in user | `whoami` |
| `sudo useradd username` | Create a new user account | `sudo useradd batman` |
| `sudo passwd username` | Add a password to the newly created account | `sudo passwd batman` |
| `sudo groupadd groupname` | Create a new group | `sudo groupadd marvels` |
| `sudo usermod -aG GROUPNAME USERNAME` | Add existing user to specified group | `sudo usermod -aG Rangers batman` |
| `sudo userdel username` | Removes the user account | `sudo userdel batman` |
| `sudo groupdel groupname` | Removes the group | `sudo groupdel marvels` |
| `sudo userdel -r username` | Delete user account including home directory | `sudo userdel -r batman` |
| `last` | Show recent login history of users | `last` |
| `finger` | Display information about all users currently logged in | `finger` |
| `finger username` | Provide information about specified user | `finger batman` |
| `sudo passwd -l username` | Lock the password of specified user | `sudo passwd -l batman` |
| `su – username` | Switch to another user account with user's environment | `su – batman` |
| `tail -l /etc/passwd` | Check on the created users | `tail -l /etc/passwd` |
| `tail -l /etc/shadow` | Check on the created users with encrypted password | `tail -l /etc/shadow` |
| `cat /etc/group` | Check on the created groups | `cat /etc/group` |

### Superuser (root)
In Linux, a superuser is a user account with the highest level of privileges, usually called `root`. It has unrestricted access to all files, directories, and commands on the system.

### sudo vs su

**sudo (superuser do)**
- Allows users to execute commands with elevated privileges
- More secure approach
- Grants specific commands temporary root access without changing user

**su (substitute user)**
- Switches to another user account, including the superuser
- Switches you entirely to the root user
- Grants all powers but potentially exposing the system to wider risks

### /etc/passwd Format
Each line represents a user account with seven fields separated by colons:

`batman:x:1001:1001:Batman:/home/batman:/bin/bash`

1. **Username**: "batman"
2. **Password**: "x" (password stored in /etc/shadow)
3. **User ID (UID)**: 1001
4. **Group ID (GID)**: 1001
5. **GECOS (Comment)**: "Batman"
6. **Home Directory**: "/home/batman"
7. **Login Shell**: "/bin/bash"

### /etc/shadow Format
Each line corresponds to a user with nine fields separated by colons:

`batman:$6$SaltString$EncryptedPassword:18595:0:99999:7:::`

1. **Username**: "batman"
2. **Encrypted Password**: Begins with "$" followed by encryption algorithm
3. **Last Password Change**: Number of days since January 1, 1970
4. **Minimum Password Age**: Minimum days before password can be changed
5. **Maximum Password Age**: Maximum days a password is valid
6. **Password Warning Period**: Days before expiration to start warning
7. **Inactive Account Expiration**: (empty means won't expire)
8. **Reserved Field**: (empty, available for future use)

### /etc/group Format
Each line represents a group with four fields separated by colons:

`superHeros:x:1004:batman,wonderwoman,superman`

1. **Group Name**: "superHeros"
2. **Password**: "x" (no password required for group membership)
3. **Group ID (GID)**: 1004
4. **Member List**: "batman,wonderwoman,superman"

---

## Permissions and Ownership

### Three Types of Permissions
- **Read (r)**: Allows users to view the file or directory contents
- **Write (w)**: Allows users to modify the file or directory contents
- **Execute (x)**: Allows users to run executable files or access directories

### Permission Values

| Value | Access Right |
|-------|--------------|
| 0 | No permission (---) |
| 1 | Execute only (--x) |
| 2 | Write only (-w-) |
| 3 | Write and execute (-wx) |
| 4 | Read-only (r--) |
| 5 | Read and execute (r-x) |
| 6 | Read and write (rw-) |
| 7 | Read, write, and execute (rwx) |

### Permission Representation
Permissions are represented by a string of nine characters:
- First character: File type (`d` for directory, `-` for regular file)
- Remaining eight: Owner, group, and others permissions

**Example:** `-rw-r--r--`
- Regular file with read and write for owner, read for group and others

### Ownership Components
- **u (user)**: Owner of the file or directory
- **g (group)**: Primary group associated with the file
- **o (others)**: All users who are not the owner or part of the primary group
- **a (all)**: All users, including owner, group members, and others

### Permission Commands

| Command | Description | Example |
|---------|-------------|---------|
| `chmod` | Modifies file's read, write, and execute permissions | `chmod 755 filename.txt` |
| `chown` | Changes file ownership | `chown batman myfile` |
| `chgrp` | Changes group ownership | `chgrp marvels mydir` |

### Viewing Permissions

#### `ls -l` Command
Most commonly used method:

```
-rw-r--r-- 1 user group 1024 Oct 27 10:15 filename.txt
```

**Breakdown:**
1. **Permissions**: `-rw-r--r--`
2. **Number of Links**: `1`
3. **Owner**: `user`
4. **Group**: `group`
5. **Size**: `1024`
6. **Date and Time**: `Oct 27 10:15`
7. **Filename**: `filename.txt`

#### `stat` Command
Provides more detailed information:

```
File: filename.txt
Size: 1024
Type: regular file
Mode: -rw-r--r--
UID: 1000
GID: 1000
```

### Default Permissions
- **Directories**: 755 (owner full access, group and others read and execute)
- **Files**: 644 (owner read and write, group and others read only)

### Permission Examples

1. **Allow everyone to read a file:**
   ```bash
   chmod a+r filename.txt
   ```

2. **Grant write access to the group for a directory:**
   ```bash
   chmod g+w bungkus
   ```

3. **Make a directory executable:**
   ```bash
   chmod +x directory_name
   ```

4. **Revoke all permissions for others:**
   ```bash
   chmod o-rwx directory_name
   ```

5. **Add execute permission to user:**
   ```bash
   chmod u+x file1.txt
   ```

---

## DNS (Domain Name System)

### What is DNS?
DNS (Domain Name System) is a hierarchical and decentralized naming system used to translate human-readable domain names into IP addresses.

### Key Points
- **Translation**: Converts domain names to IP addresses
- **Hierarchy**: Structured in a tree format with domains and subdomains
- **Decentralized**: Managed across multiple servers globally

### Ports Associated with DNS
- **TCP/UDP 53**

### BIND9 (Berkeley Internet Name Domain)
Powerful DNS server software commonly implemented on Linux.

### Key Files and Configuration

#### named.conf
Main configuration file for BIND9 DNS server.

#### Forward Lookup Zone
Maps domain names to IP addresses.

#### Reverse Lookup Zone
Maps IP addresses back to domain names.

### DNS Configuration Steps

1. Install BIND9:
   ```bash
   sudo dnf install -y bind bind-utils
   ```

2. Enable and start the service:
   ```bash
   sudo systemctl enable named --now
   sudo systemctl start named
   ```

3. Configure /etc/named.conf:
   - Allow port 53 for all devices
   - Create forward and reverse lookup zones

4. Create zone files:
   - Forward zone file: `fwd.bungkus.org.db`
   - Reverse zone file: `rvs.200.168.192.db`

5. Check configuration:
   ```bash
   named-checkconf
   named-checkzone fwd.bungkus.org.db /var/named/fwd.bungkus.org.db
   ```

6. Configure firewall:
   ```bash
   sudo firewall-cmd --permanent --add-port=53/udp
   sudo firewall-cmd --permanent --add-port=53/tcp
   sudo firewall-cmd --reload
   ```

### Testing DNS

#### NSLOOKUP
```bash
nslookup shaserver.bungkus.org
```

#### Ping
```bash
ping shaserver.bungkus.org
```

#### DIG
```bash
dig shaserver.bungkus.org
```

---

## DHCP (Dynamic Host Configuration Protocol)

### What is DHCP?
DHCP is an automated network protocol that assigns IP addresses and other network settings to devices on a network.

### Main Components
1. **Client-Server Model**: DHCP server manages a pool of IP addresses
2. **Automatic IP Assignment**: Devices request IP addresses automatically
3. **IP Lease**: Leases act like temporary rentals for IP addresses

### Benefits
- **Reduced Errors**: Eliminates manual configuration errors
- **Efficient Management**: Centralized IP address management
- **Scalability**: Easy to add new devices

### Ports Associated with DHCP
- **UDP 67 & 68**

### DHCP Configuration Steps

1. Install DHCP server:
   ```bash
   dnf install -y dhcp-server
   ```

2. Configure /etc/dhcp/dhcpd.conf:
   ```bash
   default-lease-time 900;
   max-lease-time 10800;
   authoritative;
   subnet 192.168.200.0 netmask 255.255.255.0 {
       range 192.168.200.80 192.168.200.90;
       option routers 192.168.200.1;
       option subnet-mask 255.255.255.0;
       option domain-name-servers 192.168.200.4 8.8.8.8;
   }
   ```

3. Enable and start service:
   ```bash
   sudo systemctl enable --now dhcpd.service
   sudo systemctl start dhcpd
   ```

4. Configure firewall:
   ```bash
   sudo firewall-cmd --permanent --add-service=dhcp
   sudo firewall-cmd --reload
   ```

---

## FTP (File Transfer Protocol)

### What is FTP?
FTP is a standard network protocol used to transfer files from one host to another over a TCP-based network.

### Key Components
1. **FTP Client**: Software that initiates file transfers
2. **FTP Server**: Software that responds to FTP client requests

### Secure FTP Variants
1. **FTPS (FTP Secure)**: Uses SSL/TLS to encrypt control and/or data channels
2. **SFTP (SSH File Transfer Protocol)**: Runs over SSH protocol

### Advantages
- **Efficiency**: Suitable for transferring large files
- **Resume Capability**: Can resume interrupted transfers
- **Support**: Widely supported across platforms

### Disadvantages
- **Security**: Basic FTP is not encrypted
- **Complexity**: More complex to set up than modern alternatives

### Ports Associated with FTP
- **TCP 20 & 21**

### FTP Server Configuration (vsftpd)

1. Install vsftpd:
   ```bash
   sudo dnf -y install vsftpd
   ```

2. Enable and start service:
   ```bash
   sudo systemctl enable vsftpd
   sudo systemctl start vsftpd
   ```

3. Configure /etc/vsftpd/vsftpd.conf:
   - Disable anonymous access
   - Enable local user access
   - Allow file uploads
   - Configure SSL/TLS settings

4. Configure SELinux:
   ```bash
   sudo setsebool -P ftpd_full_access on
   ```

5. Configure firewall:
   ```bash
   sudo firewall-cmd --permanent --add-service=ftp
   sudo firewall-cmd --reload
   ```

### FTP Client Commands

| Command | Description |
|---------|-------------|
| `ls -l` | List files on server |
| `cd directory` | Change directory on server |
| `lcd directory` | Change directory on local client |
| `put file` | Upload a single file |
| `mput file1 file2` | Upload multiple files |
| `get file` | Download a single file |
| `mget file1 file2` | Download multiple files |
| `rm file` | Delete file on server |
| `mrm file1 file2` | Delete multiple files on server |
| `mkdir directory` | Create directory on server |
| `rmdir directory` | Remove directory on server |
| `!command` | Execute command on local client |

---

## SSL/TLS

### What is SSL/TLS?
Secure Sockets Layer (SSL) and Transport Layer Security (TLS) are cryptographic protocols designed to provide secure communication.

### FTP with SSL (FTPS)
Extension to FTP that adds support for TLS/SSL, ensuring data and login credentials are secure during transmission.

### Key Features
1. **Encryption and Security**: Encrypts data to prevent unauthorized access
2. **Authentication**: Can use client certificates for authentication
3. **Compatibility**: Retains compatibility with existing FTP clients/servers
4. **Data Integrity**: Ensures files are not tampered with during transmission

### OpenSSL Installation
```bash
sudo dnf install openssl
```

### Creating SSL Certificate
```bash
sudo openssl req -x509 -nodes -keyout /etc/ssl/vsftpd/vsftpd-selfsigned.pem -out /etc/ssl/vsftpd/vsftpd-selfsigned.pem -days 365 -newkey rsa:2048
```

### SSL Configuration in vsftpd.conf
```bash
ssl_enable=YES
ssl_tlsv1_2=YES
ssl_sslv2=NO
ssl_sslv3=NO
rsa_cert_file=/etc/ssl/vsftpd/vsftpd-selfsigned.pem
rsa_private_key_file=/etc/ssl/vsftpd/vsftpd-selfsigned.pem
allow_anon_ssl=NO
force_local_data_ssl=YES
force_local_logins_ssl=YES
ssl_ciphers=HIGH
require_ssl_reuse=NO
```

### Firewall Configuration for SSL
```bash
sudo firewall-cmd --permanent --add-port=990/tcp
sudo firewall-cmd --permanent --add-port=40000-40001/tcp
sudo firewall-cmd --reload
```

---

## NFS (Network File System)

### What is NFS?
Network File System (NFS) is a distributed file system protocol allowing users on client computers to access files over a network as if they were local.

### Key Features
1. **Transparency**: Users interact with remote files as if they were local
2. **Scalability**: Can handle numerous clients
3. **Interoperability**: Supports various operating systems
4. **Access Control**: Employs authentication and permissions
5. **Performance**: Includes caching features

### Common Use Cases
1. **Home Directories**: Centralized user home directories
2. **Shared Storage**: Facilitating shared access in collaborative environments
3. **Backup Solutions**: Centralizing backup data
4. **Media Streaming**: Serving media files from a central server

### NFS Server Configuration

1. Install NFS server:
   ```bash
   sudo dnf install nfs-utils
   ```

2. Enable and start service:
   ```bash
   sudo systemctl enable nfs-server --now
   sudo systemctl start nfs-server
   ```

3. Create shared directory:
   ```bash
   sudo mkdir /var/nfs/general -p
   sudo chown nobody:nobody /var/nfs/general/
   ```

4. Configure /etc/exports:
   ```
   /var/nfs/general 192.168.200.80(rw, sync, no_subtree_check)
   ```

5. Export the share:
   ```bash
   sudo exportfs -arv
   ```

6. Configure firewall:
   ```bash
   sudo firewall-cmd --permanent --add-service={nfs,nfs3,rpc-bind,mountd}
   sudo firewall-cmd --reload
   ```

### NFS Client Configuration

1. Install NFS client:
   ```bash
   sudo apt install nfs-common
   ```

2. Create mount point:
   ```bash
   sudo mkdir /nfs/Shared_From_Server -p
   ```

3. Mount the share:
   ```bash
   sudo mount 192.168.200.4:/var/nfs/general /nfs/Shared_From_Server
   ```

4. Configure permanent mount in /etc/fstab:
   ```
   192.168.200.4:/var/nfs/general /nfs/Shared_From_Server nfs auto,nofail,noatime,nolock,intr,tcp,actimeo=1800 0 0
   ```

---

## SSH (Secure Shell)

### What is SSH?
SSH (Secure Shell) is a cryptographic network protocol used for secure communication over an unsecured network.

### Key Features
1. **Encryption**: Uses strong encryption to protect data
2. **Authentication**: Supports password-based and public key authentication
3. **Data Integrity**: Uses cryptographic hash functions to detect tampering
4. **Port Forwarding**: Can tunnel network connections through encrypted channels
5. **File Transfer**: Includes SCP and SFTP for secure file transfers

### Common Use Cases
- **Remote Administration**: Manage and configure servers remotely
- **Secure File Transfers**: SCP and SFTP for secure file transfer
- **Tunneling**: Tunnel network connections securely

### Ports Associated with SSH
- **TCP 22**

### SSH Configuration

1. Install SSH (usually pre-installed):
   ```bash
   sudo dnf install openssh-server
   ```

2. Configure /etc/ssh/sshd_config:
   ```bash
   PermitRootLogin no
   Port 22
   ```

3. Enable and start service:
   ```bash
   sudo systemctl enable sshd
   sudo systemctl start sshd
   ```

4. Configure firewall:
   ```bash
   sudo firewall-cmd --zone=public --permanent --add-service=ssh
   sudo firewall-cmd --permanent --add-port=22/tcp
   sudo firewall-cmd --reload
   ```

### SSH Usage
```bash
ssh username@192.168.200.4
```

---

## Firewalld

### What is Firewalld?
Firewalld is a firewall management tool for Linux that works with either nftables or iptables, using zones and services to define firewall rules.

### Zones
Zones are security levels assigned to different parts of a network:

| Zone | Trust Level | Purpose |
|------|-------------|---------|
| Drop | Lowest | Blocks all incoming and outgoing traffic |
| Block | Very Low | Blocks all incoming traffic, allows outgoing |
| Public | Low | Allows public services like HTTP/HTTPS |
| External | Low-Medium | For network gateways/NAT firewalls |
| Internal | Medium | For trusted internal networks |
| DMZ | Medium-High | For servers exposed to internet |
| Work | High | For trusted work networks |
| Home | High | For home environments |
| Trusted | Highest | Trusts all machines in the network |

### Firewalld Commands

#### Status and Information
```bash
sudo systemctl status firewalld
sudo firewall-cmd --get-default-zone
sudo firewall-cmd --get-active-zones
sudo firewall-cmd --zone=public --list-all
```

#### Add/Remove Services
```bash
# Add service
sudo firewall-cmd --zone=public --add-service=ssh
sudo firewall-cmd --reload

# Remove service
sudo firewall-cmd --zone=public --remove-service=ssh
sudo firewall-cmd --reload
```

#### Add/Remove Ports
```bash
# Add port
sudo firewall-cmd --permanent --add-port=22/tcp
sudo firewall-cmd --reload

# Remove port
sudo firewall-cmd --permanent --remove-port=22/tcp
sudo firewall-cmd --reload
```

### Rich Rules
Allows complex firewall rules for granular control:

```bash
sudo firewall-cmd --permanent --add-rich-rule='rule family=ipv4 source address=192.168.200.80 service name=ssh accept'
sudo firewall-cmd --reload
```

### Cockpit (Web-based GUI)
```bash
sudo systemctl enable --now cockpit.socket
```
Access at: `https://server-ip:9090`

---

## ACL (Access Control Lists)

### What are ACLs?
ACLs offer a more granular way to manage file and directory permissions compared to standard chmod approach.

### Advantages over chmod
1. **Granular Permissions**: Assign permissions to specific users and groups
2. **Inheritance**: ACLs can be inherited by subdirectories and files
3. **Flexibility**: Create more intricate permission schemes

### Comparison: chmod vs ACLs

| Feature | chmod | ACLs |
|---------|-------|------|
| Permission Type | User, Group, Other | User, Group, Other, Specific Users/Groups |
| Granularity | Limited (3 permissions for 3 entities) | Granular (specific permissions for users/groups) |
| Inheritance | Yes (simple) | Yes (can be complex) |

### ACL Commands

| Command | Description | Example |
|---------|-------------|---------|
| `setfacl -m u:username:permissions file` | Set ACL for user | `setfacl -m u:Joy:r CyberTech.txt` |
| `getfacl file` | Get ACL of file | `getfacl CyberTech.txt` |
| `setfacl -m mask:permissions file` | Set ACL mask | `setfacl -m mask:r CyberTech.txt` |

### ACL Mask
The mask defines the maximum permissions that any ACL entry can grant. It acts as a "ceiling" for individual ACL entries.

### Example: Setting ACL for File
```bash
# Create file and set basic permissions
touch CyberTech.txt
chmod 640 CyberTech.txt

# Grant read permission to specific user
setfacl -m u:Joy:r CyberTech.txt

# Verify ACL
getfacl CyberTech.txt
```

### Example: Setting ACL for Directory
```bash
# Create directory and set basic permissions
mkdir ITsec
chmod 750 ITsec/

# Grant read and execute permission to specific user
setfacl -m u:Joy:rx ITsec/

# Verify ACL
getfacl ITsec/
```

---

## Syslog

### What is Syslog?
Syslog is a standard protocol used for message logging, enabling the logging of different types of messages such as system events, security incidents, and application errors.

### Components
1. **Syslog Clients**: Devices or applications that generate log messages
2. **Syslog Server**: Central system that collects, stores, and processes log messages
3. **Syslog Messages**: Actual log messages with timestamp, hostname, and content

### Benefits
1. **Centralized Logging**: Aggregates logs from multiple sources
2. **Improved Security**: Helps identify and respond to security incidents
3. **Simplified Troubleshooting**: Facilitates quicker problem resolution
4. **Compliance**: Assists in meeting regulatory requirements

### Ports Associated with Syslog
- **TCP/UDP 514**

### Syslog Server Configuration (rsyslog)

1. Install rsyslog:
   ```bash
   sudo dnf install rsyslog
   ```

2. Enable and start service:
   ```bash
   sudo systemctl start rsyslog
   sudo systemctl enable rsyslog
   ```

3. Configure /etc/rsyslog.conf:
   ```bash
   # Uncomment for UDP
   module(load="imudp")
   input(type="imudp" port="514")

   # Uncomment for TCP
   module(load="imtcp")
   input(type="imtcp" port="514")

   # Template for incoming logs
   $template IncomingLogs,"/var/log/remote-logs/%HOSTNAME%/%PROGRAMNAME%.log"
   *.* ?IncomingLogs
   ```

4. Create log directory:
   ```bash
   sudo mkdir /var/log/remote-logs
   ```

5. Validate configuration:
   ```bash
   sudo rsyslogd -N1 -f /etc/rsyslog.conf
   ```

6. Restart service:
   ```bash
   sudo systemctl restart rsyslog
   ```

7. Configure firewall:
   ```bash
   sudo firewall-cmd --permanent --add-port=514/tcp
   sudo firewall-cmd --permanent --add-port=514/udp
   sudo firewall-cmd --reload
   ```

### Syslog Client Configuration

1. Configure /etc/rsyslog.conf:
   ```bash
   *.* @@192.168.200.4:514
   ```

2. Restart service:
   ```bash
   sudo systemctl restart rsyslog
   ```

### Viewing Logs
```bash
# View log directories
sudo ls /var/log/remote-logs/

# View specific log file
sudo cat /var/log/remote-logs/shaserver/sudo.log
```

---

## Additional Concepts

### Sudoers
In Linux, the sudoers command is used to manage user permissions for executing administrative tasks with sudo.

### SELinux (Security-Enhanced Linux)
A mandatory access control (MAC) system built into the Linux kernel, providing an extra layer of security by enforcing restrictions on system resources.

### Check SELinux Status
```bash
sudo sestatus
```

### Set SELinux Boolean
```bash
sudo setsebool -P ftpd_full_access on
```

---

## Summary of Important Ports

| Service | Protocol | Port |
|---------|----------|------|
| DNS | TCP/UDP | 53 |
| DHCP | UDP | 67, 68 |
| FTP | TCP | 20, 21 |
| FTPS (SSL) | TCP | 990 |
| NFS | TCP | 2049 |
| SSH | TCP | 22 |
| Syslog | TCP/UDP | 514 |
| Cockpit | TCP | 9090 |

---

## Important File Locations

| File | Purpose |
|------|---------|
| /etc/passwd | User account information |
| /etc/shadow | Encrypted user passwords |
| /etc/group | Group information |
| /etc/hostname | System hostname |
| /etc/hosts | Hostname to IP address mapping |
| /etc/NetworkManager/system-connections/ | Network connection configurations |
| /etc/named.conf | BIND9 DNS configuration |
| /var/named/ | DNS zone files |
| /etc/dhcp/dhcpd.conf | DHCP server configuration |
| /etc/vsftpd/vsftpd.conf | FTP server configuration |
| /etc/exports | NFS export configuration |
| /etc/ssh/sshd_config | SSH server configuration |
| /etc/rsyslog.conf | Syslog configuration |
| /etc/fstab | File system mount points |

---

## Notes on System Administration

### Best Practices
1. Always backup configuration files before modifying
2. Use `sudo` carefully and only when necessary
3. Regularly update and upgrade the system
4. Monitor system logs for issues
5. Implement proper firewall rules
6. Use strong passwords and secure authentication methods
7. Document all changes made to the system

### Troubleshooting Tips
1. Check service status: `sudo systemctl status service-name`
2. Review logs: `sudo journalctl -u service-name`
3. Verify network connectivity: `ping`, `traceroute`
4. Check firewall rules: `sudo firewall-cmd --list-all`
5. Validate configuration files
6. Test changes in a non-production environment first

---

*End of Notes*
