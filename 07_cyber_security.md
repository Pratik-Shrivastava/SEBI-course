# Information & Cyber Security Concepts (Expanded Conceptual Guide)

---

## ⚔️ 1. CYBER ATTACKS

**Concept:**  
A Cyber Attack is a deliberate attempt to steal, alter, or damage information systems or networks by exploiting vulnerabilities.

**Textual Diagram:**
```
[ Attacker ]
     │
     ▼
[ Network / System ]
     │
     ├─► Data Theft
     ├─► Denial of Service
     └─► System Damage
```

### Classification of Attacks
| Category | Description | Examples |
|-----------|--------------|-----------|
| Active | Alter or destroy data | DDoS, Man-in-the-Middle |
| Passive | Eavesdropping, info gathering | Packet sniffing |
| Insider | Authorized user misuse | Employee data leak |
| External | Outside intrusion | Hackers, Botnets |
| Malware-based | Malicious code execution | Viruses, Worms, Trojans |

### Common Attacks and Defenses
| Attack Type | Mechanism | Mitigation |
|--------------|------------|-------------|
| Phishing | Fake emails/websites | Awareness, spam filters |
| Ransomware | Encrypts files, demands ransom | Backups, anti-malware |
| SQL Injection | Injects code into queries | Input validation |
| DDoS | Floods traffic to crash target | Firewalls, load balancers |
| MITM | Intercepts data between systems | Encryption (TLS/SSL) |

**Example:**  
An attacker sends fake bank login emails → user enters credentials → stolen by attacker.

**MCQs:**  
Flooding server with traffic → ✅ DDoS  
Encrypting files for ransom → ✅ Ransomware  
SQL Injection targets → ✅ Databases

---

## 🧰 2. SOFTWARE DEVELOPMENT SECURITY

**Concept:**  
Security must be integrated into every phase of the SDLC (Software Development Life Cycle) — not added afterward.

**Secure SDLC Flow:**
```
Requirements → Design → Implementation → Testing → Deployment → Maintenance
      ↓             ↓             ↓             ↓             ↓
  Define CIA    Threat Model   Secure Code   Pen Test     Patch Mgmt
```

### Security Across Phases
| SDLC Phase | Security Practice | Example |
|-------------|-------------------|----------|
| Requirements | Identify data sensitivity, access needs | Define roles |
| Design | Threat modeling, secure architecture | Data flow diagrams |
| Implementation | Secure coding standards | Input sanitization |
| Testing | Static/Dynamic testing, code review | Fuzzing |
| Deployment | Configuration hardening | Disable default accounts |
| Maintenance | Patches, incident response | Regular updates |

**Frameworks & Standards:**  
OWASP Top 10 (Web Security), ISO/IEC 27034 (App Security)

**Example:**  
Implement role-based access control to prevent privilege escalation.

**MCQs:**  
Threat modeling done during → ✅ Design phase  
OWASP Top 10 lists → ✅ Web app vulnerabilities  
Security integrated in → ✅ Every SDLC phase

---

## 🌐 3. NETWORK SECURITY

**Concept:**  
Protecting data in transit from unauthorized access, misuse, or modification.

**Textual Diagram:**
```
[User] → [Switch] → [Router] → [Firewall] → [Server]
```

### Core Components
| Control | Function |
|----------|-----------|
| Firewall | Blocks unauthorized traffic |
| IDS/IPS | Detects or prevents intrusions |
| VPN | Encrypts communication channels |
| DMZ | Isolates public-facing servers |
| Proxy | Hides internal IPs |
| TLS/IPSec | Encrypts network traffic |

**Common Tools:** Wireshark, Snort, pfSense, Nmap

**Example:**  
VPN ensures encrypted remote access — even over public Wi-Fi.

**MCQs:**  
IDS detects → ✅ Unauthorized access attempts  
VPN uses → ✅ Encryption tunnels  
DMZ hosts → ✅ Public servers

---

## 🔐 4. AUTHENTICATION

**Concept:**  
Process of verifying who a user or system claims to be before granting access.

**AAA Model Diagram:**
```
User Request
   ↓
[ Authentication ]
   ↓
[ Authorization ]
   ↓
[ Accounting (Logging) ]
```

### Authentication Factors
| Type | Example |
|------|----------|
| Something you know | Password, PIN |
| Something you have | OTP token, Smart card |
| Something you are | Fingerprint, Iris scan |

**Mechanisms:**
- Password-based login  
- Two-Factor Authentication (2FA)  
- Single Sign-On (SSO)  
- Biometrics  
- Kerberos, LDAP, OAuth protocols

**Example:**  
Logging in with password + OTP = Two-Factor Authentication.

**MCQs:**  
MFA means → ✅ Multi-Factor Authentication  
“Something you are” → ✅ Biometric factor  
Kerberos used for → ✅ Network authentication

---

## 🏛 5. CIA TRIAD — Confidentiality, Integrity, Availability

**Concept:**  
The CIA Triad forms the foundation of all cybersecurity policies.

**Textual Diagram:**
```
   Confidentiality
        /\
       /  \
 Integrity ---- Availability
```

### Principle Breakdown
| Principle | Function | Controls / Examples |
|------------|-----------|---------------------|
| Confidentiality | Prevent unauthorized disclosure | Encryption, Access Control |
| Integrity | Ensure data accuracy & trust | Hashing, Digital Signatures |
| Availability | Ensure systems are accessible | Backups, Redundancy, DRP |

**Example:**  
Using AES encryption (confidentiality), SHA-256 hashing (integrity), and redundant servers (availability).

**MCQs:**  
CIA stands for → ✅ Confidentiality, Integrity, Availability  
Integrity maintained by → ✅ Hashing  
Availability improved with → ✅ Backups

---

## 🕵️‍♂️ 6. NETWORK AUDIT

**Concept:**  
Network audit ensures infrastructure, configurations, and controls are secure and compliant.

**Diagram (Audit Flow):**
```
Inventory → Configuration Review → Vulnerability Scan → Report & Fix
```

### Audit Focus Areas
| Step | Objective |
|------|------------|
| Asset Discovery | Identify devices and topology |
| Access Control Review | Validate permissions and firewall rules |
| Patch Verification | Check updates and firmware |
| Vulnerability Scanning | Detect open ports and misconfigurations |
| Reporting | Summarize findings and remediation plan |

**Common Tools:** Nessus, Nmap, Wireshark, SolarWinds

**Example:**  
Using Nmap to scan for open ports and firewall gaps.

**MCQs:**  
Network audit ensures → ✅ Compliance and security posture  
First step → ✅ Asset inventory  
Tool for scanning → ✅ Nmap

---

## 🧮 7. SYSTEMS AUDIT

**Concept:**  
Evaluates integrity, security, and efficiency of software, hardware, and operational processes.

**Diagram:**
```
[ Applications ]
      ↓
[ Operating System ]
      ↓
[ Hardware & Network ]
```

### Audit Objectives
| Area | Control / Focus |
|------|------------------|
| Access Controls | Least privilege, role-based permissions |
| Change Management | Track system modifications |
| Backup & Recovery | Verify disaster recovery process |
| Logs & Monitoring | Detect unauthorized actions |
| Compliance Check | Adherence to ISO/NIST policies |

### Types of Audits
- **Compliance Audit:** Confirms with ISO 27001, IT Act  
- **Operational Audit:** Checks system efficiency  
- **Technical Audit:** Tests configuration & security flaws

**MCQs:**  
System audit checks → ✅ Security & control mechanisms  
Compliance audit ensures → ✅ Standards adherence  
Audit logs used for → ✅ Forensic analysis

---

## ✅ FINAL REVISION TABLE
| Concept | Function / Objective | Common Tools / Standards |
|----------|----------------------|----------------------------|
| Cyber Attacks | Exploit vulnerabilities | Firewalls, Anti-malware |
| Secure SDLC | Embed security in software lifecycle | OWASP, ISO 27034 |
| Network Security | Protect data in transit | VPN, IDS, Firewall |
| Authentication | Verify identity | MFA, Kerberos, OAuth |
| CIA Triad | Core security principles | Encryption, Hashing, Backup |
| Network Audit | Evaluate network configuration | Nmap, Nessus |
| System Audit | Assess IT system security | ISO 27001, Logs |

---

## 🧠 IFSCA EXAM TIPS
- ✅ **Cyber Attack Focus:** Know at least 3 examples each of malware, phishing, and network attacks.  
- ✅ **CIA Triad:** Most repeated 2-mark topic.  
- ✅ **SDLC:** Threat modeling → Design phase.  
- ✅ **Authentication:** Two of three factors = MFA.  
- ✅ **Network Audit:** Begin with asset inventory, end with risk report.  
- ✅ **System Audit:** Check access rights, backups, and change management.  
- ✅ **Common Standards:** ISO 27001 (Information Security), OWASP (Application Security), NIST CSF (Cyber Framework).  
- ✅ **Tools:** Nmap = port scan, Nessus = vulnerability, Wireshark =