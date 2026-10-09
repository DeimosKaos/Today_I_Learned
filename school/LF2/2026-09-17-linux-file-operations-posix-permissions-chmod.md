---
date: 2026-09-17
category: Linux Systems & Administration
tags: [linux-filesystem, posix-permissions, chmod, chown, file-management, bash, nano, LF2]
source: school
lernfeld: LF2
---

# Linux File Operations & POSIX Permission Architecture (chmod & chown)
*Date: 17-09-2026* | *Category: #linux #file-permissions #system-security #sysadmin*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.7**), we mastered Linux file system operations (creation, editing, copying, moving, deletion) and conducted an extensive practical session on the **POSIX permission security model** (User-Group-Others, read/write/execute flags, octal calculation, `chmod`, and `chown`).

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.7**) Dateioperationen (Erstellen, Bearbeiten, Kopieren, Verschieben, Löschen) und das **POSIX-Rechtemodell** (User-Group-Others, rwx-Flags, Oktalberechnung, `chmod` und `chown`) vertieft.

---

## Key Topics — Hauptthemen

### 1. File & Directory Management — Datei- und Verzeichnisoperationen

| Command / Befehl | Syntax Example | Function / Wirkung |
|---|---|---|
| `mkdir` | `mkdir -p /srv/data/reports` | Creates directory (with `-p` to build nested parent directories). |
| `rmdir` / `rm` | `rm -rf /tmp/old_build/` | Removes empty directory (`rmdir`) or recursively deletes files and folders (`rm -r`). |
| `cp` | `cp -r src/ dst/`, `cp -a` | Copies files or directories (with `-a` preserving attributes/timestamps). |
| `mv` | `mv file.txt /var/data/`, `mv old.md new.md` | Moves or renames files and directories. |
| `nano` / `vim` | `nano /etc/hosts` | Terminal-based text editor for interactive configuration edits. |

---

### 2. POSIX Permission Architecture — Das Linux-Rechtemodell

**🇬🇧** Every file and directory in Linux has an owner (**User / `u`**), a primary group (**Group / `g`**), and a rule for everyone else (**Others / `o`**):
**🇩🇪** Jede Datei und jedes Verzeichnis besitzt einen Besitzer (**User / `u`**), eine Gruppe (**Group / `g`**) und Rechte für den Rest der Welt (**Others / `o`**):

```
- r w x  r - x  r - -    (10 characters: File Type + User + Group + Others)
┬ ─────  ─────  ─────
│   │      │      │
│   │      │      └──── Others (r-- = 4 = Read only)
│   │      └─────────── Group  (r-x = 5 = Read + Execute)
│   └────────────────── User   (rwx = 7 = Full Control)
└────────────────────── Type: '-' (Regular File) | 'd' (Directory) | 'l' (Symlink)
```

**Permission Values & Octal Calculation / Oktale Werte:**

| Permission | Symbol | Binary Value | Octal Weight | Meaning on Files | Meaning on Directories |
|---|---|---|---|---|---|
| **Read (Lesen)** | `r` | `100` | **4** | View file contents (`cat`) | List directory contents (`ls`) |
| **Write (Schreiben)** | `w` | `010` | **2** | Modify/overwrite file | Create, rename, or delete files inside |
| **Execute (Ausführen)** | `x` | `001` | **1** | Run as a program/script | Enter directory (`cd`) and access metadata |

**Calculation Examples:**
- `rwxr-xr-x` $= (4+2+1) \ (4+0+1) \ (4+0+1) = \mathbf{755}$ (Standard for executable scripts and directories).
- `rw-r--r--` $= (4+2+0) \ (4+0+0) \ (4+0+0) = \mathbf{644}$ (Standard for public configuration/documents).
- `rw-------` $= (4+2+0) \ (0+0+0) \ (0+0+0) = \mathbf{600}$ (Standard for private SSH keys and sensitive credentials).

---

### 3. Modifying Permissions & Ownership — `chmod` & `chown`

```bash
# Octal permission assignment
chmod 755 /usr/local/bin/backup_script.sh

# Symbolic permission modification (+/-)
chmod u+x,g-w,o-r secret_report.txt

# Changing owner and group recursively
sudo chown -R www-data:www-data /var/www/html/
```

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Execute flag on directories means traversal:** Without the `x` bit on a directory, a user cannot `cd` into it, even if they have read (`r`) permission.
- **Octal math makes permission audits fast:** Grouping permissions into 3 digits ($755$, $644$, $700$) enables unambiguous security validation across thousands of server files.

**🇩🇪**
- **Das Execute-Bit auf Ordnern steuert den Zutritt:** Ohne das `x`-Bit kann ein Benutzer nicht per `cd` in ein Verzeichnis wechseln, selbst wenn Leserechte (`r`) bestehen.
- **Oktal-Notation ermöglicht schnelle Sicherheitsaudits:** Die kompakte 3-Ziffern-Schreibweise ($755$, $644$, $700$) erleichtert die eindeutige Prüfung von Zugriffsberechtigungen im Betrieb.
