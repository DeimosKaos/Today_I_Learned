---
date: 2026-07-27
category: Theory
tags: [operating-systems, windows, boot-process, security, uac, processes, virtualization, hyper-v, LF2]
source: school
lernfeld: LF2.6
---

# Windows Deep Dive: Boot Process, UAC, Processes & Virtualization
*Date: 27-07-2026* | *Category: #theory #operating-systems*

---

## Context — Kontext

**🇬🇧** Today at school, we went deeper into Windows internals — from the 7-step boot sequence (UEFI to Desktop) to process management with the Task Manager, user account security via UAC, and the relationship between a physical host and a Hyper-V virtual machine.

**🇩🇪** Heute haben wir uns tiefer mit Windows-Interna beschäftigt — vom 7-Schritt-Bootvorgang (UEFI bis Desktop) über die Prozessverwaltung im Task-Manager, die Benutzerkontensicherheit über die UAC bis hin zur Beziehung zwischen einem physischen Host und einer Hyper-V-VM.

---

## Key Topics — Hauptthemen

### 1. System Architecture & Boot Process — Systemarchitektur & Bootvorgang

**🇬🇧** The **Kernel** is the core of the OS, controlling all hardware through drivers. The Windows boot sequence follows 7 defined steps:
**🇩🇪** Der **Kernel** ist das Herzstück des Betriebssystems und steuert die Hardware über Treiber. Der Windows-Bootvorgang folgt 7 klar definierten Schritten:

| Step / Schritt | Phase | Description / Beschreibung |
|---|---|---|
| 1 | **Power On / Einschalten** | Hardware initialized / Hardware initialisiert |
| 2 | **UEFI / POST** | Firmware self-test, hardware check / Firmware-Selbsttest, Hardwareprüfung |
| 3 | **Secure Boot + TPM 2.0** | Signature verification of bootloader / Signaturprüfung des Bootloaders |
| 4 | **Windows Boot Manager** | Selects OS to load / Wählt das zu ladende Betriebssystem |
| 5 | **Windows Loader (winload.exe)** | Loads Kernel and core drivers / Lädt Kernel und Kerntreiber |
| 6 | **Kernel Initialization** | HAL loaded, services started / HAL geladen, Dienste gestartet |
| 7 | **Desktop / Logon** | User session created, Desktop displayed / Benutzersitzung erstellt, Desktop angezeigt |

> 🔒 **🇬🇧** TPM 2.0 (Trusted Platform Module) stores cryptographic keys to verify system integrity at boot — required for Windows 11.
> 🔒 **🇩🇪** TPM 2.0 speichert kryptografische Schlüssel zur Überprüfung der Systemintegrität beim Start — Voraussetzung für Windows 11.

---

### 2. Users & Security — Benutzer & Sicherheit (UAC)

**🇬🇧** Windows enforces a strict separation between **Standard Users** and **Administrators**, implementing the principle of least privilege through the **UAC (User Account Control / Benutzerkontensteuerung)**:
**🇩🇪** Windows erzwingt eine strikte Trennung zwischen **Standardbenutzern** und **Administratoren** und setzt das Prinzip der geringsten Rechte über die **UAC (Benutzerkontensteuerung)** durch:

| Account Type / Kontotyp | Rights / Rechte |
|---|---|
| **Standard User / Standardbenutzer** | Day-to-day tasks, no system changes / Alltägliche Aufgaben, keine Systemänderungen |
| **Administrator** | Full system access / Vollständiger Systemzugriff — only when needed / nur bei Bedarf |

- **🇬🇧** **UAC mechanism:** When an application requires elevated privileges, Windows interrupts execution and prompts the user for explicit approval — even for admins. This limits the blast radius of malware.
- **🇩🇪** **UAC-Mechanismus:** Wenn eine Anwendung erhöhte Rechte benötigt, unterbricht Windows die Ausführung und fordert die explizite Zustimmung des Benutzers — auch bei Administratoren. Dies begrenzt den Schaden durch Schadsoftware.

---

### 3. Processes & Task Manager — Prozesse & Task-Manager

- **🇬🇧** When an application is launched, it becomes a **Process** — an active instance with a unique temporary **PID (Process ID)**. A process can spawn multiple **Threads** (parallel workstreams within the same process).
- **🇩🇪** Wenn eine Anwendung gestartet wird, wird sie zu einem **Prozess** — einer aktiven Instanz mit einer eindeutigen temporären **PID (Prozess-ID)**. Ein Prozess kann mehrere **Threads** (parallele Arbeitsstränge innerhalb desselben Prozesses) erzeugen.

| Task Manager Tab / Reiter | What it shows / Was es zeigt |
|---|---|
| **Processes / Prozesse** | All running apps and background processes with CPU/RAM usage |
| **Performance / Leistung** | Real-time graphs for CPU, RAM, Disk, Network |
| **Services / Dienste** | System-level background services (start, stop, restart) |
| **Details** | Full process list with PID, status, and user |

---

### 4. Virtualization & Navigation — Virtualisierung & Bedienung

- **🇬🇧** **Host vs. VM:** The **Host PC** is the physical machine running Hyper-V. A **Virtual Machine (VM)** is a software-isolated environment running its own OS on top of the host, sharing its hardware resources.
- **🇩🇪** **Host vs. VM:** Der **Host-PC** ist die physische Maschine, auf der Hyper-V läuft. Eine **Virtuelle Maschine (VM)** ist eine softwareisolierte Umgebung, die ihr eigenes Betriebssystem auf dem Host betreibt und dessen Hardwareressourcen teilt.
- **🇬🇧** Reviewed Windows UI fundamentals: keyboard shortcuts (`Win+E`, `Alt+F4`, `Ctrl+Shift+Esc`) and file path conventions (`C:\Users\Username\Documents\`).
- **🇩🇪** Wiederholung der Windows-UI-Grundlagen: Tastenkombinationen (`Win+E`, `Alt+F4`, `Ctrl+Shift+Esc`) und Dateipfad-Konventionen (`C:\Benutzer\Benutzername\Dokumente\`).

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Boot = a chain of trust:** Each step in the 7-step boot process verifies the next. TPM + Secure Boot ensure that tampering at any layer is detected before the OS loads.
- **UAC is a speed bump, not a wall:** It forces a conscious decision for privileged actions — reducing accidental or malware-triggered system changes without eliminating admin capabilities.
- **PID is temporary:** Every process gets a fresh PID each time it starts — useful to know when scripting or diagnosing stuck processes.

**🇩🇪**
- **Boot = eine Vertrauenskette:** Jeder Schritt im 7-Schritt-Bootvorgang verifiziert den nächsten. TPM + Secure Boot stellen sicher, dass Manipulationen erkannt werden, bevor das OS geladen wird.
- **UAC ist eine Geschwindigkeitsbremse, keine Mauer:** Sie erzwingt eine bewusste Entscheidung für privilegierte Aktionen — reduziert versehentliche oder durch Malware ausgelöste Systemänderungen.
- **PID ist temporär:** Jeder Prozess erhält bei jedem Start eine neue PID — wichtig beim Scripting oder bei der Diagnose hängender Prozesse.
