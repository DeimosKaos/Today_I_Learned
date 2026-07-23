---
date: 2026-07-23
category: Theory
tags: [hardware, interfaces, bios, uefi, usb, pcie, sata, secure-boot, LF2]
source: school
lernfeld: LF2
---

# Hardware Interfaces, BIOS & UEFI Deep Dive
*Date: 23-07-2026* | *Category: #theory #hardware*

---

## Context — Kontext

**🇬🇧** Today at school, we covered hardware interfaces in depth, from serial/parallel fundamentals to modern connectors (USB, HDMI, PCIe). We then dived into the firmware layer: BIOS (its boot process and POST) and its modern successor UEFI (with GPT, Secure Boot, and a look at Coreboot as an open alternative).

**🇩🇪** Heute haben wir Hardware-Schnittstellen tiefgehend behandelt, von seriellen/parallelen Grundlagen bis zu modernen Anschlüssen (USB, HDMI, PCIe). Anschließend haben wir uns mit der Firmware-Schicht beschäftigt: dem BIOS (Bootvorgang und POST) und seinem modernen Nachfolger UEFI (mit GPT, Secure Boot und einem Ausblick auf Coreboot als offene Alternative).

---

## Key Topics — Hauptthemen

### 1. Interfaces — Schnittstellen

**🇬🇧 Definition:** An interface connects systems with different physical, electrical, and mechanical properties, defining communication protocols between them.
**🇩🇪 Definition:** Eine Schnittstelle verbindet Systeme mit unterschiedlichen physikalischen, elektrischen und mechanischen Eigenschaften und definiert Kommunikationsprotokolle zwischen ihnen.

**Serial vs. Parallel / Seriell vs. Parallel:**

| | Serial / Seriell | Parallel |
|---|---|---|
| **Data Transfer / Datenübertragung** | 1 bit at a time / 1 Bit gleichzeitig | Multiple bits simultaneously / Mehrere Bits gleichzeitig |
| **Distance / Distanz** | Long distances / Lange Distanzen | Short distances (e.g. CPU↔RAM) / Kurze Distanzen |
| **Cost / Kosten** | Lower / Günstiger | Higher / Teurer |

**External Interfaces / Externe Schnittstellen:**

| Interface | Type / Typ | Key Detail / Besonderheit |
|---|---|---|
| **USB 1.0–3.1** | Serial / Seriell | Auto device detection, power supply, Type-C connector / Automatische Geräteerkennung, Spannungsversorgung, Typ-C |
| **VGA** | Analog video / Analoges Bildsignal | Legacy, no audio / Veraltet, kein Ton |
| **DVI-I** | Analog + Digital | Supports both signal types / Unterstützt beide Signaltypen |
| **HDMI** | Digital audio+video / Digital Audio+Video | Up to 4K, single cable / Bis zu 4K, ein Kabel |
| **PS/2** | Serial / Seriell | Mouse & keyboard legacy / Veraltet für Maus & Tastatur |
| **COM Port** | Serial / Seriell | Industrial / legacy use / Industrie & Altanlagen |

**Internal Storage Interfaces / Interne Massenspeicher-Schnittstellen:**

| Interface | Speed / Geschwindigkeit | Use Case / Einsatz |
|---|---|---|
| **SATA** | Up to ~600 MB/s | HDDs and SSDs / Festplatten und SSDs |
| **SAS** | Up to ~12 Gbit/s | Servers & storage systems / Server & Storage |
| **PCIe / NVMe** | Up to ~16 GB/s (v5.0) | High-performance SSDs / Hochleistungs-SSDs (x1–x16 lanes, backwards compatible / abwärtskompatibel) |

---

### 2. BIOS — Basic Input/Output System

**🇬🇧** The BIOS is the firmware stored on an EEPROM/Flash chip that acts as the bridge between hardware and the operating system during startup.
**🇩🇪** Das BIOS ist eine Firmware, die auf einem EEPROM-/Flash-Chip gespeichert ist und als Brücke zwischen Hardware und Betriebssystem beim Start dient.

**POST (Power-On Self-Test) Sequence:**
1. **🇬🇧** CPU initialized → Graphics card checked → RAM tested → Keyboard detected → Drives scanned → ACPI tables generated
2. **🇩🇪** CPU initialisiert → Grafikkarte geprüft → RAM getestet → Tastatur erkannt → Laufwerke gescannt → ACPI-Tabellen erzeugt

**Boot Process / Bootvorgang:**
- **🇬🇧** BIOS loads the OS via the **Master Boot Record (MBR)** on the first sector of the disk → hands off to OS drivers (Protected Mode).
- **🇩🇪** BIOS lädt das Betriebssystem über den **Master Boot Record (MBR)** im ersten Sektor der Festplatte → übergibt an OS-Treiber (Protected Mode).

> ⚠️ **🇬🇧** BIOS updates carry a risk of bricking the device if interrupted — always use a stable power source and follow manufacturer instructions.
> ⚠️ **🇩🇪** BIOS-Updates können das Gerät unbrauchbar machen, wenn sie unterbrochen werden — stets stabile Stromversorgung und Herstelleranleitung beachten.

---

### 3. UEFI & Secure Boot

**🇬🇧** UEFI (Unified Extensible Firmware Interface) replaced the legacy BIOS. Written in C, it supports high-resolution GUIs, networking, modular extensions, and GPT partitioning.
**🇩🇪** UEFI ersetzt das klassische BIOS. In C geschrieben, unterstützt es hochauflösende GUIs, Netzwerkfähigkeit, modulare Erweiterbarkeit und GPT-Partitionierung.

| Feature | BIOS | UEFI |
|---|---|---|
| **Language / Sprache** | Assembler | C |
| **Partition Table / Partitionstabelle** | MBR (max 2 TB, 4 partitions) | GPT (max >2 TB, 127 partitions / Partitionen) |
| **Interface / Oberfläche** | Text-only / Nur Text | Graphical / Grafisch |
| **Network / Netzwerk** | ❌ | ✅ |
| **Secure Boot** | ❌ | ✅ |

**UEFI Secure Boot:**
- **🇬🇧** Validates digital signatures (Platform Key, Key Exchange Key) during boot to block unsigned/malicious bootloaders. *Note: known vulnerabilities exist — not a silver bullet.*
- **🇩🇪** Prüft digitale Signaturen (Platform Key, Key Exchange Key) beim Start, um unsignierte/schädliche Bootloader zu blockieren. *Hinweis: bekannte Sicherheitslücken existieren — kein Allheilmittel.*

**CSM (Compatibility Support Module):**
- **🇬🇧** Allows UEFI to emulate legacy BIOS behaviour for older operating systems that do not support UEFI natively.
- **🇩🇪** Ermöglicht UEFI, das klassische BIOS-Verhalten für ältere Betriebssysteme zu emulieren, die UEFI nicht nativ unterstützen.

**Coreboot (Alternative):**
- **🇬🇧** Open-source firmware project offering extremely fast boot times. Used by Google to replace proprietary server firmware in Chromebooks and data centres.
- **🇩🇪** Open-Source-Firmware-Projekt mit extrem schnellen Bootzeiten. Von Google eingesetzt, um proprietäre Server-Firmware in Chromebooks und Rechenzentren zu ersetzen.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Interfaces are contracts:** Every hardware component communicates via standardized physical and logical rules — understanding interfaces is key to diagnosing compatibility issues.
- **UEFI is not just faster BIOS:** It is a full software environment (networking, GUI, cryptographic validation) that fundamentally changes how a system boots and how security is enforced at the hardware level.

**🇩🇪**
- **Schnittstellen sind Verträge:** Jede Hardwarekomponente kommuniziert über standardisierte physikalische und logische Regeln — das Verständnis von Schnittstellen ist der Schlüssel zur Diagnose von Kompatibilitätsproblemen.
- **UEFI ist nicht nur ein schnelleres BIOS:** Es ist eine vollständige Softwareumgebung (Netzwerk, GUI, kryptografische Validierung), die grundlegend verändert, wie ein System bootet und wie Sicherheit auf Hardwareebene durchgesetzt wird.
