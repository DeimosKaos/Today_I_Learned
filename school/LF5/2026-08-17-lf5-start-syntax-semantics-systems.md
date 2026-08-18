---
date: 2026-08-17
category: Software Development
tags: [software-development, markdown, drawio, syntax, semantics, linter, systems-theory, LF5]
source: school
lernfeld: LF5
---

# LF5 Start — Software Development Fundamentals: Tools, Syntax & Systems Theory
*Date: 17-08-2026* | *Category: #theory #software-development*

---

## Context — Kontext

**🇬🇧** Today marked the start of **Lernfeld 5 (LF5): Software Development**. We introduced the key tools (Draw.io, Markdown) and established the foundational vocabulary of software engineering: syntax vs. semantics, the role of a linter, the IEEE definition of software, and the formal definition of a system.

**🇩🇪** Heute begann **Lernfeld 5 (LF5): Softwareentwicklung**. Wir haben die wichtigsten Werkzeuge (Draw.io, Markdown) vorgestellt und das grundlegende Vokabular der Softwareentwicklung erarbeitet: Syntax vs. Semantik, die Rolle eines Linters, die IEEE-Definition von Software und die formale Definition eines Systems.

---

## Key Topics — Hauptthemen

### 1. Tools — Werkzeuge

| Tool | What it is / Was es ist | How to get it / Installation |
|---|---|---|
| **Draw.io** | Diagram drawing app — flowcharts, UML, BPMN / Diagramm-Zeichenanwendung | VS Code Extension (Side Menu → Extensions) |
| **Markdown** | Lightweight markup language for structured text / Einfache Auszeichnungssprache für strukturierten Text | Native in VS Code, GitHub, Notion — file extension: `.md` |

**🇬🇧** Markdown allows creating headers, lists, links, and emphasis using simple readable characters — without complex word processors.
**🇩🇪** Markdown ermöglicht das Erstellen von Überschriften, Listen, Links und Hervorhebungen mit einfachen lesbaren Zeichen — ohne komplexe Textverarbeitungsprogramme.

---

### 2. Core Concepts — Grundbegriffe der Softwareentwicklung

#### Syntax
- **🇬🇧** The **rules and structure** of a programming language — defines how code must be written to be correctly interpreted and executed (grammar, keywords, operators, element order).
- **🇩🇪** Die **Regeln und Struktur** einer Programmiersprache — legt fest, wie Code geschrieben werden muss, damit er korrekt interpretiert und ausgeführt werden kann (Grammatik, Schlüsselwörter, Operatoren, Anordnung).

#### Semantik
- **🇬🇧** The **meaning and interpretation** of code — what the code actually *does* and what effect it has on data or program state, independent of syntactic correctness.
- **🇩🇪** Die **Bedeutung und Interpretation** von Code — was der Code tatsächlich *tut* und welche Auswirkungen er auf Daten oder den Programmzustand hat, unabhängig von der syntaktischen Korrektheit.

**The key distinction / Die wichtige Unterscheidung:**

| | Syntax correct? / Korrekte Syntax? | Semantic meaning? / Semantischer Sinn? |
|---|---|---|
| `"Ein Esel lese nie."` | ✅ | ✅ Meaningful sentence / Sinnvoller Satz |
| `"Lorem ipsum dolor sit amet."` | ✅ | ❌ Syntactically valid, semantically empty / Syntaktisch korrekt, semantisch sinnleer |

#### Linter
- **🇬🇧** A **linter** is a static analysis tool that checks source code for potential errors, style issues, and violations of coding standards — before the code is run.
- **🇩🇪** Ein **Linter** ist ein statisches Analysewerkezeug, das Quellcode auf potenzielle Fehler, Stilprobleme und Verstöße gegen Programmierstandards prüft — bevor der Code ausgeführt wird.

---

### 3. Software — Definition (IEEE Standard 610.12)

> **🇬🇧** *"Software encompasses all programs, prescribed procedures, documentation, and data required for the operation of a computer system."*
>
> **🇩🇪** *"Software umfasst alle Programme, vorgeschriebenen Abläufe, Dokumentation und Daten, die zum Betrieb eines Rechnersystems erforderlich sind."*

**🇬🇧** Note: software is not just code — it includes documentation and data as integral parts.
**🇩🇪** Hinweis: Software ist nicht nur Code — sie umfasst Dokumentation und Daten als integrale Bestandteile.

---

### 4. System Theory — Systemtheorie

**🇬🇧** A **system** is defined by the following properties:
**🇩🇪** Ein **System** ist durch folgende Eigenschaften definiert:

| Property / Eigenschaft | Description / Beschreibung |
|---|---|
| **Components in relation / Komponenten in Beziehung** | A system consists of parts that interact with each other / Ein System besteht aus Teilen, die miteinander in Beziehung stehen |
| **Boundary / Systemgrenze** | Separated from its relevant environment by a defined boundary / Durch eine Grenze von seiner relevanten Umgebung getrennt |
| **Interfaces / Schnittstellen** | Interacts with its environment through defined interfaces / Interagiert über Schnittstellen mit seiner Umwelt |
| **Subsystems** | Can contain subsystems / Kann Subsysteme enthalten |
| **State / Zustand** | Is at a specific state at any given moment / Befindet sich zu jedem Zeitpunkt in einem konkreten Zustand |

**Two structural dimensions / Zwei Strukturdimensionen:**

| Dimension | German term | What it describes / Beschreibung |
|---|---|---|
| **Static structure** | *Aufbaustruktur* | The architecture: which components exist and how they relate / Die Architektur: welche Komponenten existieren und wie sie sich zueinander verhalten |
| **Dynamic behaviour** | *Ablaufstruktur* | The processes: how the system behaves over time / Die Prozesse: wie sich das System über Zeit verhält |

> 💡 **🇬🇧** Key insight: the *Aufbaustruktur* (static structure) **enables** the *Ablaufstruktur* (behaviour). You cannot have dynamic behaviour without a defined static architecture.
> 💡 **🇩🇪** Schlüsselerkenntnis: Die *Aufbaustruktur* **ermöglicht** die *Ablaufstruktur*. Ohne eine definierte statische Architektur kann es kein dynamisches Verhalten geben.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Syntax ≠ Semantics:** Code can be syntactically perfect and logically wrong at the same time. A linter catches syntax issues; testing catches semantic ones.
- **Software is more than code:** The IEEE definition explicitly includes documentation and data — a reminder that professional software development is a discipline, not just writing lines of code.
- **Systems thinking is universal:** The system model (boundary, interfaces, state, subsystems) applies to software, organizations, and machines alike — it is the foundation of process and data analysis.

**🇩🇪**
- **Syntax ≠ Semantik:** Code kann syntaktisch perfekt und logisch falsch zugleich sein. Ein Linter findet Syntaxfehler; Tests finden semantische Fehler.
- **Software ist mehr als Code:** Die IEEE-Definition schließt ausdrücklich Dokumentation und Daten ein — eine Erinnerung daran, dass professionelle Softwareentwicklung eine Disziplin ist, kein bloßes Schreiben von Code.
- **Systemdenken ist universell:** Das Systemmodell (Grenze, Schnittstellen, Zustand, Subsysteme) gilt für Software, Organisationen und Maschinen gleichermaßen — es ist das Fundament der Prozess- und Datenanalyse.
