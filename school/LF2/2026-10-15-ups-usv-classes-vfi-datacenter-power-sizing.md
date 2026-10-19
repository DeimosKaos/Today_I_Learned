---
date: 2026-10-15
category: Data Center Infrastructure & Power
tags: [ups, usv, power-supply, vfd, vi, vfi, datacenter-cooling, power-factor, capacity-planning, LF2]
source: school
lernfeld: LF2
---

# Uninterruptible Power Supplies (UPS/USV: VFD, VI, VFI) & Data Center Power Sizing
*Date: 15-10-2026* | *Category: #datacenter-infrastructure #power-systems #electrical-engineering #availability*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.2 / KW42 Tag 4**), we investigated data center cooling architectures (Hot Aisle / Cold Aisle containment, PUE metrics) and completed a deep engineering breakdown of **Uninterruptible Power Supply (UPS / USV)** systems: analyzing the three standardized topologies (**VFD, VI, VFI** according to IEC 62040-3), performance tradeoffs, and mathematical sizing calculations (apparent power $\text{VA}$ vs. active power $\text{W}$, power factor $\cos \varphi$, and expansion headroom).

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.2 / KW42 Tag 4**) Kühlkonzepte für Rechenzentren (Warmgang-/Kaltgang-Einhausung, PUE) und eine umfassende technische Analyse von **Unterbrechungsfreien Stromversorgungen (USV)** durchgeführt: die drei Norm-Klassen (**VFD, VI, VFI** nach IEC 62040-3), Vor- und Nachteile sowie Berechnungen zur Dimensionierung (Scheinleistung $\text{VA}$ vs. Wirkleistung $\text{W}$, Leistungsfaktor $\cos \varphi$ und Leistungsreserve).

---

## Key Topics — Hauptthemen

### 1. Data Center Thermal Architecture — Warmgang- & Kaltgang-Einhausung

- **Physical Separation:** Preventing the mixing of chilled intake air and hot server exhaust air.
- **Cold Aisle Containment (Kaltgangeinhausung):** Enclosing the corridor where server intake fans pull cold air ($20\text{--}24^\circ\text{C}$).
- **PUE (Power Usage Effectiveness):**
  $$\text{PUE} = \frac{\text{Total Facility Energy Consumption}}{\text{IT Equipment Energy Consumption}}$$
  *(Target: as close to $1.0$ as possible; legacy centers $\approx 1.8$, modern hyper-efficient centers $<1.2$).*

---

### 2. The Three UPS/USV Standard Classes (IEC 62040-3) — USV-Klassen

| USV Class (IEC 62040-3) | Topology & Name | Operating Principle / Funktionsweise | Switchover Time / Umschaltzeit | Primary Use Case / Einsatzgebiet |
|---|---|---|---|---|
| **Class 3: VFD** | **Offline / Standby** *(Voltage & Frequency Dependent)* | Normal power bypasses directly to load; inverter only activates upon total grid failure. | $4\text{--}10\text{ ms}$ (Interruption occurs) | Non-critical single workstations, small office PCs, cash registers. |
| **Class 2: VI** | **Line-Interactive** *(Voltage Independent)* | Automatic Voltage Regulation (**AVR**) compensates for minor undervoltage/overvoltage without switching to battery. | $2\text{--}4\text{ ms}$ | Small department servers, local network switches, NAS appliances. |
| **Class 1: VFI** | **Online / Double Conversion** *(Voltage & Frequency Independent)* | **Continuous double conversion:** $\text{AC} \rightarrow \text{DC} \rightarrow \text{AC}$. Load is always powered purely by the internal inverter. Zero switchover delay; pure sine wave. | **$0\text{ ms}$ (Zero interruption)** | Mission-critical servers, data center core racks, healthcare life-support systems, telecommunication nodes. |

---

### 3. UPS Power Dimensioning & Sizing Math — USV-Berechnung

**🇬🇧 Mathematical Relationship: Apparent Power ($S$) vs. Active Power ($P$):**
$$\text{Active Power } P \text{ (Watts, W)} = \text{Apparent Power } S \text{ (Volt-Amperes, VA)} \times \text{Power Factor } (\cos \varphi)$$
$$\text{Required USV Capacity } S \text{ (VA)} = \frac{\text{Total Server Load } P \text{ (W)}}{\cos \varphi} \times (1 + \text{Safety Margin})$$

#### Practical Sizing Example / Rechenbeispiel:
- **Given Server Rack Load:** $4$ servers consuming $450\text{ W}$ each $\rightarrow P_{total} = 4 \times 450\text{ W} = \mathbf{1800\text{ W}}$.
- **Power Factor of Power Supplies ($\cos \varphi$):** $0.85$.
- **Required Minimum Apparent Power:**
  $$S_{base} = \frac{1800\text{ W}}{0.85} \approx \mathbf{2118\text{ VA}}$$
- **Required Safety & Expansion Reserve ($+25\%$):**
  $$S_{rated} = 2118\text{ VA} \times 1.25 = \mathbf{2647.5\text{ VA}}$$
- **Selected UPS Model:** Enterprise $3000\text{ VA}$ ($3\text{ kVA}$) **VFI Online UPS** with SNMP network management card to trigger automated graceful server shutdown (via NUT / Network UPS Tools) before battery exhaustion.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **VFI is mandatory for mission-critical IT:** Consumer offline UPS (VFD) units exhibit a $4\text{--}10\text{ ms}$ switchover gap that sensitive server redundant power supplies cannot tolerate. Only VFI double-conversion provides true zero-millisecond continuous power.
- **Never size a UPS based solely on Watts:** Equipment specifications must account for inductive/capacitive reactive power ($\text{VA}$ vs. $\text{W}$) and factor in at least a $20\text{--}30\%$ expansion buffer to avoid catastrophic UPS overload during startup peak currents.

**🇩🇪**
- **VFI ist im Serverraum Pflicht:** Einfache Offline-USVs (VFD) haben Umschaltzeiten von $4\text{--}10\text{ ms}$, was bei empfindlichen Servernetzteilen zum Neustart führen kann. Nur VFI-Online-USVs bieten echte $0\text{ ms}$ Umschaltzeit und saubere Sinusspannung.
- **USV niemals nur nach Watt dimensionieren:** Scheinleistung ($\text{VA}$) und Wirkleistung ($\text{W}$) weichen durch den Leistungsfaktor ($\cos \varphi$) voneinander ab. Eine Reserve von $20\text{--}30\%$ fängt Einschaltströme sicher ab.
