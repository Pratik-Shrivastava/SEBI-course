# Cyber Security & Cryptography Notes

## **1. Cyber Attacks and Security Concepts**
Cybersecurity deals with protecting systems, networks, and data from digital attacks.

### **Need for Security:**
With the growth of online connectivity, hacking, viruses, and fraud have become common. Protection of data integrity and access is vital.

### **Threat Categories:**
- Human errors
- Espionage: gathering secret information
- sabotage: deliberate destruction or disruption of property or systems
- Software and hardware failures
- Deliberate acts (e.g., theft, extortion)

### **Aspects of Security:**
- **Security Attack:** Any action that compromises information security.
- **Security Mechanism:** Techniques that detect, prevent, or recover from attacks.
- **Security Service:** Services ensuring confidentiality, authentication, integrity, and availability.

---

## **2. CIA Triad (Confidentiality, Integrity, Availability)**
| Concept | Definition | Mechanism |
|----------|-------------|------------|
| **Confidentiality** | Prevents unauthorized data access | Encryption, Access control |
| **Integrity** | Prevents unauthorized modification | Hashing, Checksums |
| **Availability** | Ensures data is accessible | Backups, Redundancy |

---

## **3. Authentication**
Authentication ensures that communication or access is from an authorized source.

### **Types:**
- **Peer Entity Authentication:** Verifies the identity of communicating parties.
- **Data Origin Authentication:** Ensures message source authenticity.

---

## **4. Security Mechanisms**
### **Specific Mechanisms:**
- **Encipherment:** Converts plaintext into ciphertext.
- **Digital Signature:** Validates message integrity and source.
- **Access Control:** Enforces access permissions.
- **Data Integrity:** Ensures data is not altered.
- **Authentication Exchange:** Confirms identity using credentials.
- **Traffic Padding:** Prevents traffic pattern analysis.
- **Routing Control:** Ensures secure transmission paths.

### **Pervasive Mechanisms:**
- Event Detection
- Security Audit Trail
- Security Recovery

---

## **5. Model for Network Security**
A security model defines the secure transmission of information using:
1. **Security Transformation** – e.g., encryption.
2. **Secret Information (Key)** – Shared securely between parties.
3. **Protocol** – Governs how the transformation and key are used.
4. **Trusted Third Party** – Handles key distribution and dispute resolution.

---

## **6. Software Development Security**
Software security ensures that software is designed and maintained securely.

### **Key Principles:**
- Secure SDLC practices
- Code reviews and threat modeling
- Input validation and safe coding
- Use of secure APIs

---

## **7. Network Security**
Network security protects data during transmission using policies and tools like:
- Firewalls
- Intrusion Detection Systems (IDS)
- VPNs
- Authentication and Encryption

### **Network Security Layers:**
1. Data Security
2. Application Security
3. Endpoint Security
4. Network and Perimeter Security

---

## **8. Network & System Audit**
### **Network Audit:**
Systematic review of network devices and configurations to detect vulnerabilities.

**Steps:**
1. Asset Identification  
2. Configuration Review  
3. Access Control Verification  
4. Vulnerability Assessment  
5. Reporting & Recommendations

### **System Audit:**
Ensures systems adhere to security standards using tools like:
- **Wireshark** – Network monitoring
- **Nmap** – Port scanning
- **Nessus** – Vulnerability detection

---

## **9. Cryptography Concepts**
Cryptography secures data by converting it into unreadable form using mathematical algorithms.

### **Types:**
- **Symmetric Key Cryptography:** Same key for encryption and decryption (e.g., DES, AES, Blowfish).
- **Asymmetric Key Cryptography:** Different keys for encryption and decryption (e.g., RSA, Diffie-Hellman).

### **Classical Ciphers:**
- **Caesar Cipher:** Shifts letters by a fixed number.
- **Playfair Cipher:** Encrypts pairs of letters.
- **Vigenère Cipher:** Uses a keyword for multiple shifts.

### **Modern Algorithms:**
| Algorithm | Type | Key Size | Description |
|------------|------|-----------|--------------|
| **DES** | Symmetric | 56 bits | Block cipher with 16 rounds |
| **AES** | Symmetric | 128/192/256 bits | Advanced standard with strong security |
| **RSA** | Asymmetric | Variable | Uses two keys for encryption/decryption |
| **Diffie-Hellman** | Asymmetric | Variable | Enables secure key exchange |

---

## **10. Network Security Protocols**

| **Protocol** | **Port Number** | **Function / Purpose** | **Prevents / Protects Against** | **OSI Layer** | **IP Version** | **Other Information** |
|---------------|----------------|-------------------------|----------------------------------|----------------|----------------|------------------------|
| **SSL (Secure Sockets Layer)** | 443 (for HTTPS over SSL), 465 (SMTP over SSL) | Encrypts data between web browser and server | Eavesdropping, Man-in-the-middle (MITM), Data tampering | Transport Layer | IPv4 / IPv6 | Deprecated, replaced by TLS |
| **TLS (Transport Layer Security)** | 443 (HTTPS), 995 (POP3S), 993 (IMAPS), 465 (SMTPS) | Ensures secure transmission via encryption, authentication, and integrity | Eavesdropping, Data manipulation, MITM | Transport Layer | IPv4 / IPv6 | Successor of SSL; uses asymmetric + symmetric encryption |
| **HTTPS (Hypertext Transfer Protocol Secure)** | 443 | Secure version of HTTP; encrypts data using SSL/TLS | Data sniffing, MITM attacks | Application Layer | IPv4 / IPv6 | Used for secure web browsing |
| **SSH (Secure Shell)** | 22 | Secure remote login and command execution | Eavesdropping, Password theft, MITM | Application Layer | IPv4 / IPv6 | Replaces Telnet and FTP for secure connections |
| **SFTP (SSH File Transfer Protocol)** | 22 (via SSH) | Secure file transfer using SSH encryption | Data interception, Unauthorized file access | Application Layer | IPv4 / IPv6 | Different from FTPS (uses SSL/TLS) |
| **FTPS (FTP Secure)** | 990 (implicit), 21 (explicit) | Secure file transfer using SSL/TLS | Data sniffing, Credential theft | Application Layer | IPv4 / IPv6 | Extension of FTP adding SSL/TLS |
| **IPSec (Internet Protocol Security)** | Protocol IDs: 50 (ESP), 51 (AH), 500 (IKE) | Secures IP packets via authentication & encryption | IP spoofing, Replay attacks, Packet sniffing | Network Layer | IPv4 & IPv6 | Provides VPN security; Transport & Tunnel modes |
| **IKE (Internet Key Exchange)** | 500 (UDP) | Establishes security associations for IPSec | Unauthorized access, Replay attacks | Network Layer | IPv4 / IPv6 | Automates key exchange and management |
| **DNSSEC (Domain Name System Security Extensions)** | 53 (UDP/TCP) | Adds authentication to DNS responses | DNS spoofing, Cache poisoning | Application Layer | IPv4 / IPv6 | Uses digital signatures to validate DNS data |
| **Kerberos** | 88 (TCP/UDP) | Authentication protocol using tickets | Replay attacks, Impersonation | Application Layer | IPv4 / IPv6 | Used in Windows domains; based on symmetric key cryptography |
| **SMTP with STARTTLS / SMTPS** | 25 (STARTTLS), 465 (SMTPS) | Secures email transmission | Email interception, Data leaks | Application Layer | IPv4 / IPv6 | Encrypts communication between mail servers |
| **POP3S (Post Office Protocol Secure)** | 995 | Secure retrieval of emails | Credential theft, Data sniffing | Application Layer | IPv4 / IPv6 | POP3 over SSL/TLS |
| **IMAPS (Internet Message Access Protocol Secure)** | 993 | Securely retrieves emails from mail servers | MITM, Unauthorized access | Application Layer | IPv4 / IPv6 | IMAP over SSL/TLS |
| **SNMPv3 (Simple Network Management Protocol v3)** | 161 (UDP) | Manages network devices securely | Unauthorized monitoring, Data tampering | Application Layer | IPv4 / IPv6 | Adds authentication & encryption (not in v1/v2) |
| **RADIUS (Remote Authentication Dial-In User Service)** | 1812 (Authentication), 1813 (Accounting) | Centralized authentication for network access | Unauthorized access, Replay attacks | Application Layer | IPv4 / IPv6 | Uses shared secret; common in Wi-Fi authentication |
| **TACACS+ (Terminal Access Controller Access Control System Plus)** | 49 | Provides centralized authentication similar to RADIUS but fully encrypted | Password sniffing, Unauthorized access | Application Layer | IPv4 / IPv6 | Used in Cisco devices; separates AAA functions |
| **LDAP over SSL/TLS (LDAPS)** | 636 | Securely manages directory access | Credential theft, Replay attack | Application Layer | IPv4 / IPv6 | Encrypts Lightweight Directory Access Protocol |
| **PGP (Pretty Good Privacy)** | N/A (Application based) | Encrypts and authenticates email content | Email tampering, Spoofing | Application Layer | IPv4 / IPv6 | Uses public-key encryption for secure email |
| **SPF, DKIM, DMARC** | N/A (DNS-based) | Authenticate email senders to prevent spam | Email spoofing, Phishing | Application Layer | IPv4 / IPv6 | Verified via DNS records |
| **SRTP (Secure Real-Time Transport Protocol)** | Dynamic ports (UDP-based) | Encrypts audio/video data in VoIP | Eavesdropping, Replay attacks | Application Layer | IPv4 / IPv6 | Used with SIP for secure VoIP calls |
| **SIP-TLS (Session Initiation Protocol over TLS)** | 5061 | Secure session setup for VoIP calls | Eavesdropping, Call hijacking | Application Layer | IPv4 / IPv6 | SIP (5060) unsecured → SIP-TLS (5061) secured |
| **802.1X (Port-Based Network Access Control)** | Uses EAP over LAN | Authenticates devices before granting network access | Unauthorized LAN access | Data Link Layer | IPv4 / IPv6 | Common in enterprise Wi-Fi & LAN |
| **WPA2 / WPA3 (Wi-Fi Protected Access)** | N/A (used in wireless frames) | Secures Wi-Fi communication | Eavesdropping, Dictionary attacks | Data Link Layer | IPv4 / IPv6 | WPA3 uses SAE (Simultaneous Authentication of Equals) |
| **VPN (Virtual Private Network - OpenVPN, L2TP/IPSec, PPTP)** | OpenVPN – 1194, L2TP – 1701, PPTP – 1723 | Creates encrypted tunnel for secure data transmission | Snooping, MITM attacks | Network / Transport Layer | IPv4 / IPv6 | Used for remote secure access |

---

## 🧠 Summary by OSI Layer

| **OSI Layer** | **Security Protocols** | **Main Function** |
|----------------|-----------------------|-------------------|
| **Application** | HTTPS, SSH, FTPS, SFTP, SNMPv3, Kerberos, DNSSEC, RADIUS, TACACS+, LDAPS | Encryption, Authentication |
| **Transport** | SSL/TLS | Data encryption and integrity |
| **Network** | IPSec, IKE | Secure packet transfer between networks |
| **Data Link** | 802.1X, WPA2, WPA3 | Secure access control for LAN/Wi-Fi |

---

## ⚙️ Attack Prevention Mapping

| **Attack Type** | **Prevented By** |
|------------------|------------------|
| **Man-in-the-Middle (MITM)** | TLS, IPSec, SSH |
| **Eavesdropping / Sniffing** | TLS, IPSec, WPA2/3 |
| **IP Spoofing** | IPSec (Authentication Header) |
| **DNS Spoofing / Poisoning** | DNSSEC |
| **Email Spoofing / Phishing** | SPF, DKIM, DMARC |
| **Unauthorized Network Access** | 802.1X, RADIUS, TACACS+ |
| **Replay Attacks** | Kerberos, IPSec |
| **Password Theft** | SSH, SNMPv3, TLS |

---

## 🔑 Key Notes

- **TLS** is the backbone of modern web security.
- **IPSec** works at the **Network Layer**, ideal for VPNs.
- **802.1X + RADIUS** = Enterprise-grade network access control.
- **Kerberos** provides **mutual authentication** via tickets.
- **WPA3** offers improved Wi-Fi protection using **SAE**.

---

---

## **11. Firewalls and Intrusion Prevention**
Firewalls act as a barrier between trusted and untrusted networks.

### **Types of Firewalls:**
- Packet-filtering
- Proxy
- Stateful inspection
- Next-generation firewalls (NGFW)

### **IDS/IPS:**
- **IDS:** Detects intrusions.
- **IPS:** Detects and prevents intrusions.

---

## **12. Cyber Forensics**
The process of identifying, preserving, analyzing, and presenting digital evidence.

### **Phases:**
1. **Collection** – Identify and gather data.
2. **Examination** – Recover and analyze data.
3. **Analysis** – Interpret findings.
4. **Reporting** – Document conclusions.

---

## **13. Cybersecurity Tools & Attack Prevention**
Below is a list of **widely used cybersecurity tools**, their descriptions, and the **attacks they help prevent:**

| Tool | Description | Prevents/Detects |
|------|--------------|-----------------|
| **Wireshark** | Network packet analyzer that captures and inspects traffic. | Packet sniffing, man-in-the-middle attacks |
| **Nmap** | Network scanning tool to identify hosts, open ports, and services. | Network reconnaissance, unauthorized access |
| **Nessus** | Vulnerability scanner for detecting system and network weaknesses. | Exploits, outdated software vulnerabilities |
| **Snort** | Open-source Intrusion Detection System (IDS). | DoS, DDoS, buffer overflow, port scanning |
| **Metasploit** | Penetration testing framework for identifying security flaws. | Weak authentication, exploitable services |
| **Burp Suite** | Web application security testing tool. | SQL injection, XSS, session hijacking |
| **John the Ripper** | Password cracking and strength testing tool. | Weak passwords, brute force attacks |
| **Aircrack-ng** | Wireless network security testing suite. | Wi-Fi password cracking, WPA/WEP attacks |
| **Kali Linux** | Security testing OS containing penetration tools. | Network & system attacks, ethical hacking |
| **Splunk** | Security Information and Event Management (SIEM) tool. | Anomaly detection, real-time attack alerts |
| **OSSEC** | Host-based intrusion detection system. | Unauthorized file modifications, privilege escalation |
| **OpenVAS** | Comprehensive vulnerability scanning framework. | Server misconfiguration, known exploits |
| **Fail2Ban** | Monitors logs to block repeated login attempts. | Brute-force login attacks |
| **Suricata** | Real-time intrusion detection and prevention system. | Malware, DoS/DDoS, exploit attempts |
| **Tripwire** | File integrity monitoring tool. | Unauthorized file tampering |

---

## **14. Summary of Core Cybersecurity Areas**
| Area | Focus |
|-------|--------|
| **Cyber Attacks** | Threats and countermeasures |
| **CIA Triad** | Data confidentiality, integrity, availability |
| **Network Security** | Secure transmission & communication |
| **Authentication** | Verifying identity and authorization |
| **Cryptography** | Secure data using encryption/decryption |
| **Software Security** | Secure development practices |
| **Audits** | Evaluate and strengthen security posture |
| **Forensics** | Investigate and recover digital evidence |

---

### **Recommended References:**
- William Stallings, *Cryptography and Network Security: Principles and Practice*.
- Atul Kahate, *Cryptography and Network Security*.
- Nina Godbole, *Cyber Security: Understanding Cyber Crimes, Computer Forensics and Legal Perspectives*.

