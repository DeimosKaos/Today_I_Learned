---
date: 2026-08-24
category: Software Development
tags: [binary, data-representation, parity-bit, ascii, signed-unsigned, twos-complement, computer-science, LF5]
source: school
lernfeld: LF5
---

# Parity Bits, ASCII 7-Bit Encoding, Signed vs. Unsigned & Two's Complement
*Date: 24-08-2026* | *Category: #software-development #computer-science*

---

## Context — Kontext

**🇬🇧** Yesterday at school, we dived into low-level data representation and error detection: how parity bits detect transmission faults, why the standard ASCII table only spans 128 characters (0–127), and the arithmetic mechanics of signed vs. unsigned bytes (including why `1111 1111` represents both 255 and -1).

**🇩🇪** Gestern haben wir in der Schule die hardwarenahe Datendarstellung und Fehlererkennung behandelt: wie Paritätsbits Übertragungsfehler erkennen, warum die Standard-ASCII-Tabelle nur 128 Zeichen (0–127) umfasst und die mathematische Mechanik von Signed- vs. Unsigned-Bytes (einschließlich der Erklärung, warum `1111 1111` sowohl 255 als auch -1 darstellt).

---

## Key Topics — Hauptthemen

### 1. Parity Bit & Data Transmission Errors — Paritätsbit & Datenfehler

**🇬🇧** A **parity bit** is an extra check bit appended to a binary data string to detect single-bit transmission errors (bit flips caused by electrical noise or line interference).
**🇩🇪** Ein **Paritätsbit** ist ein zusätzliches Prüfbit, das an eine binäre Datenfolge angehängt wird, um 1-Bit-Übertragungsfehler (Bitkipper durch Leitungsstörungen) zu erkennen.

| Mode / Modus | Rule / Regel | Example Data (7-Bit) | Total 1s with Parity Bit |
|---|---|---|---|
| **Even Parity / Gerade Parität** | Parity bit is set so the total count of `1`s is **even** / Gesamtanzahl der Einsen ist **gerade** | `1001001` (3 ones) | Parity = `1` $\rightarrow$ `10010011` (4 ones) |
| **Odd Parity / Ungerade Parität** | Parity bit is set so the total count of `1`s is **odd** / Gesamtanzahl der Einsen ist **ungerade** | `1001001` (3 ones) | Parity = `0` $\rightarrow$ `10010010` (3 ones) |

- **Detection Limit:** Parity bits can detect single-bit errors. If two bits flip simultaneously, the error goes unnoticed.

---

### 2. Why Does Standard ASCII Only Have 128 Characters (0–127)? — Die 7-Bit ASCII-Tabelle

- **🇬🇧** Standard ASCII uses **7 bits** to encode characters ($2^7 = 128$ combinations, indices `0` to `127`). The 8th bit in a standard byte was historically reserved as the **parity bit** for hardware transmission verification.
- **🇩🇪** Der Standard-ASCII-Code nutzt **7 Bits** zur Zeichenkodierung ($2^7 = 128$ Kombinationen, Indizes `0` bis `127`). Das 8. Bit eines Bytes war historisch als **Paritätsbit** zur hardwareseitigen Übertragungskontrolle reserviert.

---

### 3. Signed vs. Unsigned Bytes — Vorzeichenbehaftete vs. Vorzeichenlose Bytes

An 8-bit byte can be interpreted in two ways depending on data type definition:

| Representation / Typ | Range / Wertebereich | Formula / Formel | MSB (Most Significant Bit) |
|---|---|---|---|
| **Unsigned Byte** | `0` to `255` | $0 \text{ to } 2^8 - 1$ | Value bit ($2^7 = 128$) |
| **Signed Byte** | `-128` to `+127` | $-2^7 \text{ to } 2^7 - 1$ | Sign bit (`0` = positive, `1` = negative) |

---

### 4. Why is `1111 1111` both 255 and -1? — Das Zweierkomplement

The binary string `1111 1111` has two different values depending on the context:

#### Context A: Unsigned Interpretation
$$\text{Value} = 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = \mathbf{255}$$

#### Context B: Signed Interpretation (Two's Complement / Zweierkomplement)
In modern computing, negative integers are represented using **Two's Complement**:

**Calculation via weights:**
$$\text{Value} = (-1 \times 2^7) + 64 + 32 + 16 + 8 + 4 + 2 + 1 = -128 + 127 = \mathbf{-1}$$

**Calculation via algorithm:**
1. Invert all bits (One's Complement): `1111 1111` $\rightarrow$ `0000 0000`
2. Add 1: `0000 0000` + `1` = `0000 0001` (magnitude = 1)
3. Apply negative sign: $\mathbf{-1}$

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Data is just bits without context:** `1111 1111` is neither 255 nor -1 inherently — the program's data type definition determines how the CPU interprets the memory block.
- **Two's complement simplifies hardware:** It allows CPUs to use the exact same addition circuitry for both addition and subtraction ($A - B = A + (-B)$).
- **Parity is the simplest checksum:** Understanding parity bits lays the groundwork for more advanced error-correcting codes (Hamming code, CRC).

**🇩🇪**
- **Daten sind ohne Kontext nur Bits:** `1111 1111` ist von Natur aus weder 255 noch -1 — erst die Datentyp-Definition bestimmt, wie die CPU den Speicher interpretiert.
- **Zweierkomplement vereinfacht Hardware:** Die CPU kann dieselbe Addierschaltung für Addition und Subtraktion verwenden ($A - B = A + (-B)$).
- **Parität ist die einfachste Prüfsumme:** Das Verständnis von Paritätsbits bildet die Grundlage für fortgeschrittene Fehlerkorrekturverfahren (Hamming-Code, CRC).
