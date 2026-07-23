---
date: 2026-07-22
category: Theory
tags: [hardware, computer-types, memory, storage, peripherals, LF2]
source: school
lernfeld: LF2
---

# Computer Types, Components, Peripherals & Memory Hierarchy
*Date: 22-07-2026* | *Category: #theory #hardware*

---

## Context — Kontext

**🇬🇧** Today at school, we explored the landscape of computer form factors — their use cases, advantages, and disadvantages. We then analysed internal components and peripherals, with a deep dive into the different memory types and their roles in system performance.

**🇩🇪** Heute haben wir die verschiedenen Computertypen und ihre Einsatzgebiete, Vor- und Nachteile analysiert. Anschließend haben wir interne Komponenten und Peripheriegeräte untersucht, mit besonderem Fokus auf die verschiedenen Speichertypen und ihre Bedeutung für die Systemleistung.

---

## Key Topics — Hauptthemen

### 1. Types of Computers — Computertypen im Überblick

| Type / Typ | Primary Use / Einsatzgebiet | ✅ Pro | ❌ Contra |
|---|---|---|---|
| **Desktop PC** | Office, gaming, workstations | High performance, fully upgradeable<br>Hohe Leistung, vollständig aufrüstbar | Not portable, requires desk space<br>Nicht mobil, benötigt Tischplatz |
| **All-in-One** | Clean office environments<br>Ordentliche Büroumgebungen | Space-saving, tidy setup<br>Platzsparend, aufgeräumtes Setup | Limited upgradability<br>Geringe Aufrüstbarkeit |
| **Laptop / Notebook** | Mobile work and study<br>Mobiles Arbeiten und Lernen | Portable, self-contained<br>Mobil, eigenständig | Less powerful per €, battery dependency<br>Weniger Leistung pro €, Akkuabhängigkeit |
| **Server** | Data storage, hosting, centralized services<br>Datenspeicherung, Hosting, zentrale Dienste | High reliability, scalable<br>Hohe Zuverlässigkeit, skalierbar | High cost, requires dedicated space & cooling<br>Hohe Kosten, benötigt eigenen Raum & Kühlung |
| **Embedded / IoT** | Industrial, smart devices<br>Industriell, smarte Geräte | Compact, energy-efficient<br>Kompakt, energieeffizient | Fixed functionality, limited power<br>Feste Funktionalität, begrenzte Rechenleistung |

### 2. Internal Components & Peripherals — Komponenten & Peripherie
- **🇬🇧** Key internal components: **CPU** (processing), **Motherboard** (interconnect), **PSU** (power supply), **GPU** (graphics), **RAM** (working memory), **Storage** (HDD/SSD).
- **🇩🇪** Wichtige interne Komponenten: **CPU** (Verarbeitung), **Mainboard** (Verbindung), **Netzteil** (Stromversorgung), **GPU** (Grafik), **RAM** (Arbeitsspeicher), **Speicher** (HDD/SSD).
- **🇬🇧** Peripherals: Input devices (keyboard, mouse, scanner), Output devices (monitor, printer, speakers), and I/O devices (touchscreen, external drives).
- **🇩🇪** Peripheriegeräte: Eingabegeräte (Tastatur, Maus, Scanner), Ausgabegeräte (Monitor, Drucker, Lautsprecher) und E/A-Geräte (Touchscreen, externe Laufwerke).

### 3. Memory Hierarchy — Speicherhierarchie

The memory hierarchy describes how speed, cost, and capacity trade off across storage levels:

| Level | Type / Typ | Speed / Geschwindigkeit | Capacity / Kapazität | Volatile? / Flüchtig? |
|---|---|---|---|---|
| 1 | **Cache (L1/L2/L3)** | ⚡ Extremely fast / Extrem schnell | KB – MB | Yes / Ja |
| 2 | **RAM** | 🔵 Very fast / Sehr schnell | 4 GB – 128 GB | Yes / Ja |
| 3 | **VRAM** | 🟢 Fast, GPU-dedicated / Schnell, GPU-dediziert | 4 GB – 24 GB | Yes / Ja |
| 4 | **SSD (NAND Flash)** | 🟡 Fast / Schnell | 256 GB – 8 TB | No / Nein |
| 5 | **HDD (Magnetic Disk / Magnetplatte)** | 🔴 Slow / Langsam | 500 GB – 20 TB | No / Nein |

- **🇬🇧** **Volatile memory** (Cache, RAM, VRAM): data is lost when power is cut. **Non-volatile** (SSD, HDD): data persists without power.
- **🇩🇪** **Flüchtiger Speicher** (Cache, RAM, VRAM): Daten gehen bei Stromverlust verloren. **Nicht-flüchtiger Speicher** (SSD, HDD): Daten bleiben ohne Strom erhalten.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Form factor = workflow:** Choosing the right computer type is a business decision — it's about matching performance, cost, portability, and maintainability to the actual use case.
- **Memory hierarchy = speed vs. cost:** The closer memory is to the CPU (Cache > RAM > SSD > HDD), the faster it is — but also the more expensive and smaller in capacity. This directly affects data processing performance.

**🇩🇪**
- **Formfaktor = Arbeitsablauf:** Die Wahl des richtigen Computertyps ist eine Geschäftsentscheidung — es geht darum, Leistung, Kosten, Mobilität und Wartbarkeit dem tatsächlichen Anwendungsfall anzupassen.
- **Speicherhierarchie = Geschwindigkeit vs. Kosten:** Je näher der Speicher an der CPU liegt (Cache > RAM > SSD > HDD), desto schneller — aber auch teurer und kleiner. Dies beeinflusst direkt die Datenverarbeitungsleistung.
