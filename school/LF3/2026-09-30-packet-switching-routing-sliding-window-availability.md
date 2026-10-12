---
date: 2026-09-30
category: Networking & Telecommunications
tags: [switching-techniques, packet-switching, circuit-switching, routing, sliding-window, flow-control, high-availability, mtbf, LF3]
source: school
lernfeld: LF3
---

# Switching Techniques, OSI Layer 3 Routing, Sliding Window Flow Control & Availability Metrics
*Date: 30-09-2026* | *Category: #networking #routing #telecommunications #flow-control*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 3.1**), we covered network switching and routing mechanisms: comparing **Circuit, Message, and Packet Switching**, multiplexing techniques, the mechanics of **OSI Layer 3 routing**, flow control algorithms (**Sliding Window**), and high-availability reliability engineering (**MTBF, MTTR, SLA 99.999%**).

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 3.1**) Vermittlungs- und Routingtechniken behandelt: den Vergleich von **Leitungs-, Speicher- und Paketvermittlung**, Multiplexverfahren, die Grundlagen des **Routings im OSI-Referenzmodell**, Flusssteuerung per **Sliding-Window-Verfahren** sowie Verfügbarkeitsmetriken (**MTBF, MTTR, Hochverfügbarkeit**).

---

## Key Topics — Hauptthemen

### 1. Switching Techniques — Vermittlungsarten im Vergleich

| Switching Method / Vermittlung | Operating Principle / Prinzip | ✅ Advantages / Vorteile | ❌ Disadvantages / Nachteile | Examples |
|---|---|---|---|---|
| **Circuit Switching (Leitungsvermittlung)** | Dedicated physical channel established for the entire call duration / Feste Leitung exklusiv belegt. | Guaranteed constant bandwidth, zero latency jitter. | Inefficient resource usage when idle; line blocked for others. | Traditional landline telephony (ISDN/PSTN). |
| **Packet Switching (Paketvermittlung)** | Data split into individual addressed packets routed independently / Pakete werden dynamisch geroutet. | Optimal link utilization, resilient to route failures. | Variable latency and jitter, packet reordering needed at destination. | **The Internet (IP)**, Ethernet, Cellular 4G/5G. |
| **Message Switching (Speichervermittlung)** | Whole message stored at intermediate nodes and forwarded when free / Store-and-Forward. | No real-time connection required between sender and receiver. | High storage required at nodes, high transmission delay. | Email (SMTP), SMS, asynchronous message queues. |

---

### 2. Routing in the OSI Reference Model — Routing-Grundlagen

**🇬🇧** Routing operates at **OSI Layer 3 (Network Layer)**:
**🇩🇪** Routing erfolgt auf **OSI-Schicht 3 (Vermittlungsschicht)**:

- A router maintains a **Routing Table** mapping destination IP network subnets to next-hop gateway interfaces.
- Uses metrics (hop count, link bandwidth, delay) via dynamic protocols (OSPF, BGP, RIP) to calculate the shortest path.
- **TTL (Time to Live):** Every router decrements the IP packet's TTL field by 1. When $\text{TTL} = 0$, the packet is discarded and an ICMP *Time Exceeded* message is returned to the sender, preventing infinite routing loops.

---

### 3. Flow Control: The Sliding Window Algorithm — Flusssteuerung

**🇬🇧** Prevents a fast sender from overwhelming a slow receiver or congested network buffer:
**🇩🇪** Verhindert die Überlastung des Empfängers durch einen zu schnellen Sender:

```
Sender Buffer:  [ Packet 1 (ACKed) ] [ Packet 2 (ACKed) ] ──► [ Window: P3, P4, P5 (In Transit) ] ──► [ P6, P7 (Waiting) ]
```

- **Window Size:** Specifies how many bytes/segments the sender may transmit before requiring an acknowledgment (**ACK**) from the receiver. As ACKs arrive, the "window" slides forward dynamically.

---

### 4. Reliability & Availability Engineering — Zuverlässigkeit & Hochverfügbarkeit

| Metric / Kennzahl | Full Name | Meaning / Bedeutung |
|---|---|---|
| **MTBF** | Mean Time Between Failures / Mittlere Betriebsdauer zwischen Ausfällen | Average operational uptime between consecutive system breakdowns. |
| **MTTR** | Mean Time to Repair / Mittlere Reparaturdauer | Average time required to diagnose, repair, and restore the failed system. |
| **Availability ($A$)** | Systemverfügbarkeit | $A = \frac{\text{MTBF}}{\text{MTBF} + \text{MTTR}} \times 100\%$ |
| **"Five Nines" (99.999%)** | High Availability Gold Standard | Maximum allowed unplanned downtime: **$\le 5.26\text{ minutes per year}$**. |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Packet switching made the modern internet scalable:** Sharing bandwidth dynamically across packets enabled global networks without needing millions of dedicated physical lines.
- **High availability requires minimizing MTTR, not just maximizing MTBF:** Redundant failover clusters (HA) restore service in seconds, achieving 99.999% uptime even when individual servers fail.

**🇩🇪**
- **Paketvermittlung machte das Internet skalierbar:** Die dynamische Aufteilung von Bandbreite ermöglicht weltweite Datennetze ohne starre Exklusivleitungen.
- **Hochverfügbarkeit erfordert minimale MTTR:** Redundante Failover-Cluster stellen Dienste in Sekunden wieder her und erreichen „Five Nines" (99,999%), selbst wenn einzelne Hardwarekomponenten ausfallen.
