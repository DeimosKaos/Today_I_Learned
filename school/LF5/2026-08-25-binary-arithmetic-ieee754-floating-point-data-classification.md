---
date: 2026-08-25
category: Computer Science & Data Analysis
tags: [binary-arithmetic, ieee-754, floating-point, data-classification, structured-unstructured, security, LF2, LF5]
source: school
lernfeld: LF2
---

# Binary Arithmetic, IEEE 754 Floating-Point Numbers & Data Classification
*Date: 25-08-2026* | *Category: #computer-science #data-analysis #hardware-architecture*

---

## Context — Kontext

**🇬🇧** Yesterday at school, we covered binary arithmetic operations, explored the **IEEE 754 floating-point standard** (single/double precision, bias, normalization, and rounding anomalies like `0.1 + 0.2 != 0.3`), and completed our classification of data types, structure levels, and confidentiality protection classes according to BSI/ISO 27001.

**🇩🇪** Gestern haben wir in der Schule binäre Rechenoperationen behandelt, den **IEEE 754 Gleitkommastandard** (Single/Double Precision, Bias, Normalisierung und Rundungsfehler wie `0.1 + 0.2 != 0.3`) vertieft sowie die Klassifizierung von Daten nach Art, Strukturierungsgrad und Schutzklassen nach BSI/ISO 27001 abgeschlossen.

---

## Key Topics — Hauptthemen

### 1. Binary Arithmetic — Binäre Arithmetik & Rechenoperationen

#### Addition & Adders (Addierer)
- **Bitwise Addition:** $0+0=0$, $1+0=1$, $1+1=0$ (Carry $1$), $1+1+1=1$ (Carry $1$).
- **Half Adder (Halbaddierer):** Adds 2 bits $\rightarrow$ Sum ($A \oplus B$) and Carry ($A \land B$).
- **Full Adder (Volladdierer):** Adds 2 bits + 1 Carry-In ($C_{in}$) $\rightarrow$ Sum and Carry-Out ($C_{out}$).

#### Subtraction via Two's Complement — Subtraktion mit Zweierkomplement
- Subtraction is converted to addition:
  $$A - B = A + (\bar{B} + 1)$$
- **Carry Rule:** The final carry bit beyond the word length is discarded.
- **Overflow (OF) Detection:** An overflow occurs when adding two numbers of the same sign produces a result with the opposite sign (e.g. positive + positive = negative).

#### Multiplication & Division via Bit-Shifts
- **Multiplication:** Shift-and-Add algorithm. Hardware optimization via Left-Shift (`<< n`) multiplies by $2^n$.
- **Division:** Shift-and-Subtract algorithm (with remainder). Hardware optimization via Right-Shift (`>> n`) divides by $2^n$.

---

### 2. Floating-Point Numbers (IEEE 754) — Fließkommazahlen im Dualsystem

**Memory Layout / Bit-Aufbau:**

| Format | Total Bits | Sign / Vorzeichen ($S$) | Biased Exponent ($E$) | Mantissa / Fraktion ($M$) | Bias Value |
|---|---|---|---|---|---|
| **Single Precision (32-Bit / float)** | 32 | 1 Bit (Bit 31) | 8 Bit (Bit 30–23) | 23 Bit (Bit 22–0) | **127** |
| **Double Precision (64-Bit / double)** | 64 | 1 Bit (Bit 63) | 11 Bit (Bit 62–52) | 52 Bit (Bit 51–0) | **1023** |

**Value Formula / Berechnungsformel:**
$$\text{Value} = (-1)^S \times (1.M)_2 \times 2^{E - \text{Bias}}$$

- **Hidden Bit:** In normalized numbers, the leading `1.` before the binary point is implied and omitted in memory to gain +1 bit of precision.
- **Step-by-Step Conversion Example ($-13.625_{10}$ to IEEE 754 32-Bit):**
  1. *Sign:* Negative $\rightarrow S = 1$.
  2. *Integer Part:* $13_{10} = 1101_2$.
  3. *Fractional Part:* $0.625_{10} = 0.5 + 0.125 = 0.101_2$.
  4. *Combined Binary:* $1101.101_2$.
  5. *Normalize:* $1.101101_2 \times 2^3 \rightarrow \text{Mantissa } M = 10110100000000000000000$.
  6. *Biased Exponent:* $E = 3 + 127 = 130_{10} = 10000010_2$.
  7. *Result:* `1 | 10000010 | 10110100000000000000000` $\rightarrow$ Hex: `0xC15A0000`.

#### Special Cases & Precision Issues / Sonderfälle & Rundungsfehler

| Condition / Zustand | Exponent ($E$) | Mantissa ($M$) | Meaning / Bedeutung |
|---|---|---|---|
| **Zero ($\pm 0$)** | `00...0` | `00...0` | Signed Zero / Vorzeichenbehaftete Null |
| **Infinity ($\pm \infty$)** | `11...1` | `00...0` | Overflow / Division by Zero |
| **NaN (Not a Number)** | `11...1` | $\neq 0$ | Invalid operation (e.g. $\sqrt{-1}$, $0/0$) |
| **Subnormal Numbers** | `00...0` | $\neq 0$ | Gradual underflow close to zero / Denormalisierte Zahlen |

> ⚠️ **Why `0.1 + 0.2 != 0.3`:** Fractional numbers like $0.1_{10}$ and $0.2_{10}$ produce repeating infinite binary fractions ($0.0\overline{0011}_2$). Rounding to 23/52 bits causes precision drift.
> **Best Practice:** For financial and accounting systems, always use integer cents or dedicated Decimal data types, never standard floats/doubles!

---

### 3. Data Classification & Security — Daten nach Art, Struktur & Herkunft

| Classification Dimension / Dimension | Categories / Kategorien | Key Characteristics / Merkmale |
|---|---|---|
| **Signal Type / Signaltyp** | Analog vs. Digital | Continuous wave vs. discrete binary sampling (ADC, Nyquist-Shannon Theorem: $f_{sample} \ge 2 \times f_{max}$ to prevent Aliasing). |
| **Structuring Level / Strukturierungsgrad** | Structured / Semistructured / Unstructured | **Structured:** Relational tables (SQL), strict schema.<br>**Semistructured:** Self-describing schema (JSON, XML).<br>**Unstructured:** Text docs, images, videos without tabular structure. |
| **Confidentiality (BSI / ISO 27001)** | Public / Internal / Confidential / Strictly Confidential | Governed by **Need-to-Know** and **Principle of Least Privilege (PoLP)** to restrict access to sensitive business/personal data. |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Hardware is addition-only:** Inverting bits and adding 1 (Two's complement) allows the CPU's adder to perform subtraction seamlessly.
- **Float arithmetic is inexact:** Knowing that IEEE 754 binary floats cannot represent exact base-10 decimals ($0.1$) is crucial for writing bug-free data processing pipelines.
- **Data structure defines analytics architecture:** Choosing SQL vs. NoSQL (JSON) vs. Data Lake depends on whether data is structured, semistructured, or unstructured.

**🇩🇪**
- **Hardware rechnet nur mit Addition:** Durch Bit-Invertierung und Addition von 1 (Zweierkomplement) führt das Addierwerk der CPU auch Subtraktionen aus.
- **Gleitkomma-Arithmetik ist inexakt:** Das Wissen, dass binäre IEEE-754-Floats Dezimalzahlen wie $0.1$ nicht exakt abbilden können, ist essenziell für fehlerfreie Datenanalyse-Pipelines.
- **Datenstruktur bestimmt die Architektur:** Die Wahl zwischen SQL, NoSQL (JSON) und Data Lakes hängt direkt vom Strukturierungsgrad (strukturiert, semistrukturiert, unstrukturiert) ab.
