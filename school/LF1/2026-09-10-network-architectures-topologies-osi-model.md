---
date: 2026-09-10
category: Technical English & IT Systems
tags: [networking, network-topologies, osi-model, encapsulation, ethernet, copper-cabling, fiber-optics, network-hardware, LF6]
source: school
lernfeld: LF6
---

# Network Architectures, Topologies, Transmission Media & The OSI 7-Layer Model
*Date: 10-09-2026* | *Category: #networking #telecommunications #osi-model #technical-english*

---

## Context — Kontext

**🇬🇧** Today in Technical English & IT Systems (**LF6 / KW37 Tag 4**), we covered computer networking foundations: geographic scope (PAN to WAN), client-server vs. P2P architectures, physical topologies (bus, star, ring, mesh), network hardware and physical media (copper twisted pair Cat 5–8 and optical fiber), and the **OSI 7-Layer Model** including data encapsulation and bottom-up troubleshooting.

**🇩🇪** Heute haben wir in Fachenglisch & IT-Systeme (**LF6 / KW37 Tag 4**) Netzwerkgrundlagen behandelt: geografische Reichweiten (PAN bis WAN), Client-Server- vs. P2P-Modelle, Netzwerktopologien (Bus, Stern, Ring, Vermascht), Netzwerk-Hardware und Übertragungsmedien (Kupfer Cat 5–8 und Glasfaser) sowie das **OSI-7-Schichten-Modell** einschließlich Datenkapselung und Bottom-Up-Fehlerdiagnose.

---

## Key Topics — Hauptthemen

### 1. Network Scopes & Architecture Models — Netzwerkausdehnung & Modelle

| Scope / Reichweite | Description & Examples / Beschreibung |
|---|---|
| **PAN (Personal Area Network)** | Personal workspace (<10 m, Bluetooth, NFC, USB). |
| **LAN (Local Area Network)** | Home, school, single office floor/building (Ethernet, Wi-Fi). |
| **MAN (Metropolitan Area Network)** | Spans a campus or entire city (fiber rings, municipal networks). |
| **WAN (Wide Area Network)** | Connects geographically distant sites across countries/continents (Internet). |

| Model / Modell | Characteristics / Merkmale |
|---|---|
| **Peer-to-Peer (P2P)** | Decentralized; all nodes are equal; rule of thumb: best for $\le 10$ computers; low setup cost, but no centralized security. |
| **Client/Server** | Centralized; dedicated servers manage files, authentication, backups, and security policies; scalable for enterprise. |

---

### 2. Network Topologies — Netzwerktopologien

| Topology / Topologie | Structure / Aufbau | Fault Consequence / Ausfallfolge |
|---|---|---|
| **Bus** | All nodes connect to a single central cable (*Main Cable*) with terminators at both ends. | If the main cable breaks, the entire network fails (*Totalausfall*). |
| **Star / Stern** | Each node connects individually to a central switch/hub. | Individual cable failure only affects that node; central switch is a Single Point of Failure. |
| **Ring** | Nodes are connected in a closed circle; data travels in one direction. | A break in the cable disrupts the whole ring (unless dual-ring redundant). |
| **Mesh / Vermascht** | Every node is interconnected to multiple other nodes. | Highly fault-tolerant and redundant; expensive and complex to cable. |

---

### 3. Hardware & Transmission Media — Übertragungsmedien

**Network Devices / Hardware:**
- **Hub:** Layer 1 multiport repeater, broadcasts traffic to all ports (collision domain).
- **Switch:** Layer 2 device, filters and forwards frames selectively based on MAC address tables.
- **Router:** Layer 3 device, forwards packets between different IP subnets and WANs.
- **Gateway:** Protocol converter connecting fundamentally incompatible networks.

**Twisted Pair Copper Cabling / Kupferkabel:**

| Standard | Max Bandwidth / Speed | Max Distance | Primary Use |
|---|---|---|---|
| **Cat 5e** | $1\text{ Gbps}$ | $100\text{ m}$ | Standard Gigabit LAN |
| **Cat 6** | $10\text{ Gbps}$ | $55\text{ m}$ | High-speed workstation connections |
| **Cat 6a / Cat 7** | $10\text{ Gbps}$ | $100\text{ m}$ | Enterprise structured cabling / Server racks |
| **Cat 8** | $40\text{ Gbps}$ | $30\text{ m}$ | Data center switch-to-switch interconnects |

**Fiber Optics (Glasfaser):**
- **Multimode (OM1–OM5):** Larger core ($50/62.5\ \mu\text{m}$), uses LED/VCSEL light; up to $10\text{ Gbps}$ over $300\text{ m}$ to $400\text{ m}$ (in-building LANs).
- **Singlemode (OS1–OS2):** Tiny core ($9\ \mu\text{m}$), uses lasers; up to $100\text{ Gbps}$ over $10\text{ km}$ to $200\text{ km}$ (telecom & WAN backbones).

---

### 4. The OSI 7-Layer Reference Model & Troubleshooting — OSI-Modell

**🇬🇧 Encapsulation:** As data moves down from Layer 7 to Layer 1, each layer wraps the payload with its specific **Header** (and Trailer at Layer 2). Upon reception, the process decapsulates the packet in reverse:
**🇩🇪 Kapselung:** Beim Senden fügt jede Schicht von Layer 7 bis Layer 1 spezifische **Header** hinzu. Beim Empfang wird der Vorgang von unten nach oben dekapsuliert:

```
[ L7 Application ] ──► [ L6 Presentation ] ──► [ L5 Session ] ──► [ L4 Transport (Segment/Port) ] ──► [ L3 Network (Packet/IP) ] ──► [ L2 Data Link (Frame/MAC) ] ──► [ L1 Physical (Bits/Signal) ]
```

| Layer # | Name | Primary Function / Aufgabe | Diagnostic Tool / Befehl |
|---|---|---|---|
| **7** | **Application** | User-facing services (HTTP, DNS, SSH, FTP) | Browser, `curl`, application test |
| **6** | **Presentation** | Data formatting, compression, encryption (TLS, JSON) | OpenSSL, certificate checks |
| **5** | **Session** | Coordinates connections, half/full-duplex dialogues | Session keep-alive monitoring |
| **4** | **Transport** | End-to-end reliability, port addressing (**TCP / UDP**) | `ss -tulpen`, `netstat` |
| **3** | **Network** | Logical IP addressing, packet routing across nets (**IP**) | `ping`, `traceroute`, `ip route` |
| **2** | **Data Link** | Physical MAC addressing, frames, checksums (**Ethernet**) | `ip neighbor` (ARP table) |
| **1** | **Physical** | Electrical/optical bit transmission (cables, RF signals) | `ip link`, cable tester, LED status |

> 🛠️ **Troubleshooting Rule (Bottom-Up):** Always verify from Layer 1 upward: Check physical link $\rightarrow$ check IP & routing $\rightarrow$ check port listening $\rightarrow$ test application.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Star topology with switches is the modern standard:** It isolates link failures and eliminates shared collision domains while remaining straightforward to expand.
- **Systematic troubleshooting uses the OSI model:** If a website is unreachable, testing Layer 3 (`ping 8.8.8.8`), Layer 3 DNS (`ping google.com`), and Layer 4 (`telnet/curl port 443`) pinpoints the exact failure point in seconds.

**🇩🇪**
- **Stern-Topologie mit Switchen ist der moderne Standard:** Sie isoliert Leitungsfehler, eliminiert Kollisionen und lässt sich flexibel erweitern.
- **Systematische Fehlersuche folgt dem OSI-Modell:** Bei Verbindungsproblemen grenzt die schrittweise Prüfung von Layer 1 (Link) über Layer 3 (IP/DNS) bis Layer 4 (Port) die Fehlerquelle zielsicher ein.
