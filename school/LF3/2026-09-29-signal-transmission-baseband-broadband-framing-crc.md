---
date: 2026-09-29
category: Networking & Signal Processing
tags: [signal-transmission, baseband-broadband, modulation, line-coding, manchester-code, ethernet-frames, crc, LF3]
source: school
lernfeld: LF3
---

# Physical Signal Transmission, Line Coding, Baseband vs. Broadband & Framing Mechanics
*Date: 29-09-2026* | *Category: #networking #signal-processing #physical-layer #data-link*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 3.1**), we explored the physical and electrical foundations of data transmission: operational modes (simplex, duplex), line coding (NRZ, Manchester), the difference between **Baseband (*Basisband*)** and **Broadband (*Breitband*)**, analog modulation methods (AM, FM, PM, QAM), and Data Link layer **Framing & CRC Error Detection**.

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 3.1**) die physikalischen Grundlagen der Datenübertragung behandelt: Betriebsarten (Simplex, Duplex), Leitungscodierung (NRZ, Manchester), den Vergleich von **Basisband- vs. Breitbandübertragung**, Modulationsverfahren (AM, FM, PM, QAM) sowie **Frame-Erzeugung und CRC-Fehlererkennung** auf Schicht 2.

---

## Key Topics — Hauptthemen

### 1. Transmission Operational Modes — Betriebsarten

| Mode / Betriebsart | Communication Direction / Richtung | Example in Technology |
|---|---|---|
| **Simplex** | Unidirectional only (Sender $\longrightarrow$ Receiver) / Nur in eine Richtung. | Radio broadcasting, GPS, sensor telemetry. |
| **Half-Duplex (Halbduplex)** | Bidirectional, but **only one direction at a time** / Abwechselnd in beide Richtungen. | Walkie-Talkie, legacy Ethernet hub networks (CSMA/CD). |
| **Full-Duplex (Vollduplex)** | Bidirectional, **simultaneously in both directions** / Gleichzeitig in beide Richtungen. | Modern Switched Ethernet, telephone calls, fiber links. |

---

### 2. Baseband vs. Broadband & Line Coding — Basisband vs. Breitband

**Baseband Transmission (Basisbandübertragung):**
- Digital signal uses the entire frequency bandwidth of the cable directly (e.g. Ethernet standard).
- Simple hardware, ideal for local networks; uses **Line Coding** (e.g. **Manchester Code**, which embeds the clock signal directly into voltage transitions in the middle of each bit).

**Broadband Transmission (Breitbandübertragung):**
- Frequency Division Multiplexing (FDM): multiple signals modulate different carrier frequencies simultaneously on the same physical medium (e.g. Cable TV, DSL, Wi-Fi).

**Modulation Techniques (Modulationsarten):**
- **AM (Amplitude Modulation):** Modulates signal strength.
- **FM (Frequency Modulation):** Modulates signal frequency.
- **PM / QAM (Phase & Quadrature Amplitude Modulation):** Modulates phase shifts and amplitude combined (basis for high-speed Wi-Fi and 5G).

---

### 3. Frame Construction & Error Detection — Frame-Erzeugung & Fehlererkennung

**🇬🇧** On Layer 2, raw bit streams are organized into structured **Frames** bounded by preamble flags:
**🇩🇪** Auf Schicht 2 wird der Bitstrom in strukturierte **Frames** unterteilt:

```
[ Preamble / Start Frame Delimiter ] ──► [ Dest MAC ] ──► [ Source MAC ] ──► [ Type/Length ] ──► [ Payload Data ] ──► [ Frame Check Sequence (CRC-32) ]
```

- **CRC (Cyclic Redundancy Check):** The sender calculates a 32-bit polynomial checksum over the frame data. The receiver recalculates the polynomial. If a bit error occurred during transmission, the checksums do not match, and the frame is silently dropped (or re-requested by higher layers).

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Full-Duplex switches eliminate collisions:** Moving from half-duplex hubs to full-duplex switches gave every network device dedicated bandwidth without sharing transmission media.
- **CRC guarantees frame integrity:** Layer 2 does not attempt to repair corrupted bits — it detects them mathematically via CRC and discards damaged frames immediately.

**🇩🇪**
- **Vollduplex-Switche eliminieren Kollisionen:** Der Übergang von Halbduplex-Hubs zu Vollduplex-Switchen garantiert jedem Gerät exklusive Bandbreite ohne Kollisionsrisiko.
- **CRC sichert die Integrität:** Layer 2 repariert fehlerhafte Bits nicht aufwendig, sondern verwirft beschädigte Frames nach der mathematischen CRC-Prüfung sofort.
