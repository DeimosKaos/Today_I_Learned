---
date: 2026-08-28
category: Software Development & IT Security
tags: [it-security, gdpr, dsgvo, bdsg, cia-triad, tom, iso-27001, bsi-grundschutz, geschgehg, git, LF5]
source: school
lernfeld: LF5
---

# Data Protection, IT Security Frameworks (ISO 27001, BSI, GeschGehG) & Git Version Control
*Date: 28-08-2026* | *Category: #it-security #data-protection #compliance #git*

---

## Context — Kontext

**🇬🇧** Today at school, we explored the critical distinctions between **Data Protection (*Datenschutz*)**, **Data Security (*Datensicherheit*)**, and **Information Security (*Informationssicherheit*)**. We covered key regulatory and compliance frameworks (DSGVO, BDSG, ISO 27001, BSI IT-Grundschutz, GeschGehG), security mechanisms (CIA Triad, TOMs), and introduced **Git** as a version control system.

**🇩🇪** Heute haben wir die wesentlichen Unterschiede zwischen **Datenschutz**, **Datensicherheit** und **Informationssicherheit** herausgearbeitet. Wir haben wichtige gesetzliche und organisatorische Rahmenwerke (DSGVO, BDSG, ISO 27001, BSI IT-Grundschutz, GeschGehG), Schutzziele (CIA-Triade, TOM) sowie die Grundlagen der Versionsverwaltung mit **Git** behandelt.

---

## Key Topics — Hauptthemen

### 1. The Core Comparison — Datenschutz vs. Datensicherheit vs. Informationssicherheit

**🇬🇧** A classic IHK exam topic: distinguishing what each domain protects and why:
**🇩🇪** Ein klassisches IHK-Prüfungsthema: Was schützt welcher Bereich und warum?

| Domain / Bereich | Core Focus / Schutzgegenstand | Primary Goal / Hauptziel | Key Laws & Standards / Normen |
|---|---|---|---|
| **Datenschutz (Data Protection)** | Personal Data (*Personenbezogene Daten*) / Schutz natürlicher Personen | Protecting individual privacy and fundamental rights / Schutz der Privatsphäre | **DSGVO (GDPR)**, **BDSG** |
| **Datensicherheit (Data Security)** | Data of any kind (digital & physical) / Daten jeglicher Art | Protecting data from loss, destruction, tampering, or theft / Schutz vor Verlust und Manipulation | Backup strategies, Encryption, Access Control |
| **Informationssicherheit (InfoSec)** | All information assets, processes, and IT systems / Alle Informationen und IT-Systeme | Ensuring organizational resilience and operational continuity / Aufrechterhaltung des Geschäftsbetriebs | **ISO/IEC 27001**, **BSI IT-Grundschutz**, **ISMS** |
| **Informationsschutz (GeschGehG)** | Confidential business secrets / Betriebs- und Geschäftsgeheimnisse | Protecting economic competitive advantage against unauthorized acquisition / Schutz wirtschaftlicher Wettbewerbsvorteile | **GeschGehG (Trade Secrets Act)** |

---

### 2. Security Objectives & Safeguards — CIA-Triade & TOM

#### The CIA Triad (Schutzziele der Informationssicherheit)
- **Confidentiality (Vertraulichkeit):** Information is accessible only to authorized users (Encryption, Access Control, Need-to-Know).
- **Integrity (Integrität):** Information is accurate, complete, and protected against unauthorized modification (Hashing, Digital Signatures, Checksums).
- **Availability (Verfügbarkeit):** Information and services are accessible when needed (Redundancy, RAID, UPS / USV, Backups).

#### TOM — Technische und Organisatorische Maßnahmen (Art. 32 DSGVO)
- **Technical Measures (Technische Maßnahmen):** Hardware/software controls (Firewalls, 2FA, BitLocker encryption, VLANs, Anti-Malware).
- **Organizational Measures (Organisatorische Maßnahmen):** Policies and human guidelines (Security training, clean-desk policy, non-disclosure agreements / NDA, role-based access concepts).

---

### 3. Frameworks & Compliance — ISMS, ISO 27001 & BSI IT-Grundschutz

- **ISMS (Information Security Management System):** A systematic approach (policies, processes, controls) to manage company information security risks.
- **ISO/IEC 27001:** Internationally recognized certifiable standard for implementing an ISMS.
- **BSI IT-Grundschutz:** German standard by the Federal Office for Information Security offering modular security baselines (*Bausteine*) and catalogues.
- **GeschGehG:** Requires companies to prove they take "reasonable protective measures" (*angemessene Geheimhaltungsmaßnahmen*) to claim legal protection for business secrets.

---

### 4. Git Version Control Fundamentals — Versionsverwaltung mit Git

**🇬🇧** Git manages code history across three distinct local states before synchronizing with a remote repository:
**🇩🇪** Git verwaltet Code-Historien über drei lokale Zustände, bevor sie mit einem Remote-Repository synchronisiert werden:

```
[Working Directory]  ──( git add )──>  [Staging Area / Index]  ──( git commit )──>  [Local Repository]  ──( git push )──>  [Remote (GitHub)]
```

| Command / Befehl | Purpose / Zweck |
|---|---|
| `git init` / `git clone` | Initialize new local repository or clone remote / Repository initialisieren oder klonen |
| `git add <file>` / `git add .` | Stage modified files for commit / Dateien für den Commit vormerken |
| `git commit -m "msg"` | Save staged snapshot permanently in local history / Snapshot lokal dauerhaft speichern |
| `git push origin <branch>` | Upload local commits to remote server (GitHub) / Lokale Commits auf GitHub hochladen |
| `git pull` | Fetch and merge changes from remote repository / Änderungen vom Remote abrufen und einpflegen |
| `git branch` / `git checkout -b` | Create and switch isolated development branches / Entwicklungszweige verwalten |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Datenschutz protects people; Datensicherheit protects data:** You can have data security without data protection (e.g. securely encrypting illegally harvested personal data), but you cannot have data protection without data security.
- **GeschGehG requires documented proof:** Under the trade secrets act, secrets are only legally protected if the company can actively prove it implemented technical and organizational measures (TOM).
- **Git makes development non-destructive:** Branching and atomic commits allow developers to experiment freely, knowing any state can be recovered.

**🇩🇪**
- **Datenschutz schützt Menschen; Datensicherheit schützt Daten:** Man kann Datensicherheit ohne Datenschutz haben (z. B. sichere Verschlüsselung illegal erhobener Daten), aber niemals Datenschutz ohne Datensicherheit.
- **GeschGehG erfordert Dokumentationsnachweis:** Betriebsgeheimnisse sind nur geschützt, wenn das Unternehmen angemessene technische und organisatorische Schutzmaßnahmen (TOM) nachweisen kann.
- **Git macht Entwicklung zerstörungsfrei:** Branching und atomare Commits ermöglichen risikofreies Experimentieren, da jeder Systemzustand reproduzierbar bleibt.
