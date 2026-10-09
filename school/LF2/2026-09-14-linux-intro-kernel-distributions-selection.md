---
date: 2026-09-14
category: Linux Systems & Administration
tags: [linux, open-source, linux-distributions, kernel-userland, debian, rhel, fhs, LF2]
source: school
lernfeld: LF2
---

# Introduction to Linux Systems, Open-Source Philosophy & Distribution Selection
*Date: 14-09-2026* | *Category: #linux #operating-systems #open-source #system-administration*

---

## Context — Kontext

**🇬🇧** Today marked the start of **Lernfeld 2.7: Linux Systems**. We explored the origins, architecture, and licensing philosophy of GNU/Linux, decomposed the distinction between the Linux kernel and userland distributions, and evaluated criteria for selecting appropriate Linux distributions for enterprise and developer workstations.

**🇩🇪** Heute begann **Lernfeld 2.7: Linux-Systeme**. Wir haben die Entstehung, Architektur und Lizenzphilosophie von GNU/Linux behandelt, die Trennung zwischen Linux-Kernel und Userland-Distributionen analysiert und Auswahlkriterien für den Einsatz von Linux-Distributionen im Unternehmens- und Entwicklerumfeld erarbeitet.

---

## Key Topics — Hauptthemen

### 1. GNU/Linux Architecture & The Unix Philosophy — Linux-Grundlagen

**🇬🇧** Linux is fundamentally a monolithic, multi-user, multitasking Unix-like operating system kernel created by Linus Torvalds in 1991, combined with GNU system utilities:
**🇩🇪** Linux ist ein monolithischer, mandantenfähiger Unix-ähnlicher Betriebssystem-Kernel, der mit den GNU-Systemwerkzeugen kombiniert wird:

```
[ User Applications (CLI / GUI) ] ──► [ GNU C Library / Shell (Bash) ] ──► [ Linux Kernel (Monolithic: CPU, Memory, Drivers) ] ──► [ Physical Hardware ]
```

- **Unix Philosophy:** "Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface."

---

### 2. Linux Distribution Comparison — Distributionen im Vergleich

| Distribution Family / Familie | Package Manager / Paketverwaltung | Release Model / Release-Zyklus | Primary Use Case / Haupteinsatz |
|---|---|---|---|
| **Debian / Ubuntu / Mint** | `apt` / `dpkg` (`.deb`) | LTS (Long Term Support) & Fixed | Universal servers, developer workstations, cloud instances |
| **RHEL / Rocky Linux / Fedora** | `dnf` / `rpm` (`.rpm`) | Enterprise Lifecycle (10 yrs) | Corporate enterprise infrastructure, certified business workloads |
| **Arch Linux / Manjaro** | `pacman` | Rolling Release (bleeding-edge) | Power users, continuous software development |
| **Alpine Linux** | `apk` | Lightweight musl libc | Minimalist Docker containers, microservices |

**Selection Criteria for Enterprises:**
- Long-Term Support (LTS) lifecycle stability, commercial vendor support (e.g. Red Hat / Canonical), security patch speed, package repository ecosystem, and community backing.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Linux is a kernel, not a single operating system:** The combination of the Linux kernel with packaging systems, init daemons (`systemd`), and toolchains creates distinct distributions tailored for servers, IoT, or desktops.
- **Enterprise choice values stability over freshness:** In production environments, long-term stability and security backports (e.g. Debian/RHEL) take precedence over having the newest software versions.

**🇩🇪**
- **Linux ist ein Kernel, kein einzelnes Betriebssystem:** Erst das Zusammenspiel des Kernels mit Paketmanagern, Init-Systemen (`systemd`) und GNU-Tools ergibt eine fertige Distribution.
- **Unternehmen bevorzugen Stabilität vor Aktualität:** Im Produktivbetrieb stehen Langzeit-Support (LTS) und verlässliche Sicherheitspatches vor dem jeweils neuesten Release.
