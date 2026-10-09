---
date: 2026-09-18
category: Linux Systems & Administration
tags: [linux-development, python, rust, package-management, vm-backup, snapshots, hyper-v, documentation, LF2]
source: school
lernfeld: LF2
---

# Programming on Linux (Python & Rust), VM Backup Strategies & System Documentation
*Date: 18-09-2026* | *Category: #linux #software-development #devops #system-backup*

---

## Context — Kontext

**🇬🇧** Today we concluded **Lernfeld 2.7 (Linux Systems)**. We set up modern developer toolchains under Linux, comparing **Python** (interpreted scripting and data manipulation) with **Rust** (memory-safe compiled systems programming). We also established robust virtual machine backup strategies (Hyper-V checkpoints, disk exports, tar archives) and compiled our comprehensive system documentation.

**🇩🇪** Heute haben wir **Lernfeld 2.7 (Linux-Systeme)** abgeschlossen. Wir haben Entwickler-Toolchains unter Linux eingerichtet und **Python** (Skripting und Datenverarbeitung) mit **Rust** (speichersichere kompilierte Systemprogrammierung) verglichen. Zudem haben wir Backup-Strategien für virtuelle Maschinen (Hyper-V-Prüfpunkte, VHDX-Exporte, Tar-Archive) und die Systemdokumentation erarbeitet.

---

## Key Topics — Hauptthemen

### 1. Developer Toolchains: Python vs. Rust on Linux

| Aspect / Aspekt | Python | Rust |
|---|---|---|
| **Paradigm & Execution / Typ** | Interpreted, high-level, dynamically typed. | Compiled, low-level control, statically typed. |
| **Toolchain & Package Manager** | `python3`, `pip`, `venv` (Virtual Environments). | `rustc`, `cargo` (Cargo build system and package manager). |
| **Primary Strengths** | Rapid development, data processing, automation scripting, vast library ecosystem. | Memory safety without garbage collector (Borrow Checker), extreme execution speed, zero-cost abstractions. |
| **Role in Linux Ecosystem** | System administration scripts, glue code, AI/ML pipelines. | Modern systems utilities, fast CLI tools (e.g. `ripgrep`, `bat`), kernel modules. |

---

### 2. Virtual Machine Backup Strategies — VM-Sicherung & Archivierung

**🇬🇧** Reliable server operations demand multi-layered backup strategies before updates or configuration changes:
**🇩🇪** Zuverlässiger Serverbetrieb erfordert mehrstufige Backup-Strategien vor Updates oder Systemänderungen:

| Backup Method / Methode | Layer / Ebene | Mechanism & Use Case / Einsatzbereich |
|---|---|---|
| **Hyper-V Checkpoint / Snapshot** | Hypervisor | Saves current RAM and disk state in seconds; ideal for short-term rollbacks during risky updates. *(Not a permanent backup!)* |
| **VHDX Export / Image Backup** | Hypervisor / Storage | Full export of the virtual hard disk file; enables disaster recovery to another host machine. |
| **File-Level Archive (`tar` / `rsync`)** | Guest OS | `tar -czvf backup_etc.tar.gz /etc/` compresses critical configuration directories without VM downtime. |

---

### 3. System Handover & Technical Documentation — Systemdokumentation

- **Configuration Ledger:** Recording static network parameters (IP, Subnet, DNS, Gateway), enabled firewall rules (`ufw` / `iptables`), and active systemd daemons.
- **Reproducibility:** Documenting all package installation steps and configuration file overrides so an identical Linux environment can be recreated cleanly from scratch.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Linux is the native home for modern development:** Package managers like `apt` combined with language tools (`cargo`, `pip`) make setting up reproducible development environments fast and scriptable.
- **Checkpoints are not backups:** A Hyper-V checkpoint depends on the base disk and slows I/O over time — permanent disaster recovery requires independent image or file-level exports.

**🇩🇪**
- **Linux ist die native Heimat moderner Softwareentwicklung:** Das Zusammenspiel aus Paketverwaltung (`apt`) und Sprach-Toolchains (`cargo`, `pip`) ermöglicht schnelle und reproduzierbare Setups.
- **Prüfpunkte sind keine Backups:** Hyper-V-Snapshots hängen von der Basis-VHDX ab — echte Ausfallsicherheit erfordert unabhängige Image- oder Archiv-Exporte.
