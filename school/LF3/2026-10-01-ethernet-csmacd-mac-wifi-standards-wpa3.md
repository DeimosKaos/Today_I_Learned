---
date: 2026-10-01
category: Networking & Wireless Systems
tags: [ethernet, csmacd, mac-address, switched-ethernet, ieee-80211, wifi-standards, wireless-site-survey, wpa3, LF3]
source: school
lernfeld: LF3
---

# Ethernet CSMA/CD, Switched MAC Networks, IEEE 802.11 Wi-Fi Standards & Wireless Planning
*Date: 01-10-2026* | *Category: #networking #ethernet #wireless #wifi-standards #network-security*

---

## Context — Kontext

**🇬🇧** Today at school (**Lernfeld 3.1**), we covered local data link networks: the classic **CSMA/CD** shared media protocol vs. modern **Switched Ethernet**, the anatomy of **48-bit MAC addresses**, **IEEE 802.11 Wi-Fi generation standards**, wireless site surveys (*WLAN-Ausleuchtung*), and enterprise wireless security (**WPA2/WPA3 & 802.1X**).

**🇩🇪** Heute haben wir im Unterricht (**Lernfeld 3.1**) lokale Netze auf Schicht 2 behandelt: das klassische **CSMA/CD**-Zugriffsverfahren im Vergleich zu **Switched Ethernet**, den Aufbau von **48-Bit-MAC-Adressen**, **IEEE 802.11 WLAN-Standards**, Funk-Ausleuchtungs- und Kapazitätsplanung sowie WLAN-Sicherheitsverfahren (**WPA2/WPA3 & 802.1X**).

---

## Key Topics — Hauptthemen

### 1. CSMA/CD & Switched Ethernet — Zugriffsverfahren

**CSMA/CD (Carrier Sense Multiple Access with Collision Detection):**
- **Carrier Sense:** Listen before transmit (is the line free?).
- **Multiple Access:** Multiple nodes share the exact same physical wire.
- **Collision Detection:** If two nodes transmit simultaneously, an electrical collision occurs $\rightarrow$ a **Jam Signal** is broadcasted $\rightarrow$ each node waits a randomized exponential backoff time before retrying.
- **Legacy vs. Modern:** Obsolete in modern networks because **Switched Full-Duplex Ethernet** gives every device its own dedicated collision-free channel.

---

### 2. MAC Address Structure (Layer 2) — MAC-Adressaufbau

**🇬🇧** A 48-bit (6-byte) unique hardware identifier burnt into network interface cards (NICs):
**🇩🇪** Eine 48-Bit (6 Byte) weltweit eindeutige Hardware-Adresse der Netzwerkkarte:

```
[ 24 Bits: OUI (Organizationally Unique Identifier) ]  ───  [ 24 Bits: NIC Specific Serial Identifier ]
                  (e.g. 00:1A:2B - Intel)                                (e.g. 3C:4D:5E)
```

---

### 3. IEEE 802.11 Wi-Fi Generations — WLAN-Standards im Überblick

| Standard | Marketing Name | Frequency Band / Frequenzen | Max Theoretical Speed | Key Innovation |
|---|---|---|---|---|
| **802.11n** | **Wi-Fi 4** (2009) | $2.4\text{ GHz} \ / \ 5\text{ GHz}$ | up to $600\text{ Mbps}$ | Introduction of MIMO (multiple antennas). |
| **802.11ac** | **Wi-Fi 5** (2013) | $5\text{ GHz}$ | up to $3.5\text{ Gbps}$ | Multi-User MIMO (MU-MIMO), wider $80/160\text{ MHz}$ channels. |
| **802.11ax** | **Wi-Fi 6 / 6E** (2019/21) | $2.4\text{ GHz} \ / \ 5\text{ GHz} \ / \ 6\text{ GHz}$ | up to $9.6\text{ Gbps}$ | OFDMA (efficient high-density stadiums/offices). |
| **802.11be** | **Wi-Fi 7** (2024) | $2.4\text{ GHz} \ / \ 5\text{ GHz} \ / \ 6\text{ GHz}$ | up to $46\text{ Gbps}$ | 320 MHz channels, 4096-QAM, Multi-Link Operation (MLO). |

**Wireless Topologies:**
- **Ad-hoc (IBSS):** Direct device-to-device connection without an Access Point.
- **Infrastructure (BSS / ESS):** Devices communicate via centralized Access Points (AP) connected to a wired LAN backbone (*Distribution System*).

---

### 4. Wireless Planning & Security — Ausleuchtung & WLAN-Sicherheit

- **Site Survey (*WLAN-Ausleuchtung*):** Measuring signal attenuation through walls/concrete, avoiding co-channel interference (channels 1, 6, 11 on $2.4\text{ GHz}$), and planning AP density for concurrent user load.
- **WPA3 Personal:** Replaces insecure PSK with **SAE (Simultaneous Authentication of Equals)**, preventing offline dictionary brute-force attacks even with weak passwords.
- **WPA2/WPA3 Enterprise (802.1X):** Authenticates users individually via a **RADIUS** server using corporate credentials/certificates rather than a shared static Wi-Fi password.

---

## Key Takeaway — Was ich gelernt habe

**🇬🇧**
- **Switches replaced CSMA/CD collisions with memory buffering:** By storing and forwarding frames based on MAC tables, switches made collision domains a relic of the past.
- **Wi-Fi 6 is about density, not just top speed:** Technologies like OFDMA allow an AP to communicate with dozens of IoT and client devices simultaneously without packet queue stalls.

**🇩🇪**
- **Switche machten CSMA/CD-Kollisionen überflüssig:** Durch gezielte Weiterleitung anhand von MAC-Tabellen existieren in modernen Netzen keine geteilten Kollisionsdomänen mehr.
- **Wi-Fi 6 optimiert Dichte statt nur Höchstgeschwindigkeit:** OFDMA bedient viele parallele Clients gleichzeitig und verhindert Wartezeiten in ausgelasteten Unternehmensnetzen.
