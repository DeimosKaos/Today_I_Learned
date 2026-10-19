---
date: 2026-10-08
category: Hardware Engineering & Environmental Standards
tags: [power-supply-units, psu, 80-plus-efficiency, rohs-directive, monitor-panels, ips-va-oled, display-standards, LF2]
source: school
lernfeld: LF2
---

# Power Supply Units (PSU & 80 PLUS), RoHS Environmental Directive & Display Panel Technologies
*Date: 08-10-2026* | *Category: #hardware #power-management #environmental-standards #display-technologies*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.2 / KW41 Tag 4**), we investigated electrical power delivery in computer systems: switching power supply units (**PSUs**), integrated electrical protection circuits, the **80 PLUS** energy efficiency certification framework, the European environmental **RoHS Directive**, and modern visual display panel technologies (**IPS, VA, TN, OLED**).

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.2 / KW41 Tag 4**) die elektrische Energieversorgung von Computersystemen behandelt: Schaltnetzteile (**Netzteile / PSU**), integrierte Schutzschaltungen, das **80 PLUS**-Energieeffizienzprogramm, die europäische Umweltschutzrichtlinie **RoHS** sowie moderne Bildschirm-Paneltechnologien (**IPS, VA, TN, OLED**).

---

## Key Topics — Hauptthemen

### 1. Power Supply Units (PSU) & Protection Circuits — Netzteile & Schutzschaltungen

**Internal Circuit Protections (Schutzschaltungen):**
- **OVP / UVP (Over/Under Voltage Protection):** Cuts power if $12\text{V}$, $5\text{V}$, or $3.3\text{V}$ rails deviate beyond safe thresholds.
- **SCP (Short Circuit Protection):** Shuts down instantly upon dead short circuit to prevent fire.
- **OPP / OCP (Over Power / Over Current Protection):** Protects against catastrophic overload on individual rails.
- **OTP (Over Temperature Protection):** Shuts down PSU if internal cooling fan fails.

**Modularity (Kabelmanagement):**
- *Non-modular:* All cables hardwired (cheap, messy airflow).
- *Semi-modular:* 24-pin ATX and 8-pin CPU cables hardwired; PCIe and SATA modular.
- *Fully modular:* Every cable detachable (optimal airflow, clean assembly).

---

### 2. The 80 PLUS Energy Efficiency Certification — 80 PLUS Effizienzklassen

**🇬🇧** Efficiency defines how much AC wall power is converted to DC computing power vs. wasted as heat:
**🇩🇪** Der Wirkungsgrad bestimmt, wie viel Netzstrom in nutzbare DC-Leistung umgewandelt wird:

$$\text{Efficiency } \eta = \frac{P_{DC\text{ (Component Draw)}}}{P_{AC\text{ (Wall Meter Draw)}}} \times 100\%$$

| 80 PLUS Tier | Efficiency at 20% Load | Efficiency at 50% Load (Optimal) | Efficiency at 100% Load |
|---|---|---|---|
| **80 PLUS (Standard)** | $80\%$ | $80\%$ | $80\%$ |
| **80 PLUS Bronze** | $82\%$ | $85\%$ | $82\%$ |
| **80 PLUS Silver** | $85\%$ | $88\%$ | $85\%$ |
| **80 PLUS Gold** | $87\%$ | $90\%$ | $87\%$ |
| **80 PLUS Platinum** | $90\%$ | $92\%$ | $89\%$ |
| **80 PLUS Titanium** | **$92\%$** | **$94\%$** | **$90\%$** |

> 💡 **Sizing Rule of Thumb:** Power supplies operate at peak electrical efficiency around **$50\%$ load**. A heavily oversized PSU (e.g. $1000\text{ W}$ unit running a $100\text{ W}$ office PC at $10\%$ load) drops to inefficient operating curves.

---

### 3. Environmental Compliance: The RoHS Directive

- **RoHS (Restriction of Hazardous Substances — Directive 2011/65/EU):**
  - Restricts the use of specific hazardous materials in electronic and electrical equipment across the European Union.
  - Prohibits: **Lead (Pb)** (transitioned the industry to lead-free soldering), **Mercury (Hg)**, **Cadmium (Cd)**, **Hexavalent Chromium**, and toxic flame retardants (PBB/PBDE, Phthalates).
  - Essential requirement for the **CE mark** on European enterprise IT hardware.

---

### 4. Display Panel Technologies — Monitortechnologien im Vergleich

| Panel Technology | Operating Principle / Aufbau | Contrast Ratio / Kontrast | Viewing Angles / Blickwinkel | Best Suited For / Einsatz |
|---|---|---|---|---|
| **IPS (In-Plane Switching)** | Liquid crystal molecules rotate horizontally parallel to glass plane. | $1000:1$ | ⚡ Excellent ($178^\circ$, color-accurate from all angles) | Graphic design, data dashboards, software development, medical imaging. |
| **VA (Vertical Alignment)** | Liquid crystal molecules align perpendicular to glass when voltage applied. | **$3000:1\text{--}4000:1$** (Deep true blacks) | 🟡 Moderate (slight color shift off-axis) | General office work, media consumption, curved productivity displays. |
| **TN (Twisted Nematic)** | Twisted crystals block or pass light via fast helical rotation. | Low ($800:1$) | 🔴 Poor (severe vertical color inversion) | Budget legacy office monitors, e-sports gaming. |
| **OLED (Organic LED)** | Organic self-emissive subpixels (no backlight required). | ♾️ Infinite contrast (individual pixels turn completely off) | ⚡ Flawless | Premium color grading, high-end professional media production. |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **80 PLUS Gold is the enterprise sweet spot:** High energy efficiency directly translates into thousands of Euros saved on air conditioning and electric bills across large corporate workstation fleets.
- **IPS is the workplace ergonomics standard:** Color consistency and wide viewing angles reduce eye strain during full-day data analysis sessions compared to shifting TN panels.

**🇩🇪**
- **80 PLUS Gold ist der wirtschaftliche Standard:** Hohe Netzteileffizienz spart in Unternehmen doppelt — weniger Stromverbrauch an der Steckdose und geringere Wärmelast für die Raumklimatisierung.
- **IPS ist Ergonomiestandard am Arbeitsplatz:** Stabile Blickwinkel und neutrale Farbwiedergabe verhindern visuelle Ermüdung bei ganztägiger Daten- und Prozessarbeit.
