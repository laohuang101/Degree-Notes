# System Hardening and Policy-Based Management Notes

**Module:** CT106-3-2 (Version VE1)
**Topic:** System Hardening, Policy-Based Management, Security Policies
**Source:** Lecture Slides 20260306 & 20260307

---

## Table of Contents

1. [Security Policy Components](#security-policy-components)
2. [Policy-Based Management & FCAPS](#policy-based-management--fcaps)
3. [Acceptable Use Policy](#acceptable-use-policy)
4. [User Account Policy](#user-account-policy)
5. [System Hardening Checklist](#system-hardening-checklist)

---

## Security Policy Components

A comprehensive security policy consists of five essential components that work together to create a defense-in-depth strategy.

### Overview Table

| Component | Purpose | Key Functions | Technical Implementation |
|-----------|---------|---------------|-------------------------|
| **Access Policy** | Defines access rights and privileges | Establish boundaries for resource access, prevent unauthorized access | File permissions, ACLs, firewalls, network segmentation |
| **Accountability Policy** | Defines responsibilities | Creates audit trails, enables incident investigation, promotes individual responsibility | System logging, audit trails, change management logs |
| **Authentication Policy** | Establishes trust via verification | Verifies identity before granting access, prevents impersonation | Passwords, MFA, SSH keys, smart cards, biometrics |
| **Privacy Policy** | Sets monitoring expectations | Protects user privacy, complies with legal requirements, balances security with privacy | Email monitoring policies, file access logging, GDPR compliance |
| **Technology Policy** | Guidelines for systems | Ensures consistent security configurations, guides procurement, establishes hardening standards | CIS benchmarks, security baselines, procurement requirements |

### Detailed Description

#### 1. Access Policy

The access policy defines who can access what resources within the organization. It establishes clear boundaries for users and systems, preventing unauthorized access while enabling legitimate work. This policy provides the legal and procedural basis for all access control decisions.

**Key Requirements:**
- Users should only have access to services they are specifically authorized to use
- All remote connections must be authenticated
- Strict control over access to system configuration files
- Principle of least privilege enforcement

**Technical Implementation:**
- File system permissions (chmod, chown)
- Access Control Lists (ACLs) for granular control
- Network firewalls and port restrictions
- VPN and remote access controls
- Application-level permissions

#### 2. Accountability Policy

The accountability policy defines the responsibilities of users, operating staff, and management. It ensures that all actions can be traced to specific individuals, creating a foundation for security auditing and incident response.

**Key Requirements:**
- Clear assignment of duties and responsibilities
- Maintenance of audit trails for all security events
- System administrators must log all configuration changes
- Individual responsibility for security actions

**Technical Implementation:**
- System logging (syslog, auditd)
- Change management systems
- Authentication logging
- File access auditing
- Network traffic logging

#### 3. Authentication Policy

The authentication policy establishes trust by verifying user identity through multiple factors: something the user knows, has, or is. This is critical for preventing unauthorized access and impersonation attacks.

**Authentication Factors:**
- **Something you know:** Passwords, PINs
- **Something you have:** Security tokens, smart cards, mobile devices
- **Something you are:** Biometrics (fingerprint, retina)

**Key Requirements:**
- Multi-factor authentication for sensitive systems
- Strong password policies
- Regular credential updates
- Secure credential storage

**Technical Implementation:**
- SSH key-based authentication
- PAM (Pluggable Authentication Modules)
- LDAP/Kerberos integration
- MFA solutions (TOTP, hardware tokens)
- Password hashing with strong algorithms (bcrypt, Argon2)

#### 4. Privacy Policy

The privacy policy defines reasonable expectations for monitoring user activities, including email, file access, and other communications. It balances organizational security needs with employee privacy rights and ensures compliance with legal requirements.

**Key Requirements:**
- Clear disclosure of monitoring activities
- Limits on what can be monitored
- Compliance with privacy regulations (GDPR, etc.)
- Protection of personal information

**Technical Implementation:**
- Email monitoring policies (security purposes only)
- File access logging with privacy safeguards
- Data retention policies
- Encryption of sensitive logs

#### 5. Technology Policy

The technology policy provides guidelines for purchasing, configuring, and auditing computer systems. It ensures consistent security configurations across the organization and establishes standards for system hardening.

**Key Requirements:**
- All new systems must be hardened according to standards
- Procurement must include security requirements
- Regular security audits and assessments
- Standardized security configurations

**Technical Implementation:**
- CIS (Center for Internet Security) benchmarks
- Security baselines and hardening guides
- Automated configuration management
- Vulnerability scanning
- Penetration testing

### Interdependence and Defense in Depth

These five components work together to create a comprehensive security framework. The absence of any component creates gaps that attackers can exploit:

| Missing Component | Security Vulnerability Created |
|-------------------|-------------------------------|
| Access Policy | Cannot determine who should have access to what resources |
| Accountability Policy | Cannot trace security incidents to specific individuals |
| Authentication Policy | Impersonation attacks become easy |
| Privacy Policy | Legal liability, employee resistance, non-compliance |
| Technology Policy | Inconsistent security across systems, vulnerable configurations |

The **Defense in Depth** strategy places multiple defensive mechanisms at different levels (physical, network, host, application, data, user) to prevent, detect, and respond to threats. No single security measure is sufficient, and redundancy is essential for robust protection.

---

## Policy-Based Management & FCAPS

Policy-Based Management is a systematic approach to system administration where clear policies define goals, responses, and procedures. This is essential in organizations where multiple administrators cooperate, ensuring alignment with organizational objectives.

### The Philosophy

System administration involves:
- Putting together a network of computers
- Getting them to run applications
- Keeping them running in a dynamic world

**Key Insight:** System administration is as much about technology as it is about user behavior. It requires constant monitoring and rapid response to problems.

### FCAPS Framework

The OSI Network Management Model (FCAPS) standardizes management systems. It's used in NOCs, SOCs, and ITIL-aligned service management.

#### FCAPS Overview Table

| Component | Goal | Key Activities | Example Policies |
|-----------|------|----------------|------------------|
| **Fault Management** | Detect and correct network issues | Monitoring alerts, automatic alarms, root cause analysis, escalation | Alert thresholds, incident response procedures, notification policies |
| **Configuration Management** | Track device settings and changes | Network design, addressing, name resolution, service startup, user rights | Change management, backup policies, version control, documentation requirements |
| **Accounting Management** | Track resource usage and costs | Usage reports, billing support, capacity planning | Resource quotas, chargeback policies, usage limits |
| **Performance Management** | Monitor and evaluate system behavior | Performance monitoring, congestion avoidance, throughput optimization | SLA definitions, performance thresholds, capacity planning |
| **Security Management** | Protect from unauthorized access | Authentication, firewall management, log auditing, encryption | Access policies, incident response, encryption standards, security audits |

#### Detailed FCAPS Analysis

##### 1. Fault Management

**Purpose:** Detect faults or abnormal operation, isolate causes, and correct problems to return to normal state.

**Key Activities:**
- Monitoring alerts and logs
- Automatic alarms and notifications
- Root cause analysis
- Escalation processes

**Policies Required:**
- Alert thresholds and severity levels
- Response time requirements
- Escalation procedures
- Incident classification and prioritization

**Technical Implementation:**
- Monitoring tools (Nagios, Zabbix, Prometheus)
- Log aggregation (ELK Stack, Splunk)
- Alerting systems
- Automated recovery scripts

##### 2. Configuration Management

**Purpose:** Keep track of device settings, versions, and changes. Covers network structure, architecture, segmentation, addressing, and services.

**Key Activities:**
- Network design and documentation
- Addressing schemes
- Name resolution and directories
- Service configuration
- User rights and responsibilities
- Application limits
- Security and privacy settings

**Policies Required:**
- Change management procedures
- Documentation requirements
- Version control for configurations
- Approval processes for changes
- Backup and restore procedures

**Technical Implementation:**
- Configuration management tools (Ansible, Puppet, Chef)
- Version control systems (Git)
- Documentation platforms
- Network automation tools

##### 3. Accounting Management

**Purpose:** Track resource usage to understand costs or user behavior. Establish how to charge users for resource utilization.

**Key Activities:**
- Bandwidth usage reports
- Storage utilization tracking
- Application usage monitoring
- Billing support
- Cost allocation

**Policies Required:**
- Resource quotas and limits
- Chargeback mechanisms
- Usage reporting policies
- Budget allocation procedures

**Technical Implementation:**
- Usage monitoring tools
- Billing systems
- Resource tracking databases
- Reporting dashboards

##### 4. Performance Management

**Purpose:** Monitor and evaluate behavior of managed objects, assess effectiveness of communications, and verify if performance targets are met.

**Key Activities:**
- Performance monitoring
- Congestion detection and avoidance
- Throughput optimization
- Data loss minimization
- Capacity utilization analysis

**Policies Required:**
- SLA definitions and thresholds
- Performance baselines
- Capacity planning procedures
- Performance optimization guidelines

**Technical Implementation:**
- Performance monitoring tools
- Traffic analysis
- Capacity planning tools
- Performance testing

##### 5. Security Management

**Purpose:** Protect network from unauthorized access and attacks, implement security policies, ensure data integrity.

**Key Activities:**
- User authentication and authorization
- Firewall and antivirus management
- Log auditing and incident response
- Encryption key and certificate management
- Security policy implementation
- Security state analysis

**Policies Required:**
- Access control policies
- Encryption standards
- Incident response procedures
- Security audit requirements
- Vulnerability management policies

**Technical Implementation:**
- Firewalls and IPS/IDS
- Authentication systems (LDAP, Kerberos)
- Encryption (TLS, SSH)
- SIEM (Security Information and Event Management)
- Vulnerability scanners

### Security vs Usability Tradeoffs

**Tradeoff Analysis:**

| Security Measure | Benefit | Cost/Tradeoff |
|-----------------|---------|---------------|
| Strong passwords | Prevents brute force attacks | Harder to remember, users may write them down |
| MFA | Prevents credential theft | Additional step, requires tokens |
| Encryption | Protects data in transit | CPU overhead, key management complexity |
| Strict access controls | Limits unauthorized access | May impede legitimate work |
| Frequent password changes | Limits credential exposure | Users create simpler passwords |

**Key Insights:**
- More security = Less convenience
- Security adds management work (login IDs, passwords, audit logs)
- Packet filters and encryption consume CPU and memory
- Security can reduce network redundancy and load balancing flexibility

### Why Policy-Based Management?

**Benefits over reactive administration:**
1. **Consistency:** Standardized approaches across the organization
2. **Documentation:** Clear intent and procedures for all actions
3. **Preparedness:** Policies prepare for possible errors before they occur
4. **Alignment:** System operation aligned with organizational objectives
5. **Collaboration:** Essential when multiple administrators work together
6. **Accountability:** Clear responsibility assignment

**Implementation Requirements:**
- Clear expression of goals and responses
- Documentation of intent and procedure
- Mechanisms for monitoring compliance
- Regular policy reviews and updates
- User education and training

---

## Acceptable Use Policy

An Acceptable Use Policy (AUC) is critical for organizational security, legal protection, and operational efficiency. It defines appropriate technology use and sets clear expectations for employee behavior.

### Why AUC is Critical

| Aspect | Importance | Example |
|--------|------------|---------|
| **Security Protection** | Prevents employees from introducing security risks | Prohibiting personal USB drives prevents malware introduction |
| **Legal & Regulatory Compliance** | Demonstrates commitment to security, provides legal defense | AUC supports HIPAA, PCI DSS, and other regulatory compliance |
| **Operational Efficiency** | Reduces support calls, prevents resource abuse | Standardizing on approved browsers reduces support overhead |
| **Employee Education** | Sets clear expectations, promotes security culture | Warning about social engineering raises awareness |

### Key Elements of AUC

| Element | Description | Implementation |
|---------|-------------|----------------|
| **Application Restrictions** | Specify which applications can run on network PCs | Whitelist approved applications, block software installation |
| **Device Connection Policies** | Define permitted devices for LAN connections | Device registration, MAC address filtering, BYOD requirements |
| **Network Usage** | Define acceptable use of company networks | Prohibit streaming during work hours, bandwidth limits |
| **Authentication & Access** | Require logout when not in use, password requirements | Screen lock after inactivity, MFA requirements |
| **Communication Policies** | Define acceptable use of email and messaging | Prohibit sending confidential data to personal email |
| **Monitoring & Enforcement** | State monitoring occurs, define consequences | Clear violation procedures, disciplinary actions |

### BYOD Considerations

**BYOD Policy Requirements:**
- Device security standards (current OS, antivirus, encryption)
- Data protection measures (MDM, remote wipe, containerization)
- Access controls (network segmentation, authentication)
- Privacy protections (limits on monitoring, data separation)
- Compliance requirements (GDPR, industry regulations)

**Security Impact of BYOD:**
- Expanded attack surface with varying security postures
- Complicated device management and patch enforcement
- New vulnerabilities (insecure apps, public WiFi)
- Authentication and access challenges
- Data protection complexity

**Technical Controls for BYOD:**
- Mobile Device Management (MDM) enrollment
- Network segmentation (guest networks)
- Containerization for corporate data
- Remote wipe capabilities
- Certificate-based authentication

### Implementation Challenges

| Challenge | Description | Mitigation |
|-----------|-------------|------------|
| **User Resistance** | Users perceive policies as burdensome | Education, clear communication, show benefits |
| **BYOD Complexity** | Personal devices create security risks | MDM, network segmentation, clear requirements |
| **Compliance Enforcement** | Ensuring consistent policy application | Automated controls, regular audits, monitoring |
| **Privacy Concerns** | Monitoring vs employee privacy | Clear disclosure, limit monitoring to business needs |
| **Keeping Updated** | Technology and threats change rapidly | Regular policy reviews, agile update process |

### Implementation Strategy

1. **Risk Assessment**
   - Identify organizational-specific risks
   - Assess data sensitivity and regulatory requirements
   - Evaluate user needs and expectations

2. **Policy Development**
   - Involve stakeholders from IT, HR, Legal, and business units
   - Create clear, concise policies
   - Define enforcement mechanisms

3. **Communication**
   - Educate users about policy and reasons
   - Provide clear guidelines and procedures
   - Use multiple communication channels

4. **Training**
   - Conduct initial training sessions
   - Provide ongoing awareness programs
   - Use real-world examples and case studies

5. **Monitoring & Enforcement**
   - Monitor compliance with policies
   - Track security incidents
   - Apply policies consistently

6. **Continuous Improvement**
   - Review and update policies regularly
   - Gather user feedback
   - Adapt to changing threats and technologies

---

## User Account Policy

User account management and authentication are fundamental to system security. A comprehensive User Account Policy addresses the entire lifecycle of user access.

### User Account Lifecycle

| Phase | Process | Key Requirements |
|-------|---------|------------------|
| **Registration** | Formal procedure for granting new access | Manager approval, role-based access, initial credential setup |
| **Active Use** | Ongoing access management | Regular access reviews, privilege monitoring, policy compliance |
| **Deregistration** | Formal procedure for revoking access | Immediate access revocation, data handover, audit trail |

### Formal Procedures

#### 1. User Registration

**Requirements:**
- Manager approval for access requests
- Documentation of business justification
- Role-based access assignment
- Initial security training
- Credential distribution (secure method)

**Implementation:**
- Automated provisioning systems
- Integration with HR systems
- Ticket-based approval workflows
- Role templates and access groups

#### 2. User Deregistration

**Requirements:**
- Immediate access revocation upon termination
- Data handover procedures
- Account archival for audit purposes
- System cleanup (remove home directories, clean configurations)

**Implementation:**
- Automated deprovisioning scripts
- HR system integration for termination notifications
- Checklist for all systems and applications
- Audit logging of deprovisioning actions

#### 3. Access Rights Review

**Requirements:**
- Regular review of user access rights (quarterly or semi-annually)
- Manager confirmation of continued access needs
- Revocation of unnecessary privileges
- Documentation of review decisions

**Implementation:**
- Access review tools and reports
- Automated reminders to managers
- Workflow for approval/revocation
- Audit trail of reviews

### Password Policy

| Policy Element | Recommended Value | Rationale |
|----------------|-------------------|-----------|
| **Minimum Length** | 12-16 characters | Longer passwords resist brute force |
| **Complexity** | Mix of cases, numbers, symbols OR passphrases | Prevents dictionary attacks |
| **Expiration** | 90-180 days | Limits credential exposure if compromised |
| **History** | Prevent reuse of last 10 passwords | Prevents recycling of old passwords |
| **Account Lockout** | After 5-10 failed attempts | Prevents brute force attacks |
| **Recovery** | Secure reset process (multi-factor) | Prevents social engineering attacks |

### Password Vulnerabilities and Mitigations

| Vulnerability | Description | Mitigation |
|---------------|-------------|------------|
| **Weak Passwords** | Easily guessed or cracked passwords | Strong password requirements, password strength meters |
| **Password Sniffing** | Plaintext passwords captured on network | Use SSH, SSL/TLS, avoid telnet/FTP |
| **Brute Force Attacks** | Automated password guessing attempts | Account lockout, rate limiting, CAPTCHA |
| **Dictionary Attacks** | Using word lists to crack passwords | Password complexity, ban common passwords |
| **Password Reuse** | Same password across multiple accounts | Education, password managers, unique requirements |
| **Written Passwords** | Users writing down passwords | Password managers, passphrases that are memorable |

### Authentication Methods

#### Authentication Factors

| Factor Type | Examples | When to Use |
|-------------|----------|-------------|
| **Something you know** | Passwords, PINs | Standard authentication |
| **Something you have** | Security tokens, smart cards, mobile apps | MFA for sensitive systems |
| **Something you are** | Biometrics (fingerprint, retina) | High-security environments |

#### Multi-Factor Authentication (MFA)

**When MFA Should Be Required:**
- Remote access (VPN, remote desktop)
- Administrative access
- Access to sensitive data (financial, personal information)
- Privileged account access
- Cloud service access

**Implementation Options:**
- TOTP (Time-based One-Time Password) apps (Google Authenticator, Authy)
- Hardware tokens (YubiKey)
- SMS-based codes (less secure)
- Biometric authentication

### Privilege Management

#### Sudo vs Su Comparison

| Aspect | sudo | su |
|--------|------|-----|
| **Authentication** | User's password | Root password |
| **Scope** | Single command | Full shell session |
| **Logging** | Detailed audit logs | Limited logging |
| **Granularity** | Per-command control | All-or-nothing |
| **Security** | No root password distribution | Root password must be shared |
| **Recommended Use** | Yes | Limited |

**Best Practices:**
- Use sudo instead of direct root login
- Disable root account login (as in Ubuntu)
- Use the principle of least privilege
- Grant specific commands rather than full root access
- Regularly audit sudo permissions

#### Root Account Handling

**Security Guidelines:**
- Disable direct root login when possible
- Never share root passwords
- Use sudo for administrative tasks
- Implement separate admin accounts for each administrator
- Log all privileged activities

**Implementation:**
```
# Disable root login in SSH config
PermitRootLogin no

# Use sudo for admin tasks
sudo /etc/sudoers configuration
```

### Mobile Computing and Teleworking

**Security Requirements:**
- Encrypted devices (full disk encryption)
- Secure VPN access for network connections
- MFA for remote access
- Approved devices only
- Regular security updates
- Secure WiFi usage (no public WiFi without VPN)

**Policy Elements:**
- Device registration and approval
- Security software requirements
- Data protection guidelines
- Incident reporting procedures
- Physical security requirements

### Common Challenges and Mitigations

| Challenge | Description | Mitigation |
|-----------|-------------|------------|
| **User Resistance** | Users find policies burdensome | Education, demonstrate value, make security easy |
| **Password Fatigue** | Too many passwords to remember | Password managers, SSO, passphrases |
| **Administrative Overhead** | Password resets, account lockouts | Self-service tools, automated processes |
| **Social Engineering** | Users tricked into revealing credentials | Training, verification procedures, clear policies |
| **Credential Sharing** | Users sharing passwords | Technical controls, monitoring, education |

---

## System Hardening Checklist

System hardening involves implementing technical controls to reduce vulnerabilities. This checklist covers essential hardening measures for Linux-based server environments.

### Access Control and File Permissions

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **File Permissions** | Unauthorized access to sensitive files | Minimum necessary permissions | Use `chmod`, `chown`, limit world-writable files | `find / -perm -002 -type f` |
| **SUID/SGID Files** | Privilege escalation attacks | Minimize SUID/SGID executables | `chmod -s` on unnecessary binaries | `find / -perm -4000 -o -perm -2000` |
| **Home Directory Permissions** | User data exposure | Restrict home directory access | `chmod 700 /home/*` | `ls -ld /home/*` |
| **Temporary Files** | Information disclosure | Secure temp directories | Use `/tmp` with proper permissions, clean regularly | Check `/tmp` permissions |
| **Critical Files** | Configuration tampering | Restrict access to config files | `/etc` permissions 750, root ownership | `ls -ld /etc` |

**Technical Commands:**
```bash
# Find and fix world-writable files
find / -perm -002 -type f -exec chmod o-w {} \;

# Find SUID files
find / -perm -4000 -type f

# Set secure home directory permissions
chmod 700 /home/username
```

### Network Security

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **Open Ports** | Unnecessary services exposed | Close unused ports | `netstat`, `ss`, firewall rules | `ss -tulpn` |
| **Telnet/FTP** | Plaintext passwords | Prohibit, use SSH | Disable services, install SSH | `systemctl status telnet` |
| **SSH Configuration** | Brute force attacks | Secure SSH settings | Disable root login, key-based auth | Check `/etc/ssh/sshd_config` |
| **Firewall** | Unauthorized network access | Default deny, allow specific | `iptables`, `ufw`, `firewalld` | `iptables -L -n` |
| **Network Services** | Vulnerable services | Disable unnecessary services | `systemctl disable`, remove packages | `systemctl list-unit-files` |

**Technical Commands:**
```bash
# Close insecure ports
systemctl stop telnet
systemctl disable telnet

# Secure SSH configuration
# /etc/ssh/sshd_config
PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes

# Configure firewall
ufw default deny incoming
ufw allow from trusted_ip
ufw enable
```

### Service Management

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **Unnecessary Services** | Increased attack surface | Run only required services | Disable unused services, remove packages | `systemctl list-units --type=service` |
| **Service Accounts** | Privilege escalation | Dedicated service accounts with minimal privileges | Create non-root service users | Check service configuration files |
| **Listening Services** | Network exposure | Minimize listening ports | Bind to localhost when possible | `netstat -tulpn` |
| **Service Hardening** | Service-specific vulnerabilities | Apply security configurations | Follow CIS benchmarks for each service | Configuration review |

**Technical Commands:**
```bash
# List all services
systemctl list-unit-files --type=service

# Disable unnecessary services
systemctl disable service_name
systemctl stop service_name

# Run services as non-root users
# In service configuration file
User=service_user
Group=service_group
```

### Authentication and Session Management

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **Password Policy** | Weak passwords | Strong password requirements | `/etc/login.defs`, PAM configuration | Check `/etc/pam.d/common-password` |
| **Account Lockout** | Brute force attacks | Lock accounts after failed attempts | PAM `pam_faillock` module | Test failed login attempts |
| **Session Timeout** | Unattended sessions | Automatic logout after inactivity | `TMOUT` variable, SSH timeout | Check session behavior |
| **Idle Sessions** | Unauthorized access from unattended systems | Screen lock, auto-logout | `xlock`, `vlock`, SSH timeout | Test idle session behavior |
| **MFA** | Credential theft | Multi-factor authentication for sensitive access | Google Authenticator, YubiKey | Verify MFA requirement |

**Technical Commands:**
```bash
# Configure password policy in /etc/login.defs
PASS_MAX_DAYS 90
PASS_MIN_DAYS 1
PASS_MIN_LEN 12
PASS_WARN_AGE 7

# Configure account lockout in /etc/pam.d/system-auth
auth required pam_faillock.so preauth silent audit deny=5 unlock_time=900

# Set session timeout
export TMOUT=600  # 10 minutes
```

### Monitoring and Logging

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **System Logging** | No audit trail | Comprehensive logging of security events | `syslog`, `rsyslog`, centralized logging | Check `/var/log/` |
| **Audit Logging** | Undetected security breaches | Detailed audit of privileged actions | `auditd`, audit rules | `ausearch -m AVC` |
| **Log Rotation** | Disk exhaustion, log loss | Rotate and archive logs | `logrotate` configuration | Check `/etc/logrotate.conf` |
| **Log Protection** | Log tampering | Protect log files from modification | Immutable attributes, remote logging | `chattr +i` on critical logs |
| **Real-time Monitoring** | Delayed threat detection | Automated monitoring and alerting | Monitoring tools, SIEM | Verify alerting functionality |

**Technical Commands:**
```bash
# Enable auditd
systemctl enable auditd
systemctl start auditd

# Configure audit rules
auditctl -w /etc/passwd -p wa -k passwd_changes
auditctl -w /etc/shadow -p wa -k shadow_changes

# Configure log rotation
# /etc/logrotate.d/custom
/path/to/logfile {
    daily
    rotate 7
    compress
    missingok
    notifempty
}
```

### Patch and Update Management

| Area | Security Risk | Policy Requirement | Technical Implementation | Verification |
|------|---------------|-------------------|-------------------------|-------------|
| **Security Patches** | Unpatched vulnerabilities | Apply security updates promptly | Automated updates, regular patch cycles | Check package versions |
| **Package Management** | Outdated software | Current software versions | Package manager (apt, yum), update schedules | `apt list --upgradable` |
| **Vulnerability Scanning** | Undetected vulnerabilities | Regular security scans | Vulnerability scanners (OpenVAS, Nessus) | Review scan reports |
| **Kernel Updates** | Kernel vulnerabilities | Keep kernel updated | Package manager, reboot planning | `uname -r` |
| **Third-party Software** | External dependencies | Secure third-party software | Vet sources, use signed packages | Verify package signatures |

**Technical Commands:**
```bash
# Check for updates
apt update
apt list --upgradable

# Apply security updates
apt upgrade
# or for automatic security updates
apt install unattended-upgrades

# Scan for vulnerabilities
# Using OpenVAS or similar tool
openvas-start
```

### Troubleshooting Hardening Issues

When users report problems after hardening, follow this systematic approach:

#### 1. Identify the Issue
- Collect detailed error messages
- Determine when the problem started
- Identify what the user was trying to do
- Check system logs for related errors

#### 2. Check Recent Changes
- Review recent hardening changes
- Check configuration file modifications
- Review service changes
- Examine firewall rule changes

#### 3. Verify Policy Compliance
- Confirm the issue isn't a policy violation
- Check if the requested access is authorized
- Verify the user should have the access they're requesting

#### 4. Diagnostic Steps
```bash
# Check service status
systemctl status service_name

# Check firewall rules
iptables -L -n -v

# Check logs
journalctl -xe
tail -f /var/log/syslog

# Test network connectivity
ping host
telnet host port
nc -zv host port

# Check permissions
ls -la /path/to/file
```

#### 5. Resolution Strategies
- **False Positive:** If hardening blocked legitimate access, adjust policy or provide exception
- **Configuration Error:** Fix incorrect hardening configuration
- **User Education:** Explain why access is restricted per policy
- **Alternative Solution:** Provide secure alternative access method

### Balancing Security and Functionality

**Key Principles:**
1. **Risk-Based Approach:** Apply strongest controls to highest-risk areas
2. **User-Centric Design:** Make security transparent and easy to use
3. **Gradual Implementation:** Introduce changes incrementally with training
4. **Business Context:** Understand operational needs and workflows
5. **Continuous Monitoring:** Track security effectiveness and user impact

**Common Tradeoffs:**
| Security Measure | Functional Impact | Mitigation |
|------------------|-------------------|------------|
| Strong passwords | User frustration | Use passphrases, password managers |
| MFA | Additional login step | SSO to reduce frequency |
| Strict firewall | Network connectivity issues | Thorough testing, exceptions process |
| Session timeouts | Lost work | Auto-save, clear warnings |
| Restricted software | Limited tools | Provide approved alternatives |

### Maintaining Hardened Systems

**Ongoing Activities:**
1. **Regular Audits:** Periodic security assessments and compliance checks
2. **Vulnerability Management:** Continuous scanning and remediation
3. **Configuration Drift Detection:** Monitor for unauthorized changes
4. **Policy Updates:** Review and update policies as threats evolve
5. **Training:** Ongoing security awareness for administrators and users
6. **Incident Response:** Maintain readiness to respond to security incidents

**Automation Tools:**
- Configuration management (Ansible, Puppet, Chef)
- Vulnerability scanners (OpenVAS, Nessus, Qualys)
- SIEM (Security Information and Event Management)
- Compliance frameworks (OpenSCAP, CIS Benchmarks)
- Monitoring systems (Nagios, Zabbix, Prometheus)

---

## Summary

System hardening and policy-based management require a comprehensive approach that addresses:

1. **Security Policy Components:** Access, accountability, authentication, privacy, and technology policies working together
2. **Policy-Based Management:** Systematic approach using FCAPS framework for consistent, documented administration
3. **Acceptable Use Policy:** Clear guidelines for appropriate technology use, including BYOD considerations
4. **User Account Policy:** Complete lifecycle management of user access with strong authentication and privilege controls
5. **System Hardening:** Technical implementation of security controls across all system layers

**Key Success Factors:**
- Balance security with usability and business needs
- Implement defense-in-depth with multiple security layers
- Use automation to ensure consistency and reduce errors
- Provide continuous education and training
- Maintain regular audits and updates
- Foster a security-conscious organizational culture

**Final Reminder:** Security is not a destination but a continuous process of improvement and adaptation to evolving threats and business requirements.