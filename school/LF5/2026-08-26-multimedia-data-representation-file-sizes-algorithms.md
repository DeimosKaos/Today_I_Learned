---
date: 2026-08-26
category: Software Development
tags: [multimedia-data, raster-vector, color-models, image-formats, audio-sampling, algorithms, programming-foundations, LF5]
source: school
lernfeld: LF5
---

# Multimedia Data Representation (Images & Audio), File Size Calculations & Algorithms vs. Programs
*Date: 26-08-2026* | *Category: #software-development #multimedia #computer-science*

---

## Context — Kontext

**🇬🇧** Today at school, we explored how multimedia data is represented digitally: the mechanics of raster vs. vector graphics, color spaces (RGB/CMYK/Hex), audio sampling fundamentals, file size mathematical formulas, and the formal definitions distinguishing an **Algorithm** from a **Program**.

**🇩🇪** Heute haben wir die digitale Darstellung von Multimediadaten behandelt: Raster- vs. Vektorgrafiken, Farbräume (RGB/CMYK/Hex), Audio-Sampling-Grundlagen, Berechnungsformeln für Dateigrößen sowie die formale Unterscheidung zwischen einem **Algorithmus** und einem **Programm**.

---

## Key Topics — Hauptthemen

### 1. Graphical Data Representation — Darstellung von Bilddaten

#### Raster vs. Vector Graphics / Raster- vs. Vektorgrafiken
- **Raster / Bitmap:** Matrix of individual pixels. Resolution-dependent; zooming causes pixelation (e.g., photos).
- **Vector / Vektorgrafik:** Defined mathematically via coordinates, paths, lines, and curves. Resolution-independent; scalable infinitely without quality loss (e.g., logos, diagrams).

#### Color Models & Hexadecimal Representation / Farbräume
- **RGB (Red, Green, Blue):** Additive color model for screens (0–255 per channel).
  - Hex notation: `#RRGGBB` (e.g., `#FFFFFF` = White, `#FF0000` = Pure Red).
- **CMYK (Cyan, Magenta, Yellow, Key/Black):** Subtractive color model for print media.

#### Image File Size Calculation (Uncompressed) / Berechnung der Dateigröße

$$\text{File Size (Bytes)} = \frac{\text{Width (px)} \times \text{Height (px)} \times \text{Color Depth (Bits)}}{8}$$

*Note:* Real file size is typically much smaller due to compression algorithms (lossless vs. lossy).

#### Image Formats Overview / Bildformate im Vergleich

| Format | Type / Typ | Compression / Kompression | Transparency / Transparenz | Primary Use / Hauptanwendung |
|---|---|---|---|---|
| **JPEG / JPG** | Raster | Lossy / Verlustbehaftet | ❌ No | Photography, web images / Webfotos |
| **PNG** | Raster | Lossless / Verlustfrei | ✅ Yes (Alpha) | Web graphics, logos, screenshots / Grafiken mit Transparenz |
| **GIF** | Raster | Lossless (256 colors) | ✅ Yes (1-bit) | Simple animations / Einfache Animationen |
| **SVG** | Vector | Lossless (XML text) | ✅ Yes | Scalable web graphics, UI icons / Skalierbare Webicons |
| **TIFF** | Raster | Lossless / Uncompressed | ✅ Yes | High-quality print & archiving / Druckvorstufe & Archivierung |
| **PSD / AI** | Raster/Vector | Proprietary / Layers | ✅ Yes | Editable source files (Photoshop/Illustrator) |
| **PDF / EPS** | Hybrid | Vector + Embedded Raster | ✅ Yes | Print distribution & vector exchange / Druckdaten |

---

### 2. Audio Data Representation — Darstellung von Audiodaten

**🇬🇧** Analog sound waves are digitized through **Sampling** (measuring voltage at discrete time intervals) and **Quantization** (assigning discrete bit values).
**🇩🇪** Analoge Schallwellen werden durch **Sampling / Abtastung** (zeitdiskrete Messung) und **Quantisierung** (wertdiskrete Zuweisung) digitalisiert.

**Key Metrics / Kenngrößen:**
- **Sampling Rate (Abtastrate):** Samples per second in Hz (e.g. CD quality = $44.1\text{ kHz}$).
- **Bit Depth (Bittiefe):** Resolution per sample (e.g. 16-bit = 65,536 dynamic amplitude levels).
- **Channels (Kanäle):** Mono (1) vs. Stereo (2).

**Uncompressed Audio File Size Calculation / Audio-Dateigrößenberechnung:**

$$\text{Size (Bytes)} = \frac{\text{Sampling Rate (Hz)} \times \text{Bit Depth (Bits)} \times \text{Channels} \times \text{Duration (Seconds)}}{8}$$

---

### 3. Algorithms vs. Programs — Algorithmen und Programme

**🇬🇧** A foundational distinction in computer science:
**🇩🇪** Eine grundlegende Unterscheidung in der Informatik:

| Concept / Konzept | Definition | Characteristics / Eigenschaften |
|---|---|---|
| **Algorithmus (Algorithm)** | A precise, step-by-step procedure to solve a problem / Eine eindeutige Handlungsanweisung zur Problemlösung | Abstract, language-independent. Properties: **Determiniertheit** (predictable), **Finitheit** (finite steps), **Terminierung** (ends), **Ausführbarkeit** (executable). |
| **Programm (Program)** | Concrete implementation of an algorithm in a specific programming language / Die konkrete Implementierung eines Algorithmus in einer Programmiersprache | Concrete, language-dependent, compiled/interpreted for machine execution. |

> 💡 **🇬🇧** Core takeaway: An algorithm is the logical recipe; a program is the baked dish in a specific kitchen.
> 💡 **🇩🇪** Kernaussage: Ein Algorithmus ist das logische Rezept; ein Programm ist das fertige Gericht in einer konkreten Programmiersprache.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Formulas bridge theory and system design:** Calculating theoretical raw data sizes reveals why compression formats (JPEG, MP3, PNG) are mandatory for real-world network transmission and storage.
- **Algorithms outlive technologies:** Programming languages change, but algorithmic problem-solving principles remain universally applicable.

**🇩🇪**
- **Formeln verbinden Theorie und Systemdesign:** Die Berechnung theoretischer Rohdaten zeigt, warum Kompressionsformate (JPEG, MP3, PNG) für reale Netzwerke und Speicher unersetzlich sind.
- **Algorithmen überdauern Technologien:** Programmiersprachen ändern sich, aber algorithmische Problemlösungsmuster bleiben universell gültig.
