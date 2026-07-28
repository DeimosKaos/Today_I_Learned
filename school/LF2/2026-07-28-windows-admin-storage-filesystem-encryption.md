---
date: 2026-07-28
category: Theory
tags: [operating-systems, windows, storage, filesystem, encryption, bitlocker, ntfs, software-install, LF2]
source: school
lernfeld: LF2
---

# Windows Administration: Tools, Software, Storage & File Systems
*Date: 28-07-2026* | *Category: #theory #operating-systems*

---

## Context — Kontext

**🇬🇧** Today at school, we explored the Windows administration layer in depth: management consoles, software installation mechanics, storage partitioning, and file system security through encryption.

**🇩🇪** Heute haben wir die Windows-Administrations-Schicht tiefgehend untersucht: Verwaltungskonsolen, Software-Installationsmechanismen, Speicherpartitionierung und Dateisystemsicherheit durch Verschlüsselung.

---

## Key Topics — Hauptthemen

### 1. Windows Management Tools — Verwaltungswerkzeuge

**🇬🇧** Windows provides three distinct management layers, each with a different scope and target audience:
**🇩🇪** Windows bietet drei verschiedene Verwaltungsschichten mit jeweils unterschiedlichem Umfang und Zielpublikum:

| Tool | Format | Use Case / Einsatz |
|---|---|---|
| **MSC Consoles** (e.g. Computer Management) | `.msc` | Advanced administration: disk management, event log, services, device manager / Erweiterte Administration |
| **Control Panel / Systemsteuerung** | `.cpl` | Classic system settings / Klassische Systemeinstellungen |
| **Settings App / Einstellungen** | Modern UI | Modern user-facing configuration / Moderne Benutzereinstellungen |

- **🇬🇧** Notifications can be controlled via **Focus Mode / Fokus-Modus** to reduce distractions during work. The Windows interface is highly personalizable (themes, taskbar, shortcuts).
- **🇩🇪** Benachrichtigungen lassen sich über den **Fokus-Modus** gezielt steuern, um Ablenkungen während der Arbeit zu minimieren. Die Windows-Oberfläche ist stark personalisierbar (Designs, Taskleiste, Verknüpfungen).

---

### 2. Software Installation — Software-Installation

**🇬🇧** Installing software is not just copying files — it deeply modifies the system by writing to the **Registry**, registering services, and creating file associations.
**🇩🇪** Software zu installieren ist nicht nur das Kopieren von Dateien — sie verändert das System tiefgreifend durch Schreiben in die **Registry**, Registrieren von Diensten und Erstellen von Dateizuordnungen.

| Format | Description / Beschreibung | Use Case / Einsatz |
|---|---|---|
| **EXE** | Traditional installer / Klassischer Installer | Standard user installations / Standard-Benutzerinstallationen |
| **MSI** | Windows Installer package / Windows Installer-Paket | Silent / unattended installs, enterprise deployment / Unbeaufsichtigte Installationen |
| **MSIX** | Modern sandboxed format / Modernes Sandbox-Format | Microsoft Store, clean uninstall / Saubere Deinstallation |
| **Portable App** | No installer needed / Kein Installer nötig | No setup, but may still leave Registry traces / Kann trotzdem Registry-Spuren hinterlassen |

> 💡 **🇬🇧** MSI packages are preferred for enterprise environments because they support **silent installations** (`/quiet` flag) and central deployment via Group Policy.
> 💡 **🇩🇪** MSI-Pakete werden in Unternehmensumgebungen bevorzugt, da sie **unbeaufsichtigte Installationen** (`/quiet`-Flag) und zentrale Bereitstellung über Gruppenrichtlinien unterstützen.

---

### 3. Storage Management — Speicherverwaltung

**🇬🇧** Storage is organized in three logical layers: **Disk → Partition → Volume**.
**🇩🇪** Speicher ist in drei logische Ebenen unterteilt: **Datenträger → Partition → Volume**.

| Partition Style / Partitionsstil | Max Disk Size / Max. Datenträgergröße | Max Partitions / Max. Partitionen | Notes / Hinweise |
|---|---|---|---|
| **MBR** (legacy) | 2 TB | 4 primary | BIOS systems / BIOS-Systeme |
| **GPT** (modern) | >2 TB | 127 | Required for UEFI & Windows 11 / Erforderlich für UEFI & Windows 11 |

---

### 4. File Systems & Encryption — Dateisysteme & Verschlüsselung

| File System / Dateisystem | Best For / Einsatz | Key Features / Merkmale |
|---|---|---|
| **NTFS** | Windows system drives / Windows-Systemlaufwerke | Permissions, journaling, large files / Rechteverwaltung, Journaling, große Dateien |
| **FAT32** | USB drives, older devices / USB-Sticks, ältere Geräte | Max 4 GB per file / Max. 4 GB pro Datei, high compatibility / hohe Kompatibilität |
| **exFAT** | Large USB drives, SD cards / Große USB-Sticks, SD-Karten | No 4 GB limit, cross-platform / Kein 4-GB-Limit, plattformübergreifend |

**Encryption / Verschlüsselung:**

| Tool | Scope / Bereich | How It Works / Funktionsweise |
|---|---|---|
| **EFS** (Encrypting File System) | Individual files & folders / Einzelne Dateien & Ordner | Transparent NTFS-level encryption tied to user account / Transparente NTFS-Verschlüsselung, an Benutzerkonto gebunden |
| **BitLocker** | Full volumes / Komplette Volumes | Full-disk encryption using TPM 2.0 / Gesamtfestplattenverschlüsselung mit TPM 2.0 |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Three layers of storage, three layers of abstraction:** Disk → Partition → Volume mirrors the OS abstraction principle — each layer hides complexity from the one above it.
- **GPT is not optional anymore:** Windows 11 requires UEFI + GPT — understanding why (MBR's 2 TB and 4-partition limit) makes the requirement logical, not arbitrary.
- **EFS vs BitLocker = file lock vs vault door:** EFS protects specific files if you know what to protect. BitLocker protects everything — including what you forgot about.

**🇩🇪**
- **Drei Speicherebenen, drei Abstraktionsebenen:** Datenträger → Partition → Volume spiegelt das OS-Abstraktionsprinzip wider — jede Ebene verbirgt Komplexität vor der darüberliegenden.
- **GPT ist nicht mehr optional:** Windows 11 erfordert UEFI + GPT — das Verständnis des Grundes (MBR-Limit: 2 TB und 4 Partitionen) macht die Anforderung logisch, nicht willkürlich.
- **EFS vs BitLocker = Dateischloss vs Tresortür:** EFS schützt bestimmte Dateien, wenn man weiß, was zu schützen ist. BitLocker schützt alles — auch das, was man vergessen hat.
