---
date: 2026-09-15
category: Linux Systems & Administration
tags: [linux-installation, virtual-machine, hyper-v, partitioning, filesystem-hierarchy, swap, system-setup, LF2]
source: school
lernfeld: LF2
---

# Linux Virtual Machine Deployment: Hypervisor Setup, Partitioning & Base Configuration
*Date: 15-09-2026* | *Category: #linux #virtualization #system-administration*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 2.7**), we deployed a dedicated Linux distribution inside a Virtual Machine on **Hyper-V**. We walked through virtual hardware provisioning, storage partitioning schemes, base system installation, user environment initialization, and technical system documentation.

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 2.7**) eine Linux-Distribution als virtuelle Maschine auf **Hyper-V** bereitgestellt. Wir haben die Hardware-Zuweisung, Partitionierungsstrategien, die Basissystem-Installation, die Benutzerkonfiguration sowie die technische Setup-Dokumentation durchgeführt.

---

## Key Topics — Hauptthemen

### 1. VM Provisioning & Hardware Allocation — VM-Bereitstellung

| Virtual Resource / Ressource | Recommended Baseline / Richtwert | Technical Rationale |
|---|---|---|
| **Hyper-V Generation** | Generation 2 (UEFI) | Supports modern GPT partitioning and secure boot options. |
| **vCPU (Prozessorkerne)** | 2 Cores | Sufficient parallel execution for build tools and system daemons. |
| **RAM (Arbeitsspeicher)** | 4 GB (Dynamic Memory enabled) | Balances host resource usage with smooth multitasking. |
| **Virtual Disk (VHDX)** | 30–50 GB (Dynamically Expanding) | Ample room for root filesystem, packages, and development libraries. |
| **Virtual Switch** | Default Switch / Bridged Network | Provides NAT internet access and host-to-guest networking. |

---

### 2. Linux Storage Partitioning Schemes — Partitionierungsstrategien

**🇬🇧** A clean partition layout isolates system binaries from user data and logs to prevent disk space exhaustion from crashing the OS:
**🇩🇪** Eine saubere Partitionierung trennt Systemdaten von Benutzerdaten, um Systemausfälle durch volle Festplatten zu verhindern:

```
[ /boot (EFI / GRUB Bootloader) ] ──► [ / (Root Filesystem - ext4 / xfs) ] ──► [ /home (User Profiles) ] ──► [ swap (Virtual Memory Overflow) ]
```

| Mount Point / Einhängepunkt | Filesystem | Recommended Size | Purpose / Funktion |
|---|---|---|---|
| `/boot/efi` | FAT32 | $512\text{ MB}$ | UEFI bootloader (GRUB) binaries. |
| `/` (Root) | ext4 / xfs | $20\text{–}30\text{ GB}$ | Core operating system binaries, libraries, and `/var` logs. |
| `/home` | ext4 / xfs | Remaining space | User documents, configuration dotfiles, and workspace data. |
| `swap` | swap space | $2\text{–}4\text{ GB}$ | Emergency overflow when physical RAM is exhausted; hibernation support. |

---

### 3. Post-Installation Configuration & Documentation — Basiskonfiguration

1. **User Privileges:** Created a standard non-root user and added it to the `sudo` group (`usermod -aG sudo <username>`).
2. **Localization & Clock:** Configured system timezone to `Europe/Berlin` (`timedatectl set-timezone Europe/Berlin`) and generated UTF-8 locales.
3. **Repository Refresh:** Updated package lists and core utilities (`sudo apt update && sudo apt upgrade -y`).
4. **Setup Documentation:** Documented MAC address, assigned IP, hostname, and partition UUIDs in an internal deployment logbook.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Separation of `/home` and `/` enables easy upgrades:** If the OS needs to be reinstalled or replaced, user data in `/home` remains untouched on its dedicated partition.
- **Generation 2 VMs are the standard:** Deploying Linux with UEFI and synthetic network adapters delivers superior I/O throughput compared to legacy Gen 1 emulated hardware.

**🇩🇪**
- **Trennung von `/home` und `/` sichert Nutzerdaten:** Bei einer Neuinstallation des Betriebssystems bleibt das Benutzerverzeichnis `/home` auf seiner eigenen Partition unberührt.
- **Generation-2-VMs bieten spürbare Performance-Vorteile:** UEFI-basierte VMs mit synthetischen Netzwerktreibern erreichen deutlich höhere I/O-Geschwindigkeiten als emulierte Gen-1-Systeme.
