---
date: 2026-10-14
category: Systems Architecture & Data Storage
tags: [lastenheft, pflichtenheft, server-storage, sas-sata, nas, cloud-storage, kritis, datacenter-cooling, LF2]
source: school
lernfeld: LF2
---

# Specifications (Lastenheft vs. Pflichtenheft), Server Storage, KRITIS & Data Center Climate Control
*Date: 14-10-2026* | *Category: #project-management #storage #datacenter-infrastructure #compliance*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.2 / KW42 Tag 3**), we analyzed project specification methodologies (**Lastenheft vs. Pflichtenheft** according to DIN 69901-5), evaluated enterprise storage architectures (Server SAS/SATA drives, **NAS vs. Cloud Storage**), reviewed regulatory requirements for Critical IT Infrastructure (**KRITIS**), established physical environmental rules for server rooms (temperature, humidity, the "Rule of 100"), and documented NAS integration via AVM Fritz!Box.

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.2 / KW42 Tag 3**) Spezifikationsdokumente im Projektmanagement (**Lastenheft vs. Pflichtenheft** nach DIN 69901-5), Speicherarchitekturen für Server (SAS/SATA, **NAS vs. Cloud**), gesetzliche Vorgaben für Kritische Infrastrukturen (**KRITIS**), physische Grenzwerte für Serverräume (Temperatur, Feuchtigkeit, „100er-Regel“) sowie die NAS-Einbindung an einer Fritz!Box analysiert.

---

## Key Topics — Hauptthemen

### 1. Requirements vs. Functional Specification — Lastenheft vs. Pflichtenheft

**🇬🇧** A foundational IHK exam topic defining project boundaries between client and contractor:
**🇩🇪** Ein zentrales IHK-Prüfungsthema zur Abgrenzung der Verantwortlichkeiten im Projekt:

| Dimension | Lastenheft (Requirements Specification) | Pflichtenheft (System/Functional Specification) |
|---|---|---|
| **Author / Ersteller** | **Auftraggeber (Client / Buyer)** | **Auftragnehmer (Contractor / Developer)** |
| **Core Question / Kernfrage** | **"WAS und WOFÜR?"** (What is needed and why?) | **"WIE und WOMIT?"** (How and with what tools?) |
| **Content / Inhalt** | Business objectives, user stories, general constraints, acceptance criteria. | Technical architecture, database schemas, APIs, chosen frameworks, delivery schedule. |
| **Legal Role / Rolle** | Basis for the Request for Proposal (Ausschreibung / Angebot). | Basis for contract signing and formal technical acceptance (*Abnahme*). |

---

### 2. Server Drives & Storage Architectures — Serverfestplatten & NAS vs. Cloud

| Storage Architecture / Medium | Technology & Protocol | Key Advantages / Vorteile | Tradeoffs & Limitations / Nachteile |
|---|---|---|---|
| **Server HDD/SSD (SAS)** | Serial Attached SCSI ($12\text{ Gbps}$), full-duplex, dual-ported. | Designed for $24/7$ continuous load, high IOPS, lowest Unrecoverable Read Error (URE) rate ($10^{-16}$). | Higher cost per TB than consumer SATA. |
| **NAS (Network Attached Storage)** | Dedicated storage appliance connected via LAN (SMB/NFS/iSCSI). | Local data sovereignty, one-time hardware cost, high LAN bandwidth, independent of internet uplink. | Requires internal backup, physical security, and maintenance overhead. |
| **Enterprise Cloud Storage** | Remote hyperscaler infrastructure (AWS S3, Azure Blob). | Infinite elastic scalability, multi-region redundancy, zero hardware management. | Recurring monthly operational cost (OpEx), compliance risks (DSGVO), high latency compared to local LAN. |

---

### 3. Critical Infrastructure (KRITIS) & Environmental Server Room Controls

**KRITIS (Kritische Infrastrukturen nach BSI):**
- Facilities of vital importance to the state and public community (Energy, Healthcare, Water, Finance/Insurance, Transport/Logistics, IT/Telecommunications).
- Subject to mandatory IT-Sicherheitsgesetz compliance: regular security audits, certified ISMS (ISO 27001), and immediate reporting of security breaches to the BSI.

**Physical Server Room Environmental Standards:**

| Parameter | Recommended Range / Richtwert | Risk if Exceeded / Unterschritten |
|---|---|---|
| **Temperature** | $20^\circ\text{C}$ to $24^\circ\text{C}$ ($68^\circ\text{F}\text{--}75^\circ\text{F}$) | Overheating causes thermal CPU throttling, capacitor degradation, hardware shutdown. |
| **Relative Humidity (r.F.)** | $40\%$ to $60\%$ | $<30\% \rightarrow$ Risk of Electrostatic Discharge (**ESD**); $>70\% \rightarrow$ Risk of moisture condensation and corrosion. |
| **The "Rule of 100" (*100er-Regel*)** | $\text{Temp } (^\circ\text{F}) + \text{Humidity } (\%) < 100$ | Empirical rule to prevent condensation: as temperature rises, relative humidity must remain low. |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Lastenheft specifies the problem; Pflichtenheft specifies the solution:** Conflating the two leads to scope creep and contractual disputes during software development.
- **Climate control is hardware protection:** Maintaining humidity within $40\%\text{--}60\%$ is as critical as temperature control — too dry causes ESD sparks that kill microchips, while too humid creates condensation on motherboards.

**🇩🇪**
- **Das Lastenheft beschreibt das Problem, das Pflichtenheft die Lösung:** Die saubere Trennung verhindert Scope Creep und rechtliche Konflikte bei der Projektabnahme.
- **Klimaregelung ist aktiver Komponentenschutz:** Die Einhaltung von $40\%\text{--}60\%$ Luftfeuchtigkeit schützt Hardware vor unbemerkten ESD-Zerstörungen (zu trocken) und Korrosion (zu feucht).
