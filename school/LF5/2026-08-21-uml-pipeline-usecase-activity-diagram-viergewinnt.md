---
date: 2026-08-21
category: Software Development
tags: [uml, use-case, activity-diagram, requirements-engineering, user-story, software-lifecycle, LF5]
source: school
lernfeld: LF5
---

# UML Modeling Pipeline: Requirements to User Stories, Use Cases & Activity Diagrams (Connect Four Case Study)
*Date: 21-08-2026* | *Category: #software-development #uml #requirements-engineering*

---

## Context — Kontext

**🇬🇧** On Friday at school, we walked through the complete analysis and design phase of the software development lifecycle. Using the game **"Connect Four" (*Vier Gewinnt*)** as a practical example, we practiced the structured transformation pipeline: **Requirements $\rightarrow$ User Stories $\rightarrow$ Use Case Diagrams $\rightarrow$ Activity Diagrams**.

**🇩🇪** Am Freitag haben wir in der Schule die vollständige Analyse- und Entwurfsphase des Softwareentwicklungszyklus durchlaufen. Am Praxisbeispiel **„Vier Gewinnt"** haben wir die strukturierte Transformationspipeline geübt: **Anforderungen $\rightarrow$ User Story $\rightarrow$ Anwendungsfalldiagramm $\rightarrow$ Aktivitätsdiagramm**.

---

## Key Topics — Hauptthemen

### 1. The Analysis & Design Pipeline — Die Transformationspipeline

**🇬🇧** Software engineering transforms vague user needs into precise technical specifications through step-by-step refinement:
**🇩🇪** Software-Engineering überführt vage Nutzerbedürfnisse durch schrittweise Verfeinerung in präzise technische Spezifikationen:

$$\text{Anforderungen (Requirements)} \longrightarrow \text{User Story} \longrightarrow \text{Use Case Diagram} \longrightarrow \text{Aktivitätsdiagramm}$$

| Step / Schritt | Level / Ebene | Purpose / Zweck | Connect Four Example / Beispiel Vier Gewinnt |
|---|---|---|---|
| **1. Anforderung (Requirement)** | Business / Fachlich | Raw requirement / Rohe Anforderung | "Players must be able to drop chips into columns." / Spieler müssen Chips in Spalten einwerfen können. |
| **2. User Story** | User-centric / Nutzerzentriert | Agiles Format: *As a... I want to... so that...* | *"As a player, I want to choose a column so that my chip drops to the lowest free slot."* |
| **3. Use Case Diagram** | Structural / Strukturell | Maps actors to system functions | Actor: `Player` $\rightarrow$ Use Case: `Drop Chip`, `Check Win Condition` |
| **4. Aktivitätsdiagramm** | Procedural / Ablauflogik | Flowchart showing decisions, loops, and states | Step-by-step logic: Select column $\rightarrow$ Column full? $\rightarrow$ Drop $\rightarrow$ Check 4 in a row $\rightarrow$ Switch turn. |

---

### 2. UML Activity Diagram Elements — Elemente des Aktivitätsdiagramms

**🇬🇧** While Use Case diagrams show *what* the system does, Activity diagrams specify *how* the process flows step-by-step:
**🇩🇪** Während Anwendungsfalldiagramme zeigen, *was* das System tut, modellieren Aktivitätsdiagramme den genauen *Ablauf* Schritt für Schritt:

| Symbol / Element | Meaning / Bedeutung |
|---|---|
| **Initial Node / Startknoten (●)** | Starting point of the activity flow / Startpunkt des Ablaufes |
| **Action / Aktion (Rounded Box)** | A single processing step (e.g. "Validate column") / Ein einzelner Arbeitsschritt |
| **Decision / Verzweigung (◇ Diamond)** | Branching based on a condition (guard: `[valid]` vs. `[column full]`) / Bedingte Verzweigung |
| **Merge / Zusammenführung (◇ Diamond)** | Merges multiple alternative paths back into one / Führt alternative Pfade zusammen |
| **Fork / Join (Thick Bar / Balken)** | Concurrent parallel processing / Parallele Ausführung von Pfaden |
| **Final Node / Endknoten (◉)** | Termination of the entire process / Ende des Ablaufs |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **From abstract to executable:** Moving from a User Story to an Activity Diagram forces you to think about edge cases (e.g., what happens when the chosen column is already full?) before writing code.
- **Activity diagrams are visual pseudocode:** They serve as the direct blueprint for programming control structures (`if/else`, `while/for` loops).

**🇩🇪**
- **Vom Abstrakten zum Ausführbaren:** Der Übergang von der User Story zum Aktivitätsdiagramm zwingt dazu, Randfälle (z. B. was passiert, wenn die Spalte voll ist?) vor dem Programmieren zu durchdenken.
- **Aktivitätsdiagramme sind visueller Pseudocode:** Sie dienen als direkte Blaupause für die Implementierung von Kontrollstrukturen (`if/else`, Schleifen).
