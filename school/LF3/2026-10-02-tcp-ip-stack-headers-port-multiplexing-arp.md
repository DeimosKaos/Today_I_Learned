---
date: 2026-10-02
category: Networking & Internet Protocols
tags: [tcp-ip, tcp-header, udp, port-multiplexing, ip-header, mtu-fragmentation, arp, ipv4-subnetting, LF3]
source: school
lernfeld: LF3
---

# The TCP/IP Protocol Stack: TCP vs. UDP Headers, IP Fragmentation & The ARP Protocol
*Date: 02-10-2026* | *Category: #networking #tcp-ip #internet-protocols #packet-analysis*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 3.1**), we concluded our intensive networking module with a deep architectural breakdown of the **TCP/IP Protocol Suite**: examining **TCP vs. UDP header structures**, port multiplexing, the **IPv4 header format**, MTU packet fragmentation, the Address Resolution Protocol (**ARP**), and IPv4 address classification.

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 3.1**) das Netzwerkmodul mit einer tiefen Analyse der **TCP/IP-Protokollfamilie** abgeschlossen: dem Vergleich von **TCP- und UDP-Headern**, Port-Multiplexing, dem Aufbau des **IPv4-Headers**, MTU-Paketfragmentierung, dem **ARP-Protokoll** sowie der Klassifizierung von IPv4-Adressen.

---

## Key Topics — Hauptthemen

### 1. Transport Layer: TCP vs. UDP — TCP vs. UDP im Vergleich

| Feature / Protokoll | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
|---|---|---|
| **Connection State / Verbindung** | **Connection-oriented:** Establishes session via **3-Way Handshake** (`SYN` $\rightarrow$ `SYN-ACK` $\rightarrow$ `ACK`). | **Connectionless:** Sends datagrams immediately without handshake ("Fire and forget"). |
| **Reliability / Zuverlässigkeit** | Guaranteed delivery; retransmits lost packets; ordered sequence numbers. | No guarantee; lost packets are discarded; no retransmission. |
| **Header Overhead** | **20–60 Bytes** (Sequence numbers, Acknowledgment numbers, Window size, Flags: SYN, ACK, FIN, RST, PSH, URG). | **8 Bytes** (Source Port, Dest Port, Length, Checksum). |
| **Use Cases / Einsatz** | Web (HTTP/HTTPS), File Transfer (FTP/SFTP), Email (SMTP/IMAP), SSH. | Real-time voice/video (VoIP, RTP), DNS queries, live streaming, DHCP, gaming. |

---

### 2. Port Multiplexing — Multiplexmechanismus über Portnummern

**🇬🇧** Allows a single physical host with one IP address to run dozens of network services simultaneously:
**🇩🇪** Ermöglicht es einem Rechner mit einer IP, viele Netzwerkdienste gleichzeitig zu betreiben:

- **Socket:** The unique combination of `IP Address : Port Number` (e.g. `192.168.1.50:443`).
- **Well-Known Ports (0–1023):** Reserved system services (HTTP `80`, HTTPS `443`, SSH `22`, DNS `53`, DHCP `67/68`).
- **Registered Ports (1024–49151):** Vendor services (e.g. MySQL `3306`, MS SQL `1433`, PostgreSQL `5432`).
- **Dynamic / Ephemeral Ports (49152–65535):** Client-side outbound temporary ports.

---

### 3. Network Layer: IPv4 Header & MTU Fragmentation — IP-Header & Fragmentierung

```
 0                   1                   2                   3
 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|Version|  IHL  |Type of Service|          Total Length         |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|         Identification        |Flags|     Fragment Offset     |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|  Time to Live |    Protocol   |        Header Checksum        |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                       Source IP Address                       |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Destination IP Address                     |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

- **MTU (Maximum Transmission Unit):** Standard Ethernet MTU is **1500 Bytes**. If an IP packet exceeds 1500 bytes, routers split it into multiple fragments using the **Identification**, **Flags (DF/MF)**, and **Fragment Offset** fields, reassembling it at the final destination host.
- **Protocol Field:** Identifies encapsulated payload (`6` = TCP, `17` = UDP, `1` = ICMP).

---

### 4. ARP (Address Resolution Protocol) — MAC-Adressauflösung

**🇬🇧** Resolves a known Layer 3 IP address to an unknown Layer 2 physical MAC address within a local subnet:
**🇩🇪** Ermittelt zu einer bekannten IP-Adresse die zugehörige MAC-Hardware-Adresse im lokalen Netz:

1. Host A sends an **ARP Request Broadcast** (`FF:FF:FF:FF:FF:FF`): *"Who has IP 192.168.1.1? Tell 192.168.1.50!"*
2. Target Host B sends an **ARP Reply Unicast**: *"192.168.1.1 is at 00:1A:2B:3C:4D:5E."*
3. Host A saves the mapping in its local **ARP Table / Cache** (`arp -a` or `ip neighbor`).

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **TCP guarantees order; UDP prioritizes immediacy:** Video calls drop delayed UDP voice packets because hearing a word 3 seconds late is useless; file transfers require TCP because a single missing bit corrupts the archive.
- **ARP is the glue between Layer 2 and Layer 3:** IP routing gets packets across global routers, but local Ethernet delivery requires translating that destination IP into a physical MAC address via ARP.

**🇩🇪**
- **TCP sichert Vollständigkeit, UDP sichert Aktualität:** Bei Videotelefonie ist ein verspätetes UDP-Paket nutzlos; bei Dateiübertragungen zerstört ein einziges fehlendes TCP-Paket das Archiv.
- **ARP verbindet Schicht 2 und Schicht 3:** IP-Routing leitet Daten weltweit durch Netze, aber die lokale Zustellung im Ethernet erfordert die Übersetzung der IP in eine MAC-Adresse über ARP.
