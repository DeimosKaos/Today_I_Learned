---
date: 2026-07-30
category: Theory
tags: [networking, windows, security, defender, smb, dns, diagnostics, malware, LF2]
source: school
lernfeld: LF2
---

# Network Diagnostics, Wireless, File Sharing & Windows 11 Security
*Date: 30-07-2026* | *Category: #theory #networking #security*

---

## Context — Kontext

**🇬🇧** Today at school, we covered network diagnostics using Windows CLI tools, wireless network management, local file sharing via SMB, and the full security and privacy stack of Windows 11 — all core IHK exam topics.

**🇩🇪** Heute haben wir Netzwerkdiagnose mit Windows-CLI-Tools, WLAN-Verwaltung, lokale Dateifreigaben über SMB und den vollständigen Sicherheits- und Datenschutz-Stack von Windows 11 behandelt — allesamt klassische IHK-Prüfungsthemen.

---

## Key Topics — Hauptthemen

### 1. Network Diagnostics — Netzwerkdiagnose (Windows CLI)

**🇬🇧** Systematic troubleshooting works **inside-out**: start at your own machine, then the gateway, then the internet.
**🇩🇪** Systematische Fehlersuche arbeitet **von innen nach außen**: beginnend am eigenen Gerät, dann am Gateway, dann ins Internet.

| Command / Befehl | Purpose / Zweck | Key Error Pattern / Typisches Fehlerbild |
|---|---|---|
| `ipconfig /all` | Check own IP config / Eigene IP-Konfiguration prüfen | `169.254.x.x` (APIPA) = DHCP failed / DHCP fehlgeschlagen |
| `ping 127.0.0.1` | Test own TCP/IP stack (loopback) / Eigenen TCP/IP-Stack testen | Failure = TCP/IP stack broken / TCP/IP-Stack defekt |
| `ping <gateway>` | Test local network / Lokales Netz testen | Failure = LAN problem / LAN-Problem |
| `ping 8.8.8.8` | Test internet connectivity / Internetverbindung testen | Failure = WAN/ISP problem / WAN/Provider-Problem |
| `ping google.com` | Test DNS resolution / DNS-Auflösung testen | Failure but `ping 8.8.8.8` works = DNS problem |
| `nslookup` | Investigate DNS resolution specifically / Gezielt DNS-Auflösung untersuchen | Failure = DNS server unreachable / DNS-Server nicht erreichbar |
| `tracert <target>` | Show all hops to destination / Alle Zwischenstationen zum Ziel anzeigen | Identifies where packets are dropped / Wo Pakete verloren gehen |

> 💡 **🇬🇧** APIPA (`169.254.x.x`) is a self-assigned fallback IP — it means the device cannot reach a DHCP server.
> 💡 **🇩🇪** APIPA (`169.254.x.x`) ist eine selbst zugewiesene Fallback-IP — sie bedeutet, dass das Gerät keinen DHCP-Server erreichen kann.

---

### 2. Wireless Networks — Drahtlose Netzwerke

| Feature / Funktion | Description / Beschreibung |
|---|---|
| **WPA2 / WPA3** | Encryption standard for WLAN / Verschlüsselungsstandard für WLAN — unencrypted networks are untrusted / unverschlüsselte Netzwerke gelten als nicht vertrauenswürdig |
| **Metered Connection / Getaktete Verbindung** | Limits automatic updates & cloud sync to save data / Schränkt automatische Updates und Cloud-Synchronisierung ein, um Datenvolumen zu sparen |
| **Mobile Hotspot / Mobiler Hotspot** | Shares an existing internet connection via WLAN with other devices / Teilt eine bestehende Internetverbindung per WLAN mit anderen Geräten |

---

### 3. Folder Sharing & Network Drives — Ordnerfreigaben & Netzlaufwerke

**🇬🇧** Local network sharing uses the **SMB (Server Message Block)** protocol — unlike cloud storage (OneDrive), both devices must be on the same network and the sharing PC must be powered on.
**🇩🇪** Die lokale Netzwerkfreigabe nutzt das **SMB (Server Message Block)**-Protokoll — anders als bei Cloud-Speicher (OneDrive) müssen beide Geräte im selben Netzwerk sein und der freigebende PC muss eingeschaltet sein.

**Prerequisites for sharing / Voraussetzungen für Freigaben:**
- Network profile set to **Private / Privat**
- Network discovery enabled / Netzwerkerkennung aktiv
- File and printer sharing enabled / Datei- und Druckerfreigabe aktiv
- Firewall allows SMB traffic / Firewall erlaubt SMB-Datenverkehr

**UNC Path format / UNC-Pfad-Format:**
```
\\ComputerName\ShareName
\\OFFICE-PC\Documents
```

**🇬🇧** UNC paths can be **mapped as a persistent drive letter** (e.g. `Z:`) via Windows Explorer for easier daily access.
**🇩🇪** UNC-Pfade können als **dauerhafter Laufwerkbuchstabe** (z. B. `Z:`) im Explorer eingebunden werden, für einfacheren täglichen Zugriff.

---

### 4. Windows 11 Security & Privacy — Sicherheit & Datenschutz

**Malware Types / Schadsoftware-Typen:**

| Type / Typ | Behaviour / Verhalten |
|---|---|
| **Virus** | Attaches to files, spreads when file is opened / Hängt sich an Dateien, verbreitet sich beim Öffnen |
| **Worm / Wurm** | Self-replicates through the network, no user action needed / Selbstreplikation über das Netzwerk, kein Benutzer-Eingriff nötig |
| **Trojan / Trojaner** | Disguised as legitimate software / Tarnt sich als legitime Software |
| **Ransomware** | Encrypts files and demands payment / Verschlüsselt Dateien und verlangt Lösegeld |

**Microsoft Defender & Windows Security / Microsoft Defender & Windows-Sicherheit:**

| Feature / Funktion | Description / Beschreibung |
|---|---|
| **Real-time Protection / Echtzeitschutz** | Continuously scans for threats / Kontinuierliche Bedrohungserkennung |
| **Manual Scan / Manueller Scan** | On-demand full or quick scan / Bedarfsgesteuerte Voll- oder Schnellprüfung |
| **Controlled Folder Access / Überwachter Ordnerzugriff** | Blocks unauthorized apps from modifying protected folders / Blockiert unbefugte Apps an geschützten Ordnern |
| **Defender Firewall** | Filters incoming and outgoing traffic by rules / Filtert ein-/ausgehenden Datenverkehr anhand von Regeln |

**Windows Update & Privacy / Windows Update & Datenschutz:**
- **🇬🇧** **Usage Hours / Nutzungszeiten:** Define when Windows avoids automatic restarts for updates (e.g. during work hours).
- **🇩🇪** **Nutzungszeiten:** Definiert, wann Windows automatische Neustarts für Updates vermeidet (z. B. während der Arbeitszeit).
- **🇬🇧** **App Permissions / App-Berechtigungen:** Fine-grained control over which apps can access Camera, Microphone, and Location.
- **🇩🇪** **App-Berechtigungen:** Detaillierte Kontrolle darüber, welche Apps auf Kamera, Mikrofon und Standort zugreifen dürfen.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Diagnose inside-out:** The `ping 127.0.0.1 → gateway → 8.8.8.8 → google.com` sequence is a universal troubleshooting methodology that isolates the problem layer by layer.
- **SMB ≠ cloud:** File sharing via SMB is powerful but requires both machines to be on and on the same network — the tradeoff vs. cloud solutions is availability vs. control.
- **Ransomware is the most dangerous threat type:** Unlike viruses or worms, it causes immediate, irreversible data loss without backups. Controlled Folder Access is specifically designed to counter it.

**🇩🇪**
- **Diagnose von innen nach außen:** Die Sequenz `ping 127.0.0.1 → Gateway → 8.8.8.8 → google.com` ist eine universelle Diagnosemethodik, die das Problem Schicht für Schicht isoliert.
- **SMB ≠ Cloud:** Dateifreigabe über SMB ist leistungsstark, erfordert aber, dass beide Geräte eingeschaltet und im selben Netzwerk sind — der Kompromiss gegenüber Cloud-Diensten ist Verfügbarkeit vs. Kontrolle.
- **Ransomware ist die gefährlichste Bedrohung:** Anders als Viren oder Würmer verursacht sie sofortigen, irreversiblen Datenverlust ohne Backups. Der überwachte Ordnerzugriff ist speziell dafür konzipiert.
