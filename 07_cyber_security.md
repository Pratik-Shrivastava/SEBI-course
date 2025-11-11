# Cyber Security & Cryptography Notes

## **1. Cyber Attacks and Security Concepts**
Cybersecurity deals with protecting systems, networks, and data from digital attacks.

### **Need for Security:**
With the growth of online connectivity, hacking, viruses, and fraud have become common. Protection of data integrity and access is vital.

### **Threat Categories:**
- Human errors
- Espionage and sabotage
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
| Protocol | Function |
|-----------|-----------|
| **SSL/TLS** | Secures web traffic (HTTPS) |
| **SSH** | Secure remote access |
| **IPSec** | Secures IP layer communications |
| **PGP & S/MIME** | Email security protocols |

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

