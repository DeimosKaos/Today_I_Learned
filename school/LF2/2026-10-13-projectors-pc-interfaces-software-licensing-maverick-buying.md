---
date: 2026-10-13
category: IT Hardware & Software Licensing
tags: [projectors, display-technologies, pc-interfaces, ports, software-licensing, open-source, maverick-buying, LF2]
source: school
lernfeld: LF2
---

# Projector Technologies, PC Interface Topology, Software Licensing Models & Maverick Buying
*Date: 13-10-2026* | *Category: #hardware #peripherals #licensing #procurement-governance*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.2 / KW42 Tag 2**), we evaluated visual display presentation hardware (comparing projector technologies: LCD, DLP, LED, Laser), mapped all modern internal and external PC interfaces, analyzed software licensing legal structures (Proprietary, Open Source, OEM, Volume Licensing), and revisited the financial and operational risks of **Maverick Buying**.

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.2 / KW42 Tag 2**) Präsentationstechnologien (Vergleich von Beamer-Technologien: LCD, DLP, LED, Laser), alle modernen internen und externen PC-Schnittstellen, Software-Lizenzmodelle (Proprietär, Open Source, OEM, Volumenlizenzen) sowie die Risiken des **Maverick Buying** im Beschaffungsprozess analysiert.

---

## Key Topics — Hauptthemen

### 1. Projector Display Technologies — Beamerarten im Vergleich

| Technology / Technologie | Working Principle / Funktionsweise | ✅ Advantages / Vorteile | ❌ Disadvantages / Nachteile |
|---|---|---|---|
| **LCD (Liquid Crystal Display)** | Split dichroic mirrors route RGB light through 3 distinct liquid crystal panels. | Natural color reproduction, sharp text clarity, no moving color wheels. | Lower black levels/contrast, dust filter maintenance required. |
| **DLP (Digital Light Processing)** | Light bounces off millions of microscopic tilting mirrors on a DMD chip through a spinning color wheel. | High contrast, deep blacks, compact sealed optical engine (low maintenance). | Risk of visual "rainbow effect" (*Regenbogeneffekt*) for sensitive eyes. |
| **LED Projector** | Solid-state red, green, and blue LEDs replace the traditional high-pressure bulb. | Instant on/off, low power consumption, extremely long lifespan ($>20,000\text{ h}$). | Lower peak lumen brightness; best suited for dimmed or smaller meeting rooms. |
| **Laser Projector** | Solid-state blue/phosphor laser light engine illuminates DLP or 3LCD chips. | Maximum brightness ($>5,000\text{ ANSI-Lumen}$), instant startup, zero lamp replacement, superior color gamut. | Higher initial acquisition cost. |

---

### 2. Modern PC Interface Mapping — Schnittstellen eines PCs im Überblick

| Interface / Schnittstelle | Transmission Type / Signal | Max Bandwidth / Specification | Typical Application |
|---|---|---|---|
| **Thunderbolt 4 / USB4** | Serial, High-Speed (PCIe + DP tunneling) | up to $40\text{ Gbps}$ (USB-C physical connector) | Docking stations, external GPUs, high-speed NVMe storage, dual 4K displays. |
| **DisplayPort (DP 2.1)** | Digital packetized video & audio | up to $80\text{ Gbps}$ (UHBR20) | High-refresh rate professional PC monitors, Daisy-Chaining (MST). |
| **HDMI 2.1** | Digital audio & video | up to $48\text{ Gbps}$ (FRL) | TVs, projectors, conference room monitors. |
| **RJ-45 (Ethernet)** | Balanced twisted pair | $1\text{ Gbps} \ / \ 2.5\text{ Gbps} \ / \ 10\text{ Gbps}$ | Wired local area network infrastructure. |
| **PCIe 5.0 (Internal)** | Serial point-to-point bus ($x1\text{--}x16$ lanes) | up to $64\text{ GB/s}$ ($x16$ slot) | Graphics cards (GPUs), high-speed M.2 NVMe SSDs. |
| **SATA III (Internal)** | Serial storage bus | $6\text{ Gbps} \ (\approx 600\text{ MB/s})$ | Legacy $2.5''$ SSDs and $3.5''$ HDDs. |

---

### 3. Software Licensing Taxonomy — Software-Lizenzmodelle

```
Software Licenses
  ├── Proprietary / Closed Source
  │     ├── Commercial (Named User / Per-Seat vs. Concurrent Floating User)
  │     ├── OEM (Original Equipment Manufacturer - tied to specific hardware motherboard)
  │     └── Volume Licensing (Enterprise agreements, Microsoft EA, MAK / KMS activation)
  └── Open Source Software (OSS)
        ├── Permissive (MIT, Apache 2.0, BSD) → Few restrictions; can be incorporated into proprietary code.
        └── Copyleft (GPL v2/v3, AGPL) → Derivative works MUST remain open source under the same license.
```

---

### 4. Maverick Buying & IT Governance — Risiken unkontrollierter Beschaffung

**🇬🇧 Problem Statement:** When employees bypass corporate procurement channels to purchase software licenses, SaaS subscriptions, or peripheral devices independently.
**🇩🇪 Problemstellung:** Wenn Mitarbeiter eigenmächtig Hard- oder Software ohne Abstimmung mit dem offiziellen IT-Einkauf beschaffen.

- **Financial Impact:** Forfeiting negotiated enterprise volume discounts (*Rahmenverträge*), hidden recurring SaaS credit card charges.
- **IT Security & Compliance:** Creation of unmonitored **Shadow IT (*Schatten-IT*)**, data stored outside corporate backup boundaries, risk of non-compliance with DSGVO/GDPR.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Laser projectors dominate modern enterprise setups:** The elimination of toxic mercury bulbs, combined with instant boot-up and zero lamp maintenance over 20,000 hours, offsets the initial price tag.
- **License compliance requires continuous auditing:** Understanding the difference between permissive (MIT) and copyleft (GPL) licenses is vital for software developers and data analysts to prevent legal exposure.

**🇩🇪**
- **Laser-Beamer setzen sich im Unternehmen durch:** Keine Lampenwechsel, quecksilberfreier Betrieb und sofortige Betriebsbereitschaft amortisieren die höheren Anschaffungskosten.
- **Lizenz-Compliance erfordert strukturierte Audits:** Der Unterschied zwischen permissiven (MIT) und Copyleft-Lizenzen (GPL) schützt Entwicklungsteams vor teuren Abmahnungen und Urheberrechtsverletzungen.
