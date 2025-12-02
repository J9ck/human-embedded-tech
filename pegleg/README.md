# 🏴‍☠️ PegLeg Implant Project

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Raspberry_Pi_Zero_W.jpg/1200px-Raspberry_Pi_Zero_W.jpg" alt="Raspberry Pi Zero W" width="400"/>
  <br/>
  <em>Raspberry Pi Zero W — The heart of the PegLeg implant</em>
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#history--background">History</a> •
  <a href="#hardware-bill-of-materials-bom">Hardware</a> •
  <a href="#software-configuration">Software</a> •
  <a href="#usage">Usage</a> •
  <a href="#safety-considerations">Safety</a> •
  <a href="#faq">FAQ</a>
</p>

---

## Overview

**PegLeg** is a groundbreaking biohacking project that involves implanting a single-board computer—typically a **Raspberry Pi Zero W**—into the human body. The device functions as a wireless, offline file-sharing node (dead drop) and local mesh network. It is powered wirelessly through the skin using a **Qi charging coil**.

<table>
<tr>
<td width="50%">

### 🎯 What It Does
- Creates a portable WiFi hotspot
- Hosts anonymous file sharing
- Enables local chat/communication
- Functions as a "digital dead drop"

</td>
<td width="50%">

### 🔑 Key Features
- **Wireless Power** via Qi charging
- **No Internet Required** — fully offline
- **Anonymous Access** — no logging
- **Mesh Capable** — can link with other nodes

</td>
</tr>
</table>

The project represents a fascinating intersection of:

| Domain | Description |
|--------|-------------|
| 🧬 **Biohacking** | Pushing the boundaries of human-machine integration |
| 📡 **Mesh Networking** | Decentralized, anonymous communication |
| 🔓 **Open Source** | Free culture and information sharing |
| 🏴‍☠️ **Pirate Radio Culture** | Inspired by guerrilla broadcasting and info-freedom movements |

> **⚠️ DISCLAIMER:** This repository is for **educational and informational purposes only**. Implanting electronic devices into the human body carries significant medical risks, including infection, rejection, and tissue damage. This is **not** medical advice. **Proceed at your own risk.**

---

## History & Background

### Timeline

```
2019 ─────────────────────────────────────────────────────────────────────────
  │
  ├─── DEF CON 27 Biohacking Village
  │    └── PegLeg publicly demonstrated
  │
  ├─── First successful implantation
  │    └── Subdermal Raspberry Pi Zero W
  │
  └─── Media coverage explodes
       └── Tom's Hardware, Geeky Gadgets, Boing Boing, etc.
```

### Origins

The PegLeg project emerged from the **biohacking community**, specifically demonstrated at **DEF CON 27's Biohacking Village** in 2019. The creators were inspired by:

- **PirateBox** — An offline communication and file-sharing system
- **Dead Drops** — USB drives embedded in public spaces for anonymous file exchange  
- **Pirate Radio** — Underground broadcasting that challenged media monopolies

The name "PegLeg" playfully references pirate culture while nodding to the project's roots in information freedom movements.

---

## Hardware Bill of Materials (BOM)

To build a standard PegLeg unit, the following components are typically used:

### Core Components

| Component | Description | Est. Cost | Notes |
|-----------|-------------|-----------|-------|
| **Raspberry Pi Zero W** | The core computer | ~$15 | Features WiFi and Bluetooth for connectivity |
| **Qi Receiver Coil** | Power receiver | ~$5-10 | Must be soldered to the Pi's 5V/GND pads or test points |
| **MicroSD Card** | Storage (8GB-64GB) | ~$8-15 | High endurance recommended; capacity depends on use case |
| **Capacitor (100-470µF)** | Power stability | ~$1 | Smooths power delivery from the Qi coil |
| **Biocompatible Coating** | Encapsulation | ~$20-50 | **Critical.** Medical-grade silicone or resin |

### Optional Enhancements

| Component | Purpose | Notes |
|-----------|---------|-------|
| **Status LED** | Visual feedback | Indicates power/activity through skin |
| **Voltage Regulator** | Power management | Provides stable 5V from Qi receiver |
| **Thermal Pad** | Heat dissipation | Helps spread heat across larger area |

### Tools Required

- Soldering iron (fine tip recommended)
- Multimeter for testing connections
- Heat shrink tubing
- Medical-grade silicone (for encapsulation)
- Vacuum chamber (optional, for bubble-free coating)

### Hardware Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          BIOCOMPATIBLE SHELL                                 │
│    ┌─────────────────────────────────────────────────────────────────────┐  │
│    │                                                                     │  │
│    │   ┌─────────────────────────────────────────────────────────────┐  │  │
│    │   │                   RASPBERRY PI ZERO W                       │  │  │
│    │   │                                                             │  │  │
│    │   │   ┌─────────────┐      ┌──────────────────────────────┐    │  │  │
│    │   │   │  MicroSD    │      │   BCM2835 + 512MB RAM        │    │  │  │
│    │   │   │  (Storage)  │      │   WiFi 802.11n + BT 4.1      │    │  │  │
│    │   │   └─────────────┘      └──────────────────────────────┘    │  │  │
│    │   │                                                             │  │  │
│    │   │   PP1 (5V) ●────────┐         ┌──● PP6 (GND)              │  │  │
│    │   │                     │         │                            │  │  │
│    │   └─────────────────────┼─────────┼────────────────────────────┘  │  │
│    │                         │         │                               │  │
│    │                    ┌────┴─────────┴────┐                          │  │
│    │                    │     CAPACITOR     │                          │  │
│    │                    │    (100-470µF)    │                          │  │
│    │                    └─────────┬─────────┘                          │  │
│    │                              │                                    │  │
│    │          ╭──────────────────┴──────────────────╮                  │  │
│    │          │         QI RECEIVER COIL            │                  │  │
│    │          │                                     │                  │  │
│    │          │            ((( ◎ )))                │                  │  │
│    │          │                                     │                  │  │
│    │          │         5V @ ~1A (typical)          │                  │  │
│    │          ╰─────────────────────────────────────╯                  │  │
│    │                                                                     │  │
│    └─────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
                                    ↑
                                    │ Wireless Power Transfer
                                    │ (Inductive Coupling)
                                    │
                      ┌─────────────┴─────────────┐
                      │      QI CHARGER PAD       │
                      │        (EXTERNAL)         │
                      │                           │
                      │   Place against skin to   │
                      │   power the implant       │
                      └───────────────────────────┘
```

### Wiring Diagram

```
                    QI RECEIVER OUTPUT
                           │
              ┌────────────┴────────────┐
              │                         │
           [+5V]                     [GND]
              │                         │
              │    ┌─────────────┐      │
              ├────┤  CAPACITOR  ├──────┤
              │    │  100-470µF  │      │
              │    └─────────────┘      │
              │                         │
              ▼                         ▼
         ┌────────────────────────────────────┐
         │         RASPBERRY PI ZERO W        │
         │                                    │
         │   PP1 ●─────────────● PP6          │
         │   (5V)               (GND)         │
         │                                    │
         │   Alternative: Use GPIO Header     │
         │   Pin 2 (5V) ── Pin 6 (GND)        │
         │                                    │
         └────────────────────────────────────┘
```

---

## Software Configuration

The software stack is usually based on **PirateBox** or a similar offline network distribution.

### Core Features

| Feature | Description | Technical Details |
|---------|-------------|-------------------|
| 📶 **WiFi Access Point** | Broadcasts an open network | SSID: `PegLeg`, No password, 802.11n |
| 🌐 **Captive Portal** | Auto-redirects users | DNS hijacking to local web server |
| 💬 **Anonymous Chat** | Local communication | Web-based or IRC, no logging |
| 📁 **File Sharing** | Upload/download files | Shared directory, anonymous access |
| 🔄 **Mesh Support** | Link multiple nodes | Can form ad-hoc networks |

### Software Stack

```
┌─────────────────────────────────────────────────────────────┐
│                      APPLICATION LAYER                       │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │  File Share │  │    Chat     │  │   Captive Portal    │  │
│  │   (droopy)  │  │  (shout.js) │  │    (landing page)   │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                       WEB SERVER                             │
│              lighttpd / nginx / python http                  │
├─────────────────────────────────────────────────────────────┤
│                      NETWORK LAYER                           │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │   hostapd   │  │   dnsmasq   │  │     iptables        │  │
│  │   (WiFi AP) │  │ (DHCP/DNS)  │  │    (routing)        │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                     OPERATING SYSTEM                         │
│              Raspberry Pi OS Lite (Debian-based)             │
└─────────────────────────────────────────────────────────────┘
```

### Installation Guide

#### Option 1: PirateBox Image (Legacy)

```bash
# Note: PirateBox project has been archived
# Download from: https://piratebox.cc/ (if available)
# Flash to MicroSD using Raspberry Pi Imager or dd
```

#### Option 2: Manual Setup (Recommended)

```bash
# ═══════════════════════════════════════════════════════════════
# STEP 1: Flash Raspberry Pi OS Lite to MicroSD
# ═══════════════════════════════════════════════════════════════
# Use Raspberry Pi Imager: https://www.raspberrypi.org/software/
# Choose "Raspberry Pi OS Lite (32-bit)"
# Enable SSH in Imager settings for headless setup

# ═══════════════════════════════════════════════════════════════
# STEP 2: Install Required Packages
# ═══════════════════════════════════════════════════════════════
sudo apt update && sudo apt upgrade -y
sudo apt install -y hostapd dnsmasq lighttpd php-cgi

# ═══════════════════════════════════════════════════════════════
# STEP 3: Configure Static IP for wlan0
# ═══════════════════════════════════════════════════════════════
sudo nano /etc/dhcpcd.conf
# Add at the end:
# interface wlan0
#     static ip_address=192.168.4.1/24
#     nohook wpa_supplicant

# ═══════════════════════════════════════════════════════════════
# STEP 4: Configure DHCP Server (dnsmasq)
# ═══════════════════════════════════════════════════════════════
sudo mv /etc/dnsmasq.conf /etc/dnsmasq.conf.orig
sudo nano /etc/dnsmasq.conf
# Add:
# interface=wlan0
# dhcp-range=192.168.4.2,192.168.4.20,255.255.255.0,24h
# address=/#/192.168.4.1

# ═══════════════════════════════════════════════════════════════
# STEP 5: Configure Access Point (hostapd)
# ═══════════════════════════════════════════════════════════════
sudo nano /etc/hostapd/hostapd.conf
```

#### hostapd.conf (Complete Configuration)

```ini
# /etc/hostapd/hostapd.conf
# PegLeg WiFi Access Point Configuration

interface=wlan0
driver=nl80211

# Network Settings
ssid=PegLeg
hw_mode=g
channel=7
ieee80211n=1

# Security (Open Network)
auth_algs=1
wpa=0

# Performance
wmm_enabled=0
macaddr_acl=0
ignore_broadcast_ssid=0

# Country Code (adjust for your region)
# country_code=US
```

```bash
# ═══════════════════════════════════════════════════════════════
# STEP 6: Enable hostapd
# ═══════════════════════════════════════════════════════════════
sudo nano /etc/default/hostapd
# Uncomment and set: DAEMON_CONF="/etc/hostapd/hostapd.conf"

sudo systemctl unmask hostapd
sudo systemctl enable hostapd
sudo systemctl enable dnsmasq

# ═══════════════════════════════════════════════════════════════
# STEP 7: Set Up Web Server
# ═══════════════════════════════════════════════════════════════
sudo lighttpd-enable-mod fastcgi-php
sudo systemctl enable lighttpd

# Create landing page
sudo mkdir -p /var/www/html/shared
sudo chown -R www-data:www-data /var/www/html

# ═══════════════════════════════════════════════════════════════
# STEP 8: Reboot and Test
# ═══════════════════════════════════════════════════════════════
sudo reboot
```

#### Sample Landing Page (index.html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🏴‍☠️ PegLeg</title>
    <style>
        body {
            font-family: 'Courier New', monospace;
            background: #1a1a2e;
            color: #eee;
            text-align: center;
            padding: 20px;
        }
        h1 { color: #e94560; }
        a { color: #0f3460; background: #e94560; padding: 10px 20px; 
            text-decoration: none; border-radius: 5px; }
        .container { max-width: 600px; margin: 0 auto; }
    </style>
</head>
<body>
    <div class="container">
        <h1>🏴‍☠️ Welcome to PegLeg</h1>
        <p>You've connected to an implanted wireless dead drop.</p>
        <p><a href="/shared/">📁 Browse Files</a></p>
        <p><a href="/chat/">💬 Join Chat</a></p>
        <hr>
        <small>Information wants to be free.</small>
    </div>
</body>
</html>
```

### Network Architecture

```
    ┌─────────────────────────────────────────┐
    │          PEGLEG IMPLANT                 │
    │          (Under Skin)                   │
    │                                         │
    │   ┌─────────────────────────────────┐   │
    │   │      Raspberry Pi Zero W        │   │
    │   │                                 │   │
    │   │  ┌───────────┐  ┌───────────┐   │   │
    │   │  │  hostapd  │  │  dnsmasq  │   │   │
    │   │  │  (AP)     │  │ (DHCP/DNS)│   │   │
    │   │  └─────┬─────┘  └─────┬─────┘   │   │
    │   │        │              │         │   │
    │   │        └──────┬───────┘         │   │
    │   │               │                 │   │
    │   │        ┌──────┴──────┐          │   │
    │   │        │  lighttpd   │          │   │
    │   │        │ (Web Server)│          │   │
    │   │        └──────┬──────┘          │   │
    │   │               │                 │   │
    │   │  ┌────────────┼────────────┐    │   │
    │   │  │            │            │    │   │
    │   │  ▼            ▼            ▼    │   │
    │   │ [Portal]   [Files]     [Chat]   │   │
    │   │                                 │   │
    │   └─────────────────────────────────┘   │
    │                                         │
    │   WiFi: SSID "PegLeg" (Open)            │
    │   IP: 192.168.4.1                       │
    │                                         │
    └───────────────────┬─────────────────────┘
                        │
                        │ 802.11n WiFi
                        │ (Local Only)
                        │
         ┌──────────────┼──────────────┐
         │              │              │
         ▼              ▼              ▼
    ┌─────────┐   ┌─────────┐   ┌─────────┐
    │ 📱      │   │ 💻      │   │ 📲      │
    │ Phone   │   │ Laptop  │   │ Tablet  │
    └─────────┘   └─────────┘   └─────────┘
    
    All devices connect to 192.168.4.1
    and are auto-redirected to portal
```

---

## Usage

### Quick Start Guide

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  🔋 POWER    │───▶│  📶 CONNECT  │───▶│  🌐 BROWSE   │───▶│  🎉 INTERACT │
│              │    │              │    │              │    │              │
│ Place Qi pad │    │ Find WiFi    │    │ Open any URL │    │ Share files  │
│ on skin      │    │ "PegLeg"     │    │ Auto-redirect│    │ Chat & more  │
└──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
```

### Detailed Steps

| Step | Action | Details |
|------|--------|---------|
| 1️⃣ | **Power On** | Place a Qi wireless charger against the skin over the implant site. Wait ~10 seconds for boot. |
| 2️⃣ | **Connect** | On your device, search for WiFi network `PegLeg` and connect (no password). |
| 3️⃣ | **Access** | Open any browser and navigate to any URL — you'll be redirected to the portal. |
| 4️⃣ | **Interact** | Browse files, upload content, or join the local chat. |
| 5️⃣ | **Power Off** | Remove the Qi charger. The device will safely shut down. |

### LED Status Indicators (if equipped)

| LED State | Meaning |
|-----------|---------|
| 🟢 Solid Green | Powered on, WiFi active |
| 🟢 Blinking Green | Network activity |
| 🔴 Solid Red | Booting or error |
| ⚫ Off | No power |

### Power Considerations

```
Power Consumption Estimates:
┌────────────────────────────────────┐
│ State          │ Current Draw      │
├────────────────┼───────────────────┤
│ Idle           │ ~120mA @ 5V       │
│ WiFi Active    │ ~150-200mA @ 5V   │
│ File Transfer  │ ~200-250mA @ 5V   │
│ Peak           │ ~300mA @ 5V       │
└────────────────┴───────────────────┘

Typical Qi receiver provides 5V @ 1A
(sufficient with margin for stability)
```

---

## Safety Considerations

> ⚠️ **This section is critically important. Read thoroughly before attempting any implantation.**

### Risk Assessment Matrix

| Risk | Severity | Likelihood | Mitigation |
|------|----------|------------|------------|
| **Infection** | 🔴 High | Medium | Proper sterilization, professional implantation, biocompatible materials, antibiotics |
| **Heat Generation** | 🟡 Medium | Low | Low-power operation, heat dissipation through coating, thermal monitoring |
| **Tissue Rejection** | 🔴 High | Medium | Medical-grade silicone or resin encapsulation, proper wound care |
| **Power Loss Data Corruption** | 🟢 Low | High | Graceful shutdown scripts, journaling filesystem (ext4), read-only root |
| **MRI Incompatibility** | 🔴 Critical | N/A | **NEVER undergo MRI scans** |
| **X-ray/CT Interference** | 🟢 Low | Medium | Inform medical staff; minimal interference expected |
| **Security/Privacy** | 🟡 Medium | Medium | No logging, encrypted storage optional, physical access required |

### ⚠️ MRI WARNING

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                                                                           ║
║   ████████████████████████████████████████████████████████████████████   ║
║   █                                                                   █   ║
║   █   🚨 CRITICAL: DO NOT UNDERGO MRI SCANS WITH THIS IMPLANT 🚨     █   ║
║   █                                                                   █   ║
║   ████████████████████████████████████████████████████████████████████   ║
║                                                                           ║
║   MRI machines generate extremely powerful magnetic fields that can:      ║
║                                                                           ║
║   • HEAT metal components rapidly, causing severe burns                   ║
║   • MOVE or DISPLACE the implant within tissue                           ║
║   • DESTROY electronic components permanently                             ║
║   • Cause TISSUE DAMAGE from induced currents                            ║
║                                                                           ║
║   ALWAYS inform ALL medical staff about your implant before any scan.    ║
║   Consider wearing a medical alert bracelet.                              ║
║                                                                           ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

### Encapsulation Requirements

For safe implantation, the device **MUST** be properly encapsulated:

| Material | Pros | Cons |
|----------|------|------|
| **Medical-Grade Silicone** | Flexible, biocompatible, proven | May degrade over time |
| **Epoxy Resin** | Hard, durable, waterproof | Rigid, may crack |
| **Parylene Coating** | Ultra-thin, excellent biocompatibility | Requires special equipment |
| **PDMS (Polydimethylsiloxane)** | Flexible, biocompatible | May allow moisture ingress |

### Pre-Implantation Checklist

- [ ] Device fully tested and functional before encapsulation
- [ ] Proper biocompatible coating applied (bubble-free)
- [ ] Coating cured completely (follow manufacturer guidelines)
- [ ] All edges smooth with no sharp corners
- [ ] Sterilization protocol established
- [ ] Professional implanter identified (body modification artist with experience)
- [ ] Aftercare supplies ready (antibiotics, wound care)
- [ ] Emergency plan if complications arise

## Troubleshooting

### Common Issues

<details>
<summary><b>📶 WiFi network not appearing</b></summary>

**Symptoms:** Device is powered but no "PegLeg" network visible.

**Solutions:**
1. Ensure Qi charger is properly aligned over the implant
2. Wait 30-60 seconds for full boot
3. Check if `hostapd` service is running (if you have SSH access)
4. Verify `wlan0` is not in managed mode
5. Try different WiFi channel in `hostapd.conf`

```bash
# Debug commands (via SSH)
sudo systemctl status hostapd
sudo journalctl -u hostapd
iwconfig wlan0
```
</details>

<details>
<summary><b>🌐 Captive portal not loading</b></summary>

**Symptoms:** Connected to WiFi but browser doesn't redirect.

**Solutions:**
1. Try navigating to `http://192.168.4.1` directly
2. Clear browser cache/try incognito mode
3. Check `dnsmasq` is running
4. Verify DNS redirect in `dnsmasq.conf`

```bash
# Debug commands
sudo systemctl status dnsmasq
cat /etc/dnsmasq.conf | grep address
```
</details>

<details>
<summary><b>🔋 Device not powering on</b></summary>

**Symptoms:** No activity, no network, LED not lighting.

**Solutions:**
1. Verify Qi charger is working (test with phone)
2. Ensure proper alignment over coil
3. Check if capacitor has failed (requires physical inspection)
4. Solder joints may have failed

</details>

<details>
<summary><b>🔥 Device feels warm</b></summary>

**Symptoms:** Noticeable warmth at implant site during use.

**Solutions:**
1. Some warmth is normal during high activity
2. If uncomfortable, remove Qi charger immediately
3. Let device cool before resuming
4. Consider reducing WiFi transmission power in software
5. **If persistent burning sensation, seek medical attention**

</details>

---

## FAQ

<details>
<summary><b>❓ Is this legal?</b></summary>

**Short answer:** In most jurisdictions, yes — for personal use.

Body modification is generally legal in most countries. However:
- Broadcasting WiFi may have regulations (usually fine for low-power personal use)
- Some countries have restrictions on unlicensed radio equipment
- Always check local laws before implanting

</details>

<details>
<summary><b>❓ How long does the battery last?</b></summary>

**There is no battery.** The PegLeg is powered exclusively by wireless (Qi) charging. It operates only when a Qi charger is held against the implant site. When the charger is removed, the device shuts down.

</details>

<details>
<summary><b>❓ Can I go through airport security?</b></summary>

**Yes, generally.** The implant should not trigger metal detectors due to minimal metal content. X-ray machines will see it, but it's not prohibited. Be prepared to explain if questioned.

</details>

<details>
<summary><b>❓ Can I get an MRI with this implant?</b></summary>

**NO. ABSOLUTELY NOT.** MRI machines use powerful magnetic fields that can heat, move, or destroy the implant and cause serious injury. Always inform medical professionals about your implant.

</details>

<details>
<summary><b>❓ How much does it cost to build?</b></summary>

| Component | Estimated Cost |
|-----------|----------------|
| Raspberry Pi Zero W | $15 |
| Qi Receiver | $5-10 |
| MicroSD Card | $8-15 |
| Encapsulation Materials | $20-50 |
| Misc (capacitor, wires) | $5 |
| **Total** | **~$50-100** |

*Implantation costs vary widely depending on location and professional.*

</details>

<details>
<summary><b>❓ What's the range of the WiFi?</b></summary>

**Approximately 5-15 meters (15-50 feet)** depending on:
- Tissue depth and thickness
- Encapsulation material
- Environmental interference
- Client device sensitivity

Through human tissue, expect reduced range compared to an external Pi Zero W.

</details>

<details>
<summary><b>❓ Can the implant be removed?</b></summary>

**Yes,** through a minor surgical procedure similar to the implantation. Consult with a medical professional or experienced body modification artist for safe removal.

</details>

---

## References & Inspiration

### 📚 Official Resources

| Resource | Description |
|----------|-------------|
| 🏴‍☠️ [PegLeg.org](https://www.pegleg.org/) | PegLeg project documentation (historical/archive) |
| 📦 [PirateBox DIY](https://piratebox.cc/) | The original software foundation (project archived) |
| 🍓 [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) | Official hardware specifications |
| 📖 [hostapd Documentation](https://w1.fi/hostapd/) | WiFi access point daemon |

### 📰 News & Articles

- 📺 [Raspberry Pi Zero implanted under the skin - Geeky Gadgets](https://www.geeky-gadgets.com/raspberry-pi-zero-implanted-under-the-skin/)
- 🔧 [PegLeg Implants Raspberry Pi Zero Ws in Humans - Tom's Hardware](https://www.tomshardware.com/news/pegleg-implants-raspberry-pi-zero-ws-in-humans)
- 📰 [Raspberry Pi implanted in a human body - Electronics Weekly](https://www.electronicsweekly.com/news/raspberry-pi-implanted-human-body/)
- 🌐 [The Pegleg: an implanted, meshing, networked mass-storage device - Boing Boing](https://boingboing.net/2019/08/08/pegleg-implant.html)

### 🔗 Related Projects

| Project | Description |
|---------|-------------|
| [LibraryBox](https://librarybox.us/) | Portable digital library (PirateBox fork) |
| [Dangerous Things](https://dangerousthings.com/) | Biohacking implant supplier |
| [Dead Drops](https://deaddrops.com/) | USB dead drop art project |
| [OpenWrt](https://openwrt.org/) | Alternative router firmware |

### 🎥 Videos & Talks

- DEF CON 27 Biohacking Village — PegLeg demonstration
- Various YouTube tutorials on PirateBox setup
- Raspberry Pi Zero W access point tutorials

---

## Technical Specifications

### Raspberry Pi Zero W Specs

| Specification | Value |
|--------------|-------|
| **CPU** | BCM2835 (ARM11) @ 1GHz |
| **RAM** | 512MB LPDDR2 |
| **WiFi** | 802.11 b/g/n (2.4GHz) |
| **Bluetooth** | BT 4.1, BLE |
| **GPIO** | 40-pin header (unpopulated) |
| **Storage** | MicroSD slot |
| **Dimensions** | 65mm × 30mm × 5mm |
| **Power** | 5V @ 1.2A (recommended) |

### Minimum System Requirements

| Requirement | Specification |
|-------------|---------------|
| MicroSD | 8GB minimum (Class 10 recommended) |
| Power | 5V @ 500mA minimum, 1A recommended |
| Qi Receiver | 5V output, >500mA capability |

---

## Contributing

This documentation is part of the [human-embedded-tech](../) repository. Contributions are welcome!

### Ways to Contribute

- 📝 Improve documentation
- 🐛 Report issues or errors
- 💡 Suggest enhancements
- 🔧 Add technical details or configurations
- 🌐 Add translations

---

## Changelog

| Date | Changes |
|------|---------|
| 2024 | Initial documentation created |
| - | Comprehensive hardware/software guides added |
| - | Safety considerations expanded |
| - | FAQ section added |

---

## License

This documentation is provided for **educational purposes only**. 

- Hardware designs and concepts are open source where applicable
- Respect the original creators' work and licenses
- PirateBox and related software have their own licenses
- Use at your own risk

---

<p align="center">
  <br/>
  <img src="https://img.shields.io/badge/Made%20with-❤️-red" alt="Made with love"/>
  <img src="https://img.shields.io/badge/For-Biohackers-green" alt="For Biohackers"/>
  <img src="https://img.shields.io/badge/Status-Educational-blue" alt="Educational"/>
  <br/><br/>
  <i>🏴‍☠️ "Information wants to be free" — Stewart Brand</i>
  <br/><br/>
  <b>⚠️ This is educational content. Implant at your own risk. ⚠️</b>
</p>
