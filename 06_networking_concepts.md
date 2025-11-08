# 🌐 NETWORKING CONCEPTS (Expanded Conceptual Guide)

---

## 🧱 1. ISO / OSI STACK

### 1.1 Quick Overview of OSI Layers

| Layer | Name | Main Function (Precise Summary) | Typical Protocols / Examples | Devices / Role |
|:--:|:--|:--|:--|:--|
| 7 | Application | Provides services for user applications (email, web, file transfer) | HTTP, FTP, DNS, SMTP, POP | Web browsers, mail clients |
| 6 | Presentation | Translates data formats; handles encryption, compression, encoding | SSL/TLS, JPEG, ASCII | Encryption, conversion |
| 5 | Session | Establishes, maintains, and terminates communication sessions | NetBIOS, RPC | Session tracking |
| 4 | Transport | Ensures reliable delivery, flow control, segmentation | TCP, UDP | End-to-end delivery |
| 3 | Network | Handles routing and logical addressing (path determination) | IP, ICMP, ARP | Routers |
| 2 | Data Link | Node-to-node delivery; framing, MAC addressing, error check | Ethernet, PPP, VLAN | Switches, NICs |
| 1 | Physical | Transmits raw bits via cables/wireless; defines voltages & media | RJ-45, Fiber, Bluetooth | Hubs, repeaters |

**Mnemonic:** 🧠 *All People Seem To Need Data Processing*

---

### 1.2 OSI Model – Concept

**Concept:**
The OSI (Open Systems Interconnection) model is a 7-layer architecture that standardizes communication functions between computing systems.

**Textual Diagram:**
```
Layer 7: Application   → User interaction (HTTP, FTP)
Layer 6: Presentation  → Data format & encryption
Layer 5: Session       → Connection management
Layer 4: Transport     → Reliable delivery (TCP/UDP)
Layer 3: Network       → Routing & addressing
Layer 2: Data Link     → MAC addressing, framing
Layer 1: Physical      → Signals, media, cables
```

**Encapsulation Flow:**
```
Application Data → [Add Headers] → Physical Transmission
Receiver decapsulates upward layer-by-layer.
```

**Practice:**
- Identify which layer handles encryption.
- Name two devices that work at Layer 2 and Layer 3.

**MCQs:**
- OSI model has → ✅ 7 layers
- Routing occurs at → ✅ Network Layer
- TCP/UDP belong to → ✅ Transport Layer

---

## 🏨 2. LAN TECHNOLOGIES (Ethernet & Token Ring)

### 2.1 Ethernet (IEEE 802.3)

**Concept:**
Dominant LAN technology using CSMA/CD (Carrier Sense Multiple Access / Collision Detection).

**Mini Flow:**
```
Listen → Channel Free → Transmit → Collision? → Back-off & Retry
```

**Key Points:**
- Operates at Data Link & Physical layers.
- Uses 48-bit MAC addresses.
- Topology: Star (modern) / Bus (old).
- Frame fields: Preamble | Dest | Source | Type | Data | CRC.

**Example:**
```
| Dest MAC | Src MAC | Type | Payload | FCS |
```

**MCQs:**
- Ethernet standard → ✅ IEEE 802.3
- Access method → ✅ CSMA/CD
- Modern Ethernet uses → ✅ Switches

---

### 2.2 Token Ring (IEEE 802.5)

**Concept:**
Nodes pass a token sequentially; only token-holder transmits.

**Diagram:**
```
[A] → [B] → [C] → [D] → [A]
```

**Features:**
- Deterministic access (no collision).
- Logical Ring, Physical Star topology.
- 4–16 Mbps speeds.

**MCQs:**
- Standard → ✅ IEEE 802.5
- Collisions → ✅ No
- Token controls → ✅ Transmission right

---

## 🔸 3. TCP / UDP

| Feature | TCP | UDP |
|:--|:--|:--|
| Type | Connection-oriented | Connectionless |
| Reliability | Reliable (ACK, retransmit) | Unreliable |
| Speed | Slower | Faster |
| Use | Web, Mail, File Transfer | DNS, VoIP, Streaming |
| Handshake | 3-way (SYN, SYN+ACK, ACK) | None |

**Diagram:**
```
TCP:  SYN → SYN+ACK → ACK
UDP:  Direct send, no reply
```

**MCQs:**
- Reliable protocol → ✅ TCP
- DNS uses → ✅ UDP
- Flow control present in → ✅ TCP

---

## 🚀 4. INTERNET PROTOCOL (IP)

**Concept:**
Provides logical addressing & routing between networks.

| Version | Bits | Example | Note |
|:--|:--|:--|:--|
| IPv4 | 32 | 192.168.1.1 | Dotted decimal |
| IPv6 | 128 | 2001:0db8::1 | Hexadecimal |

**Routing Flow:**
```
Source → Router 1 → Router 2 → Destination
```

**MCQs:**
- IPv4 bits → ✅ 32
- IPv6 notation → ✅ Hexadecimal
- Routing handled by → ✅ Network Layer

---

## 🧩 5. NETWORK DEVICES

### Switch (Layer 2)
- Forwards frames by MAC address, reduces collisions, supports VLANs.
```
PC1-| Switch |-PC2
```

### Router (Layer 3)
- Connects different networks, decides best path using IP address.
```
LAN 1 ↔ Router ↔ Internet ↔ Router ↔ LAN 2
```

### Gateway (All Layers)
- Protocol translator between different systems (e.g., SMTP ↔ X.400).

**MCQs:**
- Switch works at → ✅ Layer 2
- Router → ✅ IP based forwarding
- Gateway → ✅ Protocol conversion

---

## 📡 6. APPLICATION LAYER PROTOCOLS

| Protocol | Function | Default Port |
|:--|:--|:--|
| DNS | Name → IP resolution | UDP 53 |
| SMTP | Send mail | TCP 25 |
| POP3 | Retrieve mail | TCP 110 |
| FTP | File transfer | TCP 20/21 |
| HTTP/HTTPS | Web communication | 80 / 443 |

**Quick Flows:**
- **DNS:** query → resolver → root → TLD → authoritative.
- **SMTP:** client → mail server → recipient server.
- **POP3:** download from server to client.
- **FTP:** 2 channels (control + data).
- **HTTP:** client requests HTML page → server responds.

**MCQs:**
- DNS port → ✅ 53 (UDP)
- FTP ports → ✅ 20/21
- HTTPS uses → ✅ SSL/TLS on 443

---

## 🔥 7. FIREWALLS

**Concept:**
Security device controlling traffic in/out based on rules.

**Textual Diagram:**
```
Internal Network ↔ [ FIREWALL ] ↔ Internet
```

### Types

| Type | Layer | Description |
|:--|:--|:--|
| Packet Filter | Network | Filters by IP/Port |
| Stateful Inspection | Transport | Tracks connections |
| Proxy | Application | Deep inspection |
| Next-Gen | Multi | Adds IDS/IPS features |

**Example Rule:**
```
ALLOW 192.168.1.5 → Port 80
DENY All others
```

**MCQs:**
- Main function → ✅ Traffic filtering
- Stateful firewall tracks → ✅ Sessions
- Default-deny policy → ✅ Blocks unless allowed

---

## ✅ FINAL REVISION TABLE

| Concept | Function / Protocol | Layer / Standard |
|:--|:--|:--|
| OSI Model | Defines 7 layers | ISO |
| Ethernet | CSMA/CD access | IEEE 802.3 |
| Token Ring | Token passing | IEEE 802.5 |
| TCP / UDP | Transport layer | Reliable / Fast |
| IP | Logical routing | IPv4/IPv6 |
| Switch | MAC based forwarding | Layer 2 |
| Router | IP routing | Layer 3 |
| Gateway | Protocol conversion | All layers |
| DNS / HTTP / FTP | Application layer | User services |
| Firewall | Access control | Multi-layer security |

---

## 🧠 IFSCA EXAM TIPS

- OSI → 7 layers, TCP/IP → 4 layers (Application, Transport, Internet, Network Access).
- Switch = L2, Router = L3, Gateway = All layers.
- Port numbers: DNS 53, HTTP 80, HTTPS 443, SMTP 25, FTP 20/21, POP3 110.
- Ethernet Frame ends with FCS (Frame Check Sequence).
- TCP Handshake: SYN → SYN+ACK → ACK.
- Token Ring obsolete; Ethernet dominant.
- IPv4 = 32-bit, IPv6 = 128-bit (colon-separated).
- Firewalls enforce policy-based traffic control; remember “default deny.”

