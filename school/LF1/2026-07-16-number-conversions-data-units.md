---
date: 2026-07-16
category: Theory
tags: [math, binary-system, data-units, binary-conversion, computer-science]
source: school
lernfeld: LF1
---

# Number System Conversions & Data Units (Bits, Bytes & 1024 Rule)
*Date: 16-07-2026* | *Category: #theory #math #computer-science*

---

## Context — Kontext

**🇬🇧** Today at school, we studied methods for converting numbers between different numeral systems (decimal, binary, octal, and hexadecimal). We also explored data measurement units (from Bits to Terabytes) and the mathematical rules for converting between them using the binary factor of 1,024.

**🇩🇪** Heute haben wir in der Schule Methoden zur Umrechnung von Zahlen zwischen verschiedenen Zahlensystemen (Dezimal, Binär, Oktal und Hexadezimal) gelernt. Zudem haben wir uns mit Dateneinheiten (von Bit bis Terabyte) und den mathematischen Umrechnungsregeln unter Verwendung des Binärfaktors 1.024 beschäftigt.

---

## Key Topics — Hauptthemen

### 1. Numeral System Conversions — Umrechnung von Zahlensystemen
- **🇬🇧** Practiced conversions between four primary bases used in computer science:
  - **Decimal (Base 10):** Human-readable numbers.
  - **Binary (Base 2):** Machine-level states (0 and 1).
  - **Octal (Base 8):** Shorthand representation of binary.
  - **Hexadecimal (Base 16):** Highly efficient representation of 8-bit bytes (0-9, A-F).
- **🇩🇪** Praktische Übungen zur Umrechnung zwischen den vier primären Basen der Informatik:
  - **Dezimal (Basis 10):** Vom Menschen lesbare Zahlen.
  - **Binär (Basis 2):** Maschinenebene (0 und 1).
  - **Oktal (Basis 8):** Komprimierte Darstellung von Binärdaten.
  - **Hexadezimal (Basis 16):** Sehr effiziente Darstellung von 8-Bit-Bytes (0-9, A-F).

### 2. Data Units & The 1024 Rule — Dateneinheiten & Die 1024-Regel
- **🇬🇧** **Bit vs. Byte:** 1 Byte consists of 8 Bits. 
- **🇩🇪** **Bit vs. Byte:** 1 Byte besteht aus 8 Bits.
- **🇬🇧** **Conversion Factor (1,024):** In computer science, prefixes like Kilo, Mega, Giga, and Tera are scaled by factors of $2^{10}$ (1,024) rather than the standard decimal $10^3$ (1,000). For example:
  $$\text{1 KB (KiB)} = 1,024 \text{ Bytes}$$
  $$\text{1 MB (MiB)} = 1,024 \text{ KB}$$
  $$\text{1 GB (GiB)} = 1,024 \text{ MB}$$
- **🇩🇪** **Umrechnungsfaktor (1.024):** In der Informatik werden Präfixe wie Kilo, Mega, Giga und Tera mit Faktoren von $2^{10}$ (1.024) statt der standardmäßigen dezimalen $10^3$ (1.000) berechnet. Beispiel:
  $$\text{1 KB (KiB)} = 1.024 \text{ Bytes}$$
  $$\text{1 MB (MiB)} = 1.024 \text{ KB}$$
  $$\text{1 GB (GiB)} = 1.024 \text{ MB}$$

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Binary scaling defines hardware:** The factor of 1,024 comes from $2^{10}$. This explains why operating systems and hardware manufacturers sometimes display different storage capacities (binary gibibytes vs. decimal gigabytes).
- **Hexadecimal simplifies binary:** It is much easier to read two hex digits (e.g., `FF`) than eight binary bits (`11111111`).

**🇩🇪**
- **Binäre Skalierung prägt Hardware:** Der Faktor 1.024 stammt aus $2^{10}$. Dies erklärt, warum Betriebssysteme und Hardwarehersteller manchmal unterschiedliche Speicherkapazitäten anzeigen (binäre Gibibytes vs. dezimale Gigabytes).
- **Hexadezimal vereinfacht Binär:** Es ist viel einfacher, zwei Hex-Ziffern zu lesen (z. B. `FF`) als acht Binär-Bits (`11111111`).
