---
date: 2026-09-28
category: Networking & Telecommunications
tags: [networking, local-area-networks, qos, bandwidth, latency, jitter, osi-model, ieee-802, LF3]
source: school
lernfeld: LF3
---

# Local Network Engineering (LF3 Start): Requirements, QoS Metrics & Layered Architectures
*Date: 28-09-2026* | *Category: #networking #telecommunications #qos #lan-fundamentals*

---

## Context — Kontext

**🇬🇧** Today marked the start of **Lernfeld 3.1: Fundamentals of Local Networks (*Grundlagen lokaler Netze*)**. We explored modern network engineering requirements (bandwidth, latency, jitter, packet loss), the mechanics of **Quality of Service (QoS)** prioritization, and the structural necessity of layered architectural models (**ISO/OSI vs. IEEE 802**).

**🇩🇪** Heute begann **Lernfeld 3.1: Grundlagen lokaler Netze**. Wir haben die Anforderungen moderner Netzwerkarchitekturen (Bandbreite, Latenz, Jitter, Paketverlust), Mechanismen für **Quality of Service (QoS)** sowie die Notwendigkeit von Schichtenmodellen (**ISO/OSI vs. IEEE 802**) behandelt.

---

## Key Topics — Hauptthemen

### 1. Network Performance Metrics — Netzwerkanforderungen

| Metric / Kenngröße | Unit / Einheit | Definition & Impact on Applications |
|---|---|---|
| **Bandwidth (Bandbreite)** | Bit/s, Mbit/s, Gbit/s | Theoretical maximum data transfer capacity of the link. |
| **Throughput (Durchsatz)** | Bit/s, Mbit/s | Actual measured payload volume transferred under real load. |
| **Latency / Delay (Latenz)** | Milliseconds ($\text{ms}$) | Propagation and queueing delay from source to destination (RTT = Round Trip Time). |
| **Jitter (Laufzeitschwankung)** | Milliseconds ($\text{ms}$) | Statistical variance in latency between successive packets (critical for VoIP/video). |
| **Packet Loss Rate (Paketverlust)** | Percentage ($\%$) | Fraction of transmitted packets dropped due to buffer congestion or physical errors. |

---

### 2. Quality of Service (QoS) & Traffic Prioritization — QoS-Mechanismen

**🇬🇧** Not all network traffic has equal tolerance for latency. QoS tags and prioritizes time-sensitive packets (VoIP, video calls) ahead of bulk transfers (downloads, backups) in network queues:
**🇩🇪** QoS priorisiert latenzempfindlichen Datenverkehr (VoIP, Video) gegenüber unkritischen Downloads in den Warteschlangen der Router und Switches:

```
[ Incoming Network Traffic ] ──► [ Classification & DSCP Tagging ] ──► [ Priority Queuing (VoIP > Web > Bulk) ] ──► [ Outbound Interface ]
```

- **VoIP / Realtime:** Requires low latency ($<150\text{ ms}$) and minimal jitter ($<30\text{ ms}$), but consumes low bandwidth.
- **Bulk Data (File Backups):** Tolerates high latency and jitter, but demands high continuous bandwidth throughput.

---

### 3. Layered Models: ISO/OSI vs. IEEE 802 — Schichtenmodelle

- **The Division of Labor:** Layering isolates concerns — a web application (HTTP) does not need to know whether the physical link is optical fiber, copper Ethernet, or Wi-Fi radio waves.
- **IEEE 802 Sublayering:** Subdivides OSI Layer 2 (Data Link) into two distinct sublayers:
  1. **LLC (Logical Link Control - 802.2):** Standardized interface to Layer 3 protocols (IP).
  2. **MAC (Media Access Control):** Hardware-specific access protocol (e.g. 802.3 Ethernet, 802.11 Wi-Fi).

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Bandwidth is width; latency is speed:** Increasing bandwidth from $100\text{ Mbps}$ to $1\text{ Gbps}$ allows larger files to transfer simultaneously, but does not make individual VoIP voice packets arrive faster.
- **IEEE 802 bridges media to IP:** By splitting Layer 2 into LLC and MAC, IP can communicate seamlessly over copper, fiber, and radio without altering network-layer routing.

**🇩🇪**
- **Bandbreite ist Kapazität; Latenz ist Geschwindigkeit:** Eine höhere Bandbreite ermöglicht größere Datenmengen zeitgleich, verringert aber nicht die Signallaufzeit eines einzelnen VoIP-Pakets.
- **IEEE 802 entkoppelt Medien von IP:** Die Teilung von Layer 2 in LLC und MAC erlaubt es IP, transparent über Kupfer, Glasfaser oder Funk zu routen.
