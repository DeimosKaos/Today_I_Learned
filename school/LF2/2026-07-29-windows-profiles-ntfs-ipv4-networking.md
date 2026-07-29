---
date: 2026-07-29
category: Theory
tags: [operating-systems, windows, ntfs, networking, ipv4, dhcp, dns, user-management, LF2]
source: school
lernfeld: LF2
---

# Windows User Profiles, NTFS Permissions & IPv4 Networking
*Date: 29-07-2026* | *Category: #theory #operating-systems #networking*

---

## Context — Kontext

**🇬🇧** Today at school, we covered two major areas: Windows user and profile management (with NTFS permissions) and networking fundamentals (IPv4, DHCP, DNS, Switch vs Router) — all classic IHK exam topics.

**🇩🇪** Heute haben wir zwei große Bereiche behandelt: Windows-Benutzer- und Profilverwaltung (mit NTFS-Berechtigungen) und Netzwerkgrundlagen (IPv4, DHCP, DNS, Switch vs. Router) — alles klassische IHK-Prüfungsthemen.

---

## Key Topics — Hauptthemen

### 1. User Accounts vs. User Profiles — Benutzerkonten vs. Benutzerprofile

**🇬🇧** Key distinction: the **account** is the identity (credentials, permissions), while the **profile** is the personal workspace stored on disk.
**🇩🇪** Wichtige Unterscheidung: Das **Konto** ist die Identität (Anmeldedaten, Berechtigungen), während das **Profil** der auf der Festplatte gespeicherte persönliche Arbeitsbereich ist.

**Profile folder structure / Profilordner-Struktur (`C:\Users\Username\`):**

| Folder / Ordner | Visibility / Sichtbarkeit | Content / Inhalt |
|---|---|---|
| `Desktop`, `Documents`, `Downloads` | Visible / Sichtbar | User files / Benutzerdateien |
| `AppData\Roaming` | Hidden / Versteckt | App settings synced across devices / App-Einstellungen, geräteübergreifend synchronisiert |
| `AppData\Local` | Hidden / Versteckt | App data local only / App-Daten nur lokal |
| `AppData\LocalLow` | Hidden / Versteckt | Low-privilege app data (e.g. browser sandbox) / Daten mit niedrigen Rechten |
| `NTUSER.DAT` | Hidden / Versteckt | User-specific Registry hive / Benutzerspezifischer Registry-Zweig |

**Environment Variables / Umgebungsvariablen:**

| Variable | Resolves to / Wird aufgelöst zu |
|---|---|
| `%USERPROFILE%` | `C:\Users\Username` |
| `%APPDATA%` | `C:\Users\Username\AppData\Roaming` |
| `%PUBLIC%` | `C:\Users\Public` (shared between all users / für alle Benutzer) |

---

### 2. NTFS Permissions & Inheritance — NTFS-Berechtigungen & Vererbung

**🇬🇧** NTFS permissions control who can do what with files and folders. Permissions are **inherited** from parent folders by default — a key concept for designing secure folder structures.
**🇩🇪** NTFS-Berechtigungen steuern, wer was mit Dateien und Ordnern tun darf. Berechtigungen werden standardmäßig von übergeordneten Ordnern **vererbt** — ein Schlüsselkonzept für sichere Ordnerstrukturen.

| Permission / Berechtigung | Read / Lesen | Write / Schreiben | Modify / Ändern | Delete / Löschen | Full Control / Vollzugriff |
|---|---|---|---|---|---|
| **Read / Lesen** | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Write / Schreiben** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Modify / Ändern** | ✅ | ✅ | ✅ | ✅ | ❌ |
| **Full Control / Vollzugriff** | ✅ | ✅ | ✅ | ✅ | ✅ |

---

### 3. Application Management: Microsoft Edge

- **🇬🇧** **Browser Profiles:** Separate work and personal data within the same browser — each profile has its own bookmarks, cookies, and extensions.
- **🇩🇪** **Browser-Profile:** Trennung von beruflichen und privaten Daten im selben Browser — jedes Profil hat eigene Lesezeichen, Cookies und Erweiterungen.
- **🇬🇧** **InPrivate Mode:** Sessions leave no local traces (no history, cookies deleted on close). Settings synced via Microsoft account. Tracking protection configurable per site.
- **🇩🇪** **InPrivate-Modus:** Sitzungen hinterlassen keine lokalen Spuren (kein Verlauf, Cookies beim Schließen gelöscht). Einstellungen über Microsoft-Konto synchronisierbar. Tracking-Schutz pro Website konfigurierbar.

---

### 4. Network Topology — Netzwerktopologie

| Component / Komponente | Function / Funktion |
|---|---|
| **Switch** | Connects devices **within** the same local network (LAN) / Verbindet Geräte **innerhalb** desselben lokalen Netzwerks |
| **Router** | Connects **different** networks (e.g. LAN → Internet) / Verbindet **verschiedene** Netzwerke (z. B. LAN → Internet) |
| **Client** | Requests services (browser, app) / Fordert Dienste an |
| **Server** | Provides services (web, file, email) / Stellt Dienste bereit |

---

### 5. IPv4 Configuration — IPv4-Konfiguration *(Classic IHK Exam Topic)*

**🇬🇧** An IPv4 address (32-bit) is split into a **network part** and a **host part**, defined by the subnet mask.
**🇩🇪** Eine IPv4-Adresse (32-Bit) wird in einen **Netzanteil** und einen **Geräteanteil** aufgeteilt, definiert durch die Subnetzmaske.

```
Example / Beispiel:
IP Address / IP-Adresse:  192.168.1.42
Subnet Mask / Subnetzmaske: 255.255.255.0  →  Network: 192.168.1.0  |  Host: .42
Default Gateway:           192.168.1.1   →  "Exit door" to other networks / "Ausgang" zu anderen Netzwerken
```

| Concept / Konzept | Description / Beschreibung |
|---|---|
| **Static IP / Statische IP** | Manually configured, always the same / Manuell konfiguriert, immer gleich |
| **DHCP** | Server automatically assigns IP, mask, gateway, DNS / Server weist automatisch IP, Maske, Gateway, DNS zu |
| **DNS** | Translates domain names to IPs (e.g. `google.com` → `142.250.x.x`) / Übersetzt Domainnamen in IPs |

**CLI Diagnostics / CLI-Netzwerkdiagnose:**

| Command / Befehl | Output / Ausgabe |
|---|---|
| `ipconfig /all` | Full IP config (MAC, IP, subnet, gateway, DNS) / Vollständige IP-Konfiguration |
| `ncpa.cpl` | Opens Network Connections window directly / Öffnet Netzwerkverbindungen direkt |

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Account ≠ Profile:** Deleting an account does not automatically delete its profile folder — understanding this prevents accidental data loss in enterprise environments.
- **NTFS inheritance = policy at scale:** Setting permissions on a parent folder automatically propagates to all child folders — one rule governs thousands of files.
- **Subnet mask = the boundary line:** It defines what is "local" (reachable via Switch) vs. what is "remote" (requires the Router/Gateway). This is the foundation of all network troubleshooting.

**🇩🇪**
- **Konto ≠ Profil:** Das Löschen eines Kontos löscht nicht automatisch seinen Profilordner — dieses Verständnis verhindert versehentlichen Datenverlust in Unternehmensumgebungen.
- **NTFS-Vererbung = Richtlinie im großen Maßstab:** Das Setzen von Berechtigungen für einen übergeordneten Ordner wird automatisch auf alle untergeordneten Ordner übertragen — eine Regel gilt für Tausende von Dateien.
- **Subnetzmaske = die Grenzlinie:** Sie definiert, was „lokal" ist (über Switch erreichbar) und was „remote" ist (erfordert Router/Gateway). Dies ist die Grundlage jeder Netzwerkdiagnose.
