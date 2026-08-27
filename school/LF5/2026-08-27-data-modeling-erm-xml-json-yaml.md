---
date: 2026-08-27
category: Software Development & Data Modeling
tags: [data-modeling, erm, database-design, xml, json, yaml, data-formats, LF5]
source: school
lernfeld: LF5
---

# Data Modeling with ERM & Text-Based Data Formats (XML vs. JSON vs. YAML)
*Date: 27-08-2026* | *Category: #data-modeling #data-formats #software-engineering*

---

## Context — Kontext

**🇬🇧** Today at school, we covered data modeling fundamentals using the **Entity-Relationship Model (ERM)** and analyzed the three primary text-based serialization formats: **XML**, **JSON**, and **YAML**, concluding with a side-by-side comparison for APIs and configuration management.

**🇩🇪** Heute haben wir die Grundlagen der Datenmodellierung mit dem **Entity-Relationship-Modell (ERM)** behandelt und die drei wichtigsten textbasierten Serialisierungsformate analysiert: **XML**, **JSON** und **YAML**, abgeschlossen mit einem direkten Vergleich für APIs und Konfigurationsmanagement.

---

## Key Topics — Hauptthemen

### 1. Graphical Data Modeling — Entity-Relationship-Modell (ERM)

**🇬🇧** ERM is an abstract conceptual framework used to design relational database schemas before implementation:
**🇩🇪** Das ERM ist ein konzeptionelles Modell zur Planung relationaler Datenbankschemata vor der technischen Umsetzung:

| Component / Komponente | Description / Beschreibung | Notation (Chen) |
|---|---|---|
| **Entity / Entität(styp)** | An identifiable object or concept (e.g. `Customer`, `Order`) / Ein eindeutig identifizierbares Objekt | ▭ Rectangle / Rechteck |
| **Attribute / Attribut** | A characteristic describing an entity (e.g. `CustomerID`, `Name`, `Price`) / Eine Eigenschaft einer Entität | ⬭ Oval / Ellipse |
| **Relationship / Beziehung** | An association linking two or more entities (e.g. `Customer` *places* `Order`) / Eine Verknüpfung zwischen Entitäten | ◇ Diamond / Raute |

**Cardinalities / Kardinalitäten:**
- **1:1** — One employee has one company laptop.
- **1:n** — One customer places multiple orders.
- **n:m** — Multiple students enroll in multiple courses (requires junction table in relational DB).

---

### 2. Text-Based Data Formats — Textbasierte Datenformate

#### A. XML (Extensible Markup Language)
- **Concept:** Tree-structured markup language using opening/closing tags and optional attributes.
- **Strengths:** Strict schema validation (XSD, DTD), self-describing, namespaces support.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<customer id="101">
    <name>Max Mustermann</name>
    <email>max@example.de</email>
    <active>true</active>
</customer>
```

#### B. JSON (JavaScript Object Notation)
- **Concept:** Lightweight, compact data-interchange format built on key-value pairs (`{}`) and ordered lists (`[]`).
- **Strengths:** Native to JavaScript/Web, highly performant parsing, standard for REST APIs.

```json
{
  "customer_id": 101,
  "name": "Max Mustermann",
  "email": "max@example.de",
  "active": true
}
```

#### C. YAML (YAML Ain't Markup Language)
- **Concept:** Human-readable data serialization format relying on strict whitespace indentation.
- **Strengths:** Cleanest syntax, native comments support (`#`), standard for CI/CD and configuration (Docker, Kubernetes).

```yaml
customer_id: 101
name: Max Mustermann
email: max@example.de
active: true
# Configuration tags
roles:
  - user
  - admin
```

---

### 3. Comparison of Data Formats — Vergleich der Datenformate

| Feature / Merkmal | XML | JSON | YAML |
|---|---|---|---|
| **Human Readability / Lesbarkeit** | 🟡 Moderate (verbose tags) | 🟢 Good | ⚡ Excellent (clean) |
| **Parsing Speed & Overhead / Performance** | 🔴 Slowest (heavy tag overhead) | ⚡ Very Fast | 🟡 Moderate (indentation parsing) |
| **Comments Support / Kommentare** | ✅ Yes (`<!-- -->`) | ❌ No | ✅ Yes (`#`) |
| **Schema Validation / Validierung** | ✅ Mature (XSD, DTD) | ✅ JSON Schema | 🟡 Possible, less common |
| **Data Types / Datentypen** | Text-only (without XSD) | String, Number, Bool, Array, Object, Null | Rich (includes dates, explicit types) |
| **Primary Use Cases / Haupteinsatz** | Legacy enterprise systems, SOAP APIs, Office OpenXML | REST APIs, Web development, NoSQL DBs | CI/CD pipelines (GitHub Actions), Docker, K8s configs |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Right tool for the right job:** Use **JSON** for fast API data transmission, **YAML** for readable configuration files, and **XML** when strict enterprise schema validation and document formatting are required.
- **ERM prevents structural database debt:** Designing clear entities, attributes, and relationships upfront eliminates data redundancy and anomalies in SQL databases.

**🇩🇪**
- **Das richtige Werkzeug für den richtigen Zweck:** Nutze **JSON** für schnellen API-Datenaustausch, **YAML** für lesbare Konfigurationsdateien und **XML**, wenn strenge Schemavalidierung und Dokumentenstrukturen erforderlich sind.
- **ERM verhindert relationale Strukturfehler:** Die saubere Modellierung von Entitäten, Attributen und Beziehungen vorab eliminiert Datenredundanzen und Anomalien in SQL-Datenbanken.
