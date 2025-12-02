# PegLeg Implant Project

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Raspberry_Pi_4_Model_B_-_Side.jpg/320px-Raspberry_Pi_4_Model_B_-_Side.jpg" alt="Raspberry Pi" width="300"/>
</p>

## Overview

**PegLeg** is a biohacking project that involves implanting a single-board computer—typically a Raspberry Pi Zero W—into the human body. The device functions as a wireless, offline file-sharing node (dead drop) and local mesh network. It is powered wirelessly through the skin using a Qi charging coil.

The project represents a fascinating intersection of:
- 🧬 **Biohacking** — pushing the boundaries of human-machine integration
- 📡 **Mesh Networking** — decentralized, anonymous communication
- 🔓 **Open Source** — free culture and information sharing

> **⚠️ DISCLAIMER:** This repository is for educational and informational purposes only. Implanting electronic devices into the human body carries significant medical risks, including infection, rejection, and tissue damage. This is **not** medical advice. Proceed at your own risk.

---

## Hardware Bill of Materials (BOM)

To build a standard PegLeg unit, the following components are typically used:

| Component | Description | Notes |
|-----------|-------------|-------|
| **Raspberry Pi Zero W** | The core computer | Features WiFi and Bluetooth for connectivity. |
| **Qi Receiver Coil** | Power receiver | Must be soldered to the Pi's 5V/GND pads or test points. |
| **MicroSD Card** | Storage | High endurance recommended; capacity depends on use case. |
| **Capacitor** | Power stability | A small capacitor may be needed to smooth power delivery from the Qi coil. |
| **Biocompatible Coating** | Encapsulation | **Critical.** Often medical-grade resin or silicone to prevent rejection. |

### Hardware Diagram

```
┌─────────────────────────────────────────────────────────┐
│                    BIOCOMPATIBLE SHELL                   │
│  ┌─────────────────────────────────────────────────┐    │
│  │                                                 │    │
│  │   ┌───────────────────────────────────────┐    │    │
│  │   │        RASPBERRY PI ZERO W            │    │    │
│  │   │   ┌─────────┐                         │    │    │
│  │   │   │ MicroSD │  [WiFi/BT Antenna]      │    │    │
│  │   │   └─────────┘                         │    │    │
│  │   │                                       │    │    │
│  │   │   5V ●──────┐                         │    │    │
│  │   │   GND●──────┼────┐                    │    │    │
│  │   └─────────────┼────┼────────────────────┘    │    │
│  │                 │    │                         │    │
│  │            ┌────┴────┴────┐                    │    │
│  │            │   CAPACITOR  │                    │    │
│  │            └──────┬───────┘                    │    │
│  │                   │                            │    │
│  │   ╭───────────────┴───────────────╮            │    │
│  │   │      QI RECEIVER COIL         │            │    │
│  │   │         (( ◯ ))               │            │    │
│  │   ╰───────────────────────────────╯            │    │
│  │                                                 │    │
│  └─────────────────────────────────────────────────┘    │
│                                                         │
└─────────────────────────────────────────────────────────┘
                         ↑
                         │ Wireless Power
                         │
               ┌─────────┴─────────┐
               │   QI CHARGER PAD  │
               │      (EXTERNAL)   │
               └───────────────────┘
```

---

## Software Configuration

The software stack is usually based on **PirateBox** or a similar offline network distribution.

### Core Features

| Feature | Description |
|---------|-------------|
| 📶 **WiFi Access Point** | The device broadcasts an open network (SSID: `PegLeg` or similar). |
| 🌐 **Captive Portal** | Users connecting to the network are redirected to a landing page. |
| 💬 **Anonymous Chat** | Built-in IRC or web-based chat for local communication. |
| 📁 **File Sharing** | Directory for uploading and downloading files anonymously. |

### Installation (General Steps)

```bash
# 1. Flash the PirateBox (or LibraryBox) image to the MicroSD card
# Download from: https://piratebox.cc/

# 2. Configure the wlan0 interface to act as an Access Point (AP)
sudo nano /etc/hostapd/hostapd.conf

# Example hostapd.conf:
# interface=wlan0
# driver=nl80211
# ssid=PegLeg
# hw_mode=g
# channel=7
# wmm_enabled=0
# macaddr_acl=0
# auth_algs=1
# ignore_broadcast_ssid=0
# wpa=0

# 3. Set up the web server (lighttpd/nginx) to serve the captive portal
sudo apt install lighttpd
sudo systemctl enable lighttpd

# 4. (Optional) Configure a script to shut down the Pi safely when power is lost
# Add to /etc/rc.local or create a systemd service
```

### Network Architecture

```
    ┌─────────────────────┐
    │   PEGLEG IMPLANT    │
    │   (Pi Zero W)       │
    │                     │
    │  ┌───────────────┐  │
    │  │  WiFi AP      │  │
    │  │  SSID:PegLeg  │  │
    │  └───────┬───────┘  │
    │          │          │
    │  ┌───────┴───────┐  │
    │  │  Web Server   │  │
    │  │  (lighttpd)   │  │
    │  └───────┬───────┘  │
    │          │          │
    │  ┌───────┴───────┐  │
    │  │ Captive Portal│  │
    │  │ + File Share  │  │
    │  │ + Chat        │  │
    │  └───────────────┘  │
    └─────────────────────┘
              │
              │ WiFi (Local)
              ▼
    ┌─────────────────────┐
    │   USER DEVICES      │
    │  📱 💻 📲           │
    │  (Within Range)     │
    └─────────────────────┘
```

---

## Usage

1. **🔋 Power On:** Place a Qi wireless charger against the skin over the implant site.
2. **📶 Connect:** Search for the WiFi network (`PegLeg`) on a phone or laptop.
3. **🌐 Interact:** Open a browser to access the file share or chat.

### User Flow

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│   POWER ON   │───▶│  CONNECT TO  │───▶│ OPEN BROWSER │───▶│   INTERACT   │
│  (Qi Charge) │    │    WiFi      │    │(Auto-Redirect)    │  (Chat/Files)│
└──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
```

---

## Safety Considerations

| Risk | Mitigation |
|------|------------|
| **Infection** | Proper sterilization, professional implantation, biocompatible materials |
| **Heat** | Low-power operation, heat dissipation through coating |
| **Rejection** | Medical-grade silicone or resin encapsulation |
| **Power Loss** | Graceful shutdown scripts, journaling filesystem |
| **MRI Incompatibility** | **DO NOT undergo MRI scans with implant** |

---

## References & Inspiration

### Official Resources
- 🏴‍☠️ [PegLeg.org](https://www.pegleg.org/) — Official PegLeg project site
- 📦 [PirateBox DIY](https://piratebox.cc/) — The software foundation
- 🍓 [Raspberry Pi Zero W Specs](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)

### News & Articles
- [Raspberry Pi Zero implanted under the skin - Geeky Gadgets](https://www.geeky-gadgets.com/raspberry-pi-zero-implanted-under-the-skin/)
- [PegLeg Implants Raspberry Pi Zero Ws in Humans - Tom's Hardware](https://www.tomshardware.com/news/pegleg-implants-raspberry-pi-zero-ws-in-humans)
- [Raspberry Pi implanted in a human body - Electronics Weekly](https://www.electronicsweekly.com/news/raspberry-pi-implanted-human-body/)
- [The Pegleg: an implanted, meshing, networked mass-storage device - Boing Boing](https://boingboing.net/2019/08/08/pegleg-implant.html)

### Related Projects
- [LibraryBox](https://librarybox.us/) — Portable digital library
- [Dangerous Things](https://dangerousthings.com/) — Biohacking implant supplier

---

## Contributing

This documentation is part of the [human-embedded-tech](../) repository. Feel free to submit issues or pull requests to improve this resource.

---

## License

This documentation is provided for educational purposes. Please respect the original creators' work and licenses when using PirateBox and related software.

---

<p align="center">
  <i>🏴‍☠️ "Information wants to be free" — Stewart Brand</i>
</p>
