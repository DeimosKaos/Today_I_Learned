---
date: 2026-08-19
category: Software Development
tags: [software-development, programming-languages, compiler, interpreter, jit, cpu-architecture, boolean-algebra, eva-prinzip, LF5]
source: school
lernfeld: LF5
---

# Programming Language Classification, CPU Execution, Boolean Algebra & EVA Principle
*Date: 19-08-2026* | *Category: #software-development #computer-architecture*

---

## Context — Kontext

**🇬🇧** Today at school, we explored how programming languages are classified (by generation, paradigm, and execution model: compiled vs. interpreted vs. JIT). We also studied what happens at the hardware level during program execution (memory addressing and the CPU instruction cycle), followed by a review of Boolean algebra and the foundational **EVA principle**.

**🇩🇪** Heute haben wir in der Schule behandelt, wie Programmiersprachen klassifiziert werden (nach Generation, Paradigma und Ausführungsmodell: kompiliert vs. interpretiert vs. JIT). Zudem haben wir untersucht, was auf Hardwareebene beim Programmstart passiert (Speicheradressierung und CPU-Befehlszyklus), gefolgt von einer Wiederholung der booleschen Algebra und des grundlegenden **EVA-Prinzips**.

---

## Key Topics — Hauptthemen

### 1. Classification of Programming Languages — Klassifizierung von Programmiersprachen

**Execution Methods / Ausführungsmethoden:**

| Method / Methode | How it works / Funktionsweise | ✅ Pro | ❌ Contra | Examples / Beispiele |
|---|---|---|---|---|
| **Compiled / Kompiliert** | Translates entire source code into machine code (`.exe`) before execution / Übersetzt den gesamten Code vor der Ausführung in Maschinencode | ⚡ Maximum execution speed, standalone / Maximale Ausführungsgeschwindigkeit | Recompilation needed for changes, OS-dependent / Neukompilierung nötig, OS-abhängig | C, C++, Rust, Go |
| **Interpreted / Interpretiert** | Reads and executes code line-by-line via an interpreter / Liest und führt Code Zeile für Zeile über einen Interpreter aus | 🔄 Platform independent, rapid prototyping / Plattformunabhängig, schnelle Entwicklung | 🐢 Slower execution speed / Langsamere Ausführung | Python, Bash, Ruby |
| **JIT (Just-In-Time)** | Compiles bytecode into machine code at runtime / Kompiliert Bytecode während der Laufzeit in Maschinencode | 🚀 Combines portability with high speed / Verbindet Portabilität mit hoher Geschwindigkeit | Higher initial memory footprint / Höherer Speicherbedarf beim Start | Java (JVM), C# (.NET), JavaScript (V8) |

**Generations & Paradigms / Generationen & Paradigmen:**
- **Generations:** From 1GL (Machine Code) and 2GL (Assembly) to 3GL (High-Level procedural/OOP like C/Java), 4GL (SQL, R), and 5GL (AI/Constraint-based logic).
- **Paradigms:** Procedural (step-by-step procedures), Object-Oriented (encapsulated objects/classes), Functional (immutable pure functions), Declarative (specifying *what* rather than *how*).

---

### 2. Hardware Execution & Memory Addressing — Programmstart & Hardware-Ablauf

**What happens when a program starts / Was beim Programmstart passiert:**
1. **Loading:** OS transfers the executable from disk into RAM (Memory Allocation & Addressing / Speicheradressierung).
2. **Fetch-Decode-Execute Cycle:**
   - **Fetch:** CPU fetches the instruction from RAM using the Program Counter.
   - **Decode:** Control Unit decodes the binary instruction.
   - **Execute:** ALU (Arithmetic Logic Unit) executes the operation and stores the result.

---

### 3. Boolean Algebra & EVA Principle — Boolesche Algebra & EVA-Prinzip

**The EVA Principle (Eingabe – Verarbeitung – Ausgabe / Input – Processing – Output):**
- The universal baseline for all computer processes and algorithms:

$$\text{Eingabe (Input)} \longrightarrow \text{Verarbeitung (Processing)} \longrightarrow \text{Ausgabe (Output)}$$

**Boolean Algebra Review / Boolesche Algebra:**
- Practiced logical operators (**AND / Konjunktion**, **OR / Disjunktion**, **NOT / Negation**) and boolean laws (Identity, Commutative, Distributive, and **De Morgan's Laws**):
  $$\neg(A \land B) = \neg A \lor \neg B$$
  $$\neg(A \lor B) = \neg A \land \neg B$$

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Tradeoff between speed and portability:** Compiled languages offer peak performance; interpreted languages offer portability; JIT strikes a modern balance.
- **The CPU is purely mechanical at its core:** The Fetch-Decode-Execute cycle and Boolean logic show how software abstractions translate directly into physical electrical switches.
- **EVA is the foundation:** Every data pipeline, software feature, and process analysis workflow follows the Input-Processing-Output pattern.

**🇩🇪**
- **Kompromiss zwischen Geschwindigkeit und Portabilität:** Kompilierte Sprachen bieten maximale Leistung; interpretierte Sprachen bieten Portabilität; JIT schafft einen modernen Ausgleich.
- **Die CPU arbeitet im Kern rein mechanisch:** Der Fetch-Decode-Execute-Zyklus und die boolesche Logik zeigen, wie Softwareabstraktionen direkt in physische Schaltungen übersetzt werden.
- **EVA ist das Fundament:** Jede Datenpipeline, jede Softwarefunktion und jeder Prozessanalyse-Workflow folgt dem Muster Eingabe-Verarbeitung-Ausgabe.
