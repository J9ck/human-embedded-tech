# 🏷️ Complete Guide to Biohacking Implants

This comprehensive guide covers every type of implant available in the biohacking community, from basic RFID chips to advanced computing devices.

---

## Table of Contents

- [Understanding Implant Basics](#understanding-implant-basics)
- [Passive Implants (No Power Required)](#passive-implants-no-power-required)
  - [RFID Implants](#rfid-implants)
  - [NFC Implants](#nfc-implants)
  - [Dual-Frequency Implants](#dual-frequency-implants)
  - [Magnetic Implants](#magnetic-implants)
- [Active Implants (Powered)](#active-implants-powered)
  - [LED Implants](#led-implants)
  - [Sensing Implants](#sensing-implants)
  - [Computing Implants](#computing-implants)
- [Form Factors](#form-factors)
- [Comparison Tables](#comparison-tables)
- [Placement Guide](#placement-guide)
- [Choosing Your Implant](#choosing-your-implant)

---

## Understanding Implant Basics

### How Implants Work

```
PASSIVE IMPLANTS (RFID/NFC):
                                              
    READER ─────────────────────► IMPLANT                   
      │                              │                       
      │ Electromagnetic              │ Receives energy,      
      │ field (13.56MHz              │ powers chip,          
      │ or 125kHz)                   │ sends data back       
      │                              │                       
      └──────────────────────────────┘                       
           Reader receives                                   
           chip response                                     

ACTIVE IMPLANTS (Powered):

    EXTERNAL                                               
    POWER    ─────────► IMPLANT ──────► FUNCTION           
    (Qi/Battery)           │               │               
                           │               │               
                           └── LED/WiFi/   │               
                               Sensor/etc  │               
                                           ▼               
                                      OUTPUT               
                                (Light/Data/etc)           
```

### Key Terminology

| Term | Definition |
|------|------------|
| **RFID** | Radio Frequency Identification - uses radio waves to read/write data |
| **NFC** | Near Field Communication - short-range RFID subset at 13.56MHz |
| **LF** | Low Frequency - 125kHz, longer range, simpler |
| **HF** | High Frequency - 13.56MHz, more data, more features |
| **NDEF** | NFC Data Exchange Format - standard data format for NFC |
| **UID** | Unique Identifier - factory-set chip ID |
| **Biocompatible** | Safe for long-term contact with body tissue |
| **Encapsulation** | Protective coating around electronics |

---

## Passive Implants (No Power Required)

### RFID Implants

RFID implants operate at **125kHz (Low Frequency)** and are primarily used for access control and identification.

#### Popular LF/RFID Implants

| Implant | Chip | Size | Rewritable | Best For |
|---------|------|------|------------|----------|
| **xEM** | T5577 | 2x12mm | ✅ Yes | Access control cloning |
| **xHT** | Hitag | 2x12mm | ⚠️ Partial | Specific access systems |
| **xLED-LF** | LED only | 2x12mm | N/A | Visual feedback |

#### xEM Deep Dive

The **xEM** is the most versatile LF implant available:

```
┌─────────────────────────────────────────────────────────────┐
│                         xEM IMPLANT                          │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Chip: EM4305 / T5577                                      │
│   Frequency: 125kHz                                          │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │   ┌───────┐                                        │   │
│   │   │ CHIP  ├─────[  COPPER ANTENNA COIL  ]         │   │
│   │   │       │                                        │   │
│   │   └───────┘                                        │   │
│   │                                                     │   │
│   │   Schott 8625 biocompatible glass                  │   │
│   │   2mm diameter × 12mm length                        │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   CAN EMULATE:                                               │
│   • EM410x (default)                                         │
│   • HID ProxCard II                                          │
│   • Indala                                                   │
│   • AWID                                                     │
│   • Pyramid                                                  │
│   • And more...                                              │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

**Use Cases:**
- ✅ Clone gym access cards
- ✅ Clone work badges (125kHz systems)
- ✅ Clone hotel room keys (older systems)
- ✅ Garage door openers
- ❌ Cannot do NFC phone interactions
- ❌ Cannot store URLs or text

---

### NFC Implants

NFC implants operate at **13.56MHz (High Frequency)** and can interact with smartphones and modern access systems.

#### Popular NFC Implants

| Implant | Chip | Memory | UID Type | Best For |
|---------|------|--------|----------|----------|
| **xNT** | NTAG216 | 888 bytes | Fixed 7-byte | URLs, vCards, general NFC |
| **xSIID** | NTAG I2C | 888 bytes | Fixed 7-byte | NFC + LED feedback |
| **xMagic** | Magic NTAG | 888 bytes | Changeable | Cloning NFC systems |
| **Spark 2** | VivoKey | Varies | Secure | Cryptographic auth |
| **Apex Flex** | VivoKey Apex | Varies | Secure | Java Card applets, advanced crypto |

#### xNT Deep Dive

The **xNT** is the most popular starter NFC implant:

```
┌─────────────────────────────────────────────────────────────┐
│                         xNT IMPLANT                          │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Chip: NTAG216                                              │
│   Frequency: 13.56MHz (NFC/HF)                              │
│   Memory: 888 bytes user memory                              │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │   ┌───────┐                                        │   │
│   │   │NTAG216├─────[  COPPER ANTENNA COIL  ]         │   │
│   │   │       │                                        │   │
│   │   └───────┘                                        │   │
│   │                                                     │   │
│   │   Schott 8625 biocompatible glass                  │   │
│   │   2mm diameter × 12mm length                        │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   CAPABILITIES:                                              │
│   • NDEF data (URLs, vCards, text, etc.)                    │
│   • Password protection                                      │
│   • Works with all NFC smartphones                           │
│   • ISO14443A compliant                                      │
│                                                              │
│   MEMORY LAYOUT:                                             │
│   ┌──────────┬───────────────────┬─────────┐                │
│   │ Header   │ User Data (888B)  │ Config  │                │
│   │ 48 bytes │                   │ 16 bytes│                │
│   └──────────┴───────────────────┴─────────┘                │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

**Use Cases:**
- ✅ Share contact info (vCard)
- ✅ Share URLs (resume, portfolio)
- ✅ Unlock smartphone apps
- ✅ Trigger phone automations
- ✅ Some NFC door locks
- ❌ Cannot clone most access cards
- ❌ Fixed UID (can't emulate other chips)

#### xSIID - NFC with LED

The **xSIID** adds a visible LED that glows when scanned:

```
┌─────────────────────────────────────────────────────────────┐
│                        xSIID IMPLANT                         │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Chip: NTAG I2C (NFC) + LED                                │
│   Frequency: 13.56MHz                                        │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │   ┌───────┐ ┌─────┐                                │   │
│   │   │ CHIP  ├─┤ LED ├──[  ANTENNA COIL  ]           │   │
│   │   │       │ │ ◉   │                                │   │
│   │   └───────┘ └─────┘                                │   │
│   │                                                     │   │
│   │   3mm diameter × 13mm length                        │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   LED COLORS AVAILABLE:                                      │
│   • 🔴 Red                                                   │
│   • 🟢 Green                                                 │
│   • 🔵 Blue                                                  │
│   • ⚪ White                                                 │
│   • 🟡 Amber                                                 │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

### Dual-Frequency Implants

These implants combine both LF (125kHz) and HF (13.56MHz) in one package.

#### NExT Implant

The **NExT** is the most popular dual-frequency implant and recommended first implant:

```
┌─────────────────────────────────────────────────────────────┐
│                        NExT IMPLANT                          │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   ┌───────────────────┬───────────────────┐                 │
│   │    LF SECTION     │    HF SECTION     │                 │
│   │                   │                   │                 │
│   │   Chip: T5577     │   Chip: NTAG216   │                 │
│   │   Freq: 125kHz    │   Freq: 13.56MHz  │                 │
│   │   Rewritable: Yes │   Memory: 888B    │                 │
│   │                   │                   │                 │
│   │   ┌──────┐        │        ┌──────┐   │                 │
│   │   │ CHIP ├──⌒⌒⌒──│────────┤ CHIP │   │                 │
│   │   └──────┘        │        └──────┘   │                 │
│   │                   │                   │                 │
│   └───────────────────┴───────────────────┘                 │
│                                                              │
│   Total Size: 2mm × 14mm                                     │
│                                                              │
│   BEST OF BOTH WORLDS:                                       │
│   • Clone 125kHz access cards (LF side)                     │
│   • Store URLs/vCards (HF side)                              │
│   • Use with smartphone NFC (HF side)                        │
│   • One implant, two technologies                            │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

### Magnetic Implants

Magnetic implants provide a "sixth sense" by allowing you to feel electromagnetic fields.

#### xG3 Magnet

```
┌─────────────────────────────────────────────────────────────┐
│                         xG3 MAGNET                           │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Type: Neodymium N52 (strongest available)                 │
│   Coating: TiN (Titanium Nitride) biocompatible             │
│   Versions: v1 (sensing) / v2 (lifting)                     │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │            ┌───────────────────┐                   │   │
│   │            │     N52 MAGNET    │                   │   │
│   │            │   [N]═══════[S]   │                   │   │
│   │            │                   │                   │   │
│   │            └───────────────────┘                   │   │
│   │                                                     │   │
│   │   3mm diameter × 10-15mm length                     │   │
│   │   TiN coating for biocompatibility                  │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   WHAT YOU CAN FEEL:                                         │
│   • Running motors and fans                                  │
│   • Transformers (power bricks)                              │
│   • Microwave ovens                                          │
│   • Live electrical wires                                    │
│   • Hard drives spinning                                     │
│   • Anti-theft gates                                         │
│                                                              │
│   v1 vs v2:                                                  │
│   • v1: Optimized for sensing (smaller, more vibration)     │
│   • v2: Optimized for lifting (stronger, less vibration)    │
│                                                              │
│   ⚠️ MRI WARNING: May be unsafe                             │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

**Sensing Use Cases:**
- 🔌 Feel when devices are on
- ⚡ Detect live wires (non-contact)
- 🔧 Troubleshoot electrical equipment
- 🎭 Party trick (pick up small metal objects)

**Considerations:**
- Takes 1-3 months to develop sensitivity
- Placement significantly affects sensation
- Can interfere with some electronics
- Some MRI concerns (varies by strength)

---

## Active Implants (Powered)

Active implants require external power (usually wireless Qi charging) and can perform more complex functions.

### LED Implants

#### Northstar (Grindhouse Wetware)

```
┌─────────────────────────────────────────────────────────────┐
│                      NORTHSTAR IMPLANT                       │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Type: Subdermal LED array                                  │
│   Power: Inductive (wireless)                                │
│   Size: ~30mm diameter disc                                  │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │              ╭───────────────────╮                  │   │
│   │              │   ◉   ◉   ◉      │                  │   │
│   │              │     ◉   ◉        │                  │   │
│   │              │   ◉   ◉   ◉      │                  │   │
│   │              │      (LEDs)      │                  │   │
│   │              ╰───────────────────╯                  │   │
│   │                                                     │   │
│   │   Red LEDs visible through skin                     │   │
│   │   Powered by holding magnet over implant            │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   STATUS: Discontinued, but inspired other projects          │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### Sensing Implants

#### Circadia (Historical)

The **Circadia** was one of the first biometric-transmitting implants:

```
┌─────────────────────────────────────────────────────────────┐
│                      CIRCADIA IMPLANT                        │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Developer: Grindhouse Wetware (2013)                       │
│   Function: Transmit biometric data via Bluetooth            │
│                                                              │
│   Features:                                                  │
│   • Temperature sensing                                      │
│   • Bluetooth data transmission                              │
│   • External charging                                        │
│                                                              │
│   Status: Historical/prototype                               │
│   Significance: Proved complex implants were possible        │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### Computing Implants

#### PegLeg

The **PegLeg** is an implantable Raspberry Pi Zero W computer:

```
┌─────────────────────────────────────────────────────────────┐
│                       PEGLEG IMPLANT                         │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   Core: Raspberry Pi Zero W                                  │
│   Power: Qi wireless charging                                │
│   Function: WiFi dead drop / file server / mesh node         │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │   ┌───────────────────────────────────────────┐    │   │
│   │   │         RASPBERRY PI ZERO W               │    │   │
│   │   │   ┌─────────────────────────────────┐     │    │   │
│   │   │   │ BCM2835 + 512MB RAM             │     │    │   │
│   │   │   │ WiFi 802.11n + Bluetooth 4.1    │     │    │   │
│   │   │   └─────────────────────────────────┘     │    │   │
│   │   └───────────────────────────────────────────┘    │   │
│   │                      │                              │   │
│   │                 ┌────┴────┐                         │   │
│   │                 │Qi Coil  │                         │   │
│   │                 └─────────┘                         │   │
│   │                                                     │   │
│   │   All encased in biocompatible coating             │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
│   CAPABILITIES:                                              │
│   • Creates WiFi hotspot ("PegLeg")                         │
│   • Anonymous file sharing                                   │
│   • Local chat server                                        │
│   • Mesh networking with other PegLegs                       │
│                                                              │
│   ⚠️ HIGHLY EXPERIMENTAL - Significant risks                │
│                                                              │
│   📁 Full documentation: ../pegleg/README.md                 │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## Form Factors

Implants come in different shapes and sizes:

```
CYLINDRICAL (Most Common)
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   ┌────────────────────┐                                    │
│   │ ○═══════════════○  │  2mm × 12-14mm                    │
│   └────────────────────┘                                    │
│                                                              │
│   Examples: xNT, xEM, NExT, xSIID                           │
│   Pros: Easy injection, minimal trauma, standard sizing      │
│   Cons: Limited antenna size, read range ~1-3cm              │
│                                                              │
└──────────────────────────────────────────────────────────────┘

FLEX (Flexible PCB)
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   ┌────────────────────────────┐                            │
│   │ ╭────────────────────────╮ │                            │
│   │ │   ~~~~~~~~~~~~        │ │  ~8mm × 30-40mm            │
│   │ │     (antenna)         │ │                            │
│   │ ╰────────────────────────╯ │                            │
│   └────────────────────────────┘                            │
│                                                              │
│   Examples: flexNExT, flexDF, flexEM                         │
│   Pros: Much larger antenna, better read range (5-10cm)      │
│   Cons: Requires scalpel installation, larger wound          │
│                                                              │
└──────────────────────────────────────────────────────────────┘

DISC (Round/Subdermal)
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│        ╭─────────────╮                                       │
│       ╱               ╲                                      │
│      │    ◉  ◉  ◉    │   20-30mm diameter                  │
│       ╲               ╱                                      │
│        ╰─────────────╯                                       │
│                                                              │
│   Examples: Northstar, custom sensing implants               │
│   Pros: Large surface area for LEDs/sensors                  │
│   Cons: Significant surgery required, higher risk            │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## Comparison Tables

### At-a-Glance Comparison

| Implant | Type | Frequency | Memory | Price | Best For |
|---------|------|-----------|--------|-------|----------|
| **xEM** | RFID | 125kHz | N/A | ~$40 | Access cloning |
| **xNT** | NFC | 13.56MHz | 888B | ~$50 | URLs, vCards |
| **NExT** | Dual | Both | 888B | ~$70 | Best starter |
| **xSIID** | NFC+LED | 13.56MHz | 888B | ~$100 | Visual feedback |
| **xMagic** | NFC | 13.56MHz | 888B | ~$90 | NFC cloning |
| **xG3** | Magnet | N/A | N/A | ~$50 | EM sensing |
| **Spark 2** | NFC | 13.56MHz | Varies | ~$200 | Security/crypto |
| **flexNExT** | Dual/Flex | Both | 888B | ~$180 | Extended range |
| **Apex Flex** | NFC/Crypto | 13.56MHz | Varies | ~$350 | Java applets, advanced security |

### Compatibility Matrix

| Feature | xEM | xNT | NExT | xSIID | xMagic | Spark | Apex |
|---------|-----|-----|------|-------|--------|-------|------|
| Phone NFC | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Clone 125kHz cards | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Clone NFC cards | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ |
| Store URLs | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Password protect | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| LED feedback | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| Cryptographic auth | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Java Card applets | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| MRI safe | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

---

## Placement Guide

### Common Implant Locations

```
                    HAND PLACEMENT MAP
                    
                        ┌───────────────┐
                        │               │
                        │   FINGERS     │
                        │  (Not common  │
                        │   for chips)  │
                        │       │       │
                ┌───────┴───────┴───────┴───────┐
                │                               │
          ┌─────┤      METACARPAL AREA          ├─────┐
          │     │        (Most Popular)         │     │
    THUMB │     │                               │     │
    WEB   │  ★  │     Between index and         │     │
    SPACE │     │     thumb metacarpals         │     │
    (Best)│     │     (Position 0)              │     │
          │     │                               │     │
          └─────┴───────────────────────────────┴─────┘
                              │
                              │
                        ┌─────┴─────┐
                        │   WRIST   │
                        │ (Possible │
                        │ but risky)│
                        └───────────┘

POSITION KEY:
★ Position 0 - Between thumb and index metacarpals (MOST COMMON)
  • Easy installation
  • Low risk
  • Good read range
  • Won't interfere with gripping
```

### Position 0 Detail

```
                    TOP VIEW OF LEFT HAND
                    
                            Index finger
                                │
                                │
                            ┌───┴───┐
                            │       │
                            │   ★   │◄── IMPLANT HERE
                            │       │    (Position 0)
                ────────────┴───────┴────────────
               │                                 │
               │         Palm side               │
               │                                 │
    Thumb ─────┤                                 │
               │                                 │
               │                                 │
               └─────────────────────────────────┘
               
    CROSS SECTION:
    
    Skin surface  ════════════════════════════
                          │ ◯ │
                          │   │◄── Implant sits above
                          │   │    muscle, below skin
    Muscle       ─────────┴───┴─────────────────
    Bone         ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓
```

### Multiple Implant Placement

```
    LEFT HAND                          RIGHT HAND
    
    ┌─────────┐                        ┌─────────┐
    │ ◯ NFC   │                        │ ◯ RFID  │
    │ (xNT)   │                        │ (xEM)   │
    └────┬────┘                        └────┬────┘
         │                                  │
    ┌────┴────────┐                  ┌──────┴────┐
    │             │                  │           │
    │   ◯ LED    │                  │  ◯ Mag    │
    │  (xSIID)   │                  │  (xG3)    │
    │             │                  │           │
    └─────────────┘                  └───────────┘
    
    SPACING: Keep implants at least 5mm apart
             to avoid interference and healing issues
```

---

## Choosing Your Implant

### Decision Flowchart

```
START: What do you want to do?
          │
          ▼
    ┌─────────────────────────────────────────────────────┐
    │           What's your primary use case?              │
    └─────────────────────────────────────────────────────┘
          │
          ├──► "Clone my work/gym badge"
          │         │
          │         ▼
          │    Is it 125kHz or 13.56MHz?
          │         │
          │         ├──► 125kHz ──► xEM or NExT
          │         └──► 13.56MHz ──► xMagic (if cloning needed)
          │                          or NExT (if not)
          │
          ├──► "Share my contact info / URL"
          │         │
          │         ▼
          │    Do you also want access control?
          │         │
          │         ├──► Yes ──► NExT (best value)
          │         └──► No ──► xNT (simplest)
          │
          ├──► "I want visual feedback"
          │         │
          │         ▼
          │    xSIID (NFC + LED)
          │
          ├──► "I want to feel electromagnetic fields"
          │         │
          │         ▼
          │    xG3 magnet
          │
          └──► "I want advanced security/crypto"
                    │
                    ▼
               Spark 2 (VivoKey)
```

### Recommendations by User Type

| User Type | Recommended | Why |
|-----------|-------------|-----|
| **Complete Beginner** | NExT | Best value, dual frequency, versatile |
| **Just wants URL sharing** | xNT | Simplest, cheapest NFC option |
| **Access control focus** | xEM or NExT | T5577 can clone most 125kHz cards |
| **Tech enthusiast** | xSIID + xEM | LED feedback + access control |
| **Security professional** | Spark 2 | Cryptographic capabilities |
| **Sensory explorer** | xG3 | Unique sensing ability |
| **Maximum functionality** | NExT + xG3 + xSIID | Complete setup |

---

## Next Steps

| Topic | Link | Description |
|-------|------|-------------|
| **Tools & Equipment** | [Tools Guide](tools-and-equipment.md) | What you need to work with implants |
| **Safety** | [Safety & Legal](safety-and-legal.md) | Critical safety information |
| **DIY Projects** | [DIY Projects](diy-projects.md) | Things to build with your implants |
| **Glossary** | [Glossary](glossary.md) | Terminology reference |

---

<p align="center">
  <a href="getting-started.md">← Getting Started</a> •
  <a href="../README.md">Wiki Home</a> •
  <a href="tools-and-equipment.md">Tools & Equipment →</a>
</p>
