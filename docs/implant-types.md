# 🔌 Implant Types Guide

A comprehensive guide to the different types of implantable technology available for biohacking.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Passive Implants](#passive-implants)
  - [NFC Implants](#nfc-implants)
  - [RFID Implants](#rfid-implants)
  - [Magnetic Implants](#magnetic-implants)
  - [LED Implants](#led-implants)
- [Active Implants](#active-implants)
  - [PegLeg](#pegleg)
  - [Other Active Projects](#other-active-projects)
- [Medical Implants](#medical-implants)
- [Comparison Charts](#comparison-charts)
- [Choosing the Right Implant](#choosing-the-right-implant)

---

## Overview

Implantable technology falls into two main categories:

```
┌─────────────────────────────────────────────────────────────────┐
│                      IMPLANT CATEGORIES                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   PASSIVE IMPLANTS                    ACTIVE IMPLANTS           │
│   ────────────────                    ───────────────           │
│   • No internal power                 • Has power source        │
│   • Powered by reader                 • Battery or wireless     │
│   • Simple function                   • Complex capabilities    │
│   • Small size                        • Larger size             │
│   • Lower risk                        • Higher complexity       │
│   • Common & well-tested              • Experimental            │
│                                                                 │
│   Examples:                           Examples:                 │
│   • NFC chips                         • PegLeg                  │
│   • RFID tags                         • Circadia                │
│   • Magnets                           • North Sense             │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Passive Implants

### NFC Implants

**Near-Field Communication (NFC)** implants are the most popular for beginners due to smartphone compatibility.

#### How NFC Works

```
Phone/Reader                          NFC Implant
┌──────────────┐                     ┌──────────────┐
│              │  ◄── 13.56 MHz ──►  │              │
│   📱 NFC     │      Radio Wave     │  🏷️ Chip    │
│   Reader     │                     │              │
│              │  ◄── Data ────────  │   Storage    │
└──────────────┘                     └──────────────┘
     │                                      │
     │  Range: 1-4 cm                       │
     │  Data: Up to 888 bytes              │
     └──────────────────────────────────────┘
```

#### Popular NFC Implants

| Model | Chip Type | Memory | Features | Price Range |
|-------|-----------|--------|----------|-------------|
| **xNT** | NTAG216 | 888 bytes | Standard NFC, wide compatibility | $40-60 |
| **xSIID** | NTAG I2C | 888 bytes | NFC + LED indicator | $100-130 |
| **NExT** | NTAG216 + T5577 | 888 bytes + 264 bits | Dual NFC + RFID | $70-90 |
| **Spark 2** | P71 + NTAG | 888 bytes + secure | Cryptographic authentication | $150-200 |
| **FlexNT** | NTAG216 | 888 bytes | Flexible form factor, better range | $80-100 |

#### NFC Capabilities

| Capability | Description | Example Use |
|------------|-------------|-------------|
| **URL Storage** | Store web links | Business card, resume link |
| **vCard** | Store contact info | Share phone/email with tap |
| **Text** | Plain text storage | Notes, passwords (not recommended) |
| **Launch Actions** | Trigger phone actions | Open app, toggle setting |
| **Authentication** | Identity verification | Login tokens, 2FA |
| **Smart Home** | IoT triggers | Unlock doors, control lights |

#### Pros & Cons

| ✅ Pros | ❌ Cons |
|---------|---------|
| Smartphone compatible | Very short range (1-4cm) |
| Programmable via phone apps | Limited storage (888 bytes) |
| Wide adoption (payments, transit) | Can be read by any NFC phone |
| No battery needed | Some phones have limited support |
| Well-documented and tested | Security varies by chip type |

---

### RFID Implants

**Radio-Frequency Identification (RFID)** implants operate at various frequencies and are primarily used for access control.

#### RFID Frequency Bands

```
┌─────────────────────────────────────────────────────────────────┐
│                     RFID FREQUENCY SPECTRUM                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   LOW FREQUENCY (LF)          HIGH FREQUENCY (HF)               │
│   ──────────────────          ───────────────────               │
│   125-134 kHz                 13.56 MHz                         │
│                                                                 │
│   • Longer read range         • NFC compatible                  │
│   • Access control            • Smartphone readable             │
│   • Simple protocols          • More complex protocols          │
│   • Less data capacity        • More data capacity              │
│                                                                 │
│   Common chips:               Common chips:                     │
│   • EM4100/EM4102             • NTAG series                     │
│   • HID ProxCard              • MIFARE                          │
│   • T5577 (rewritable)        • ISO 14443/15693                 │
│                                                                 │
│   Typical use:                Typical use:                      │
│   • Building access           • Payments                        │
│   • Gym entry                 • Data transfer                   │
│   • Car ignition              • Transit cards                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### Popular RFID Implants

| Model | Frequency | Chip | Rewritable | Best For |
|-------|-----------|------|------------|----------|
| **xEM** | 125 kHz | T5577 | ✅ Yes | Cloning EM/HID cards |
| **NExT** | 125 kHz + 13.56 MHz | T5577 + NTAG216 | ✅ Yes | Dual-frequency versatility |
| **xHT** | 125 kHz | Hitag S256 | ✅ Yes | Some HID systems |
| **xMagic** | 125 kHz + 13.56 MHz | T5577 + Magic Gen1a | ✅ Yes | MIFARE cloning |

#### RFID Use Cases

1. **Access Card Cloning**
   - Copy gym fobs to implant
   - Clone office door badges
   - Replace car key fobs

2. **Custom Access Control**
   - DIY door locks
   - Arduino projects
   - Computer login

3. **Animal ID Emulation**
   - Compatible with pet ID readers
   - Veterinary scanners

#### Important Considerations

| Consideration | Details |
|---------------|---------|
| **Compatibility** | Not all readers are compatible; test first |
| **Legal Issues** | Cloning cards may violate terms of service |
| **Security** | Basic RFID offers minimal security |
| **Read Range** | Typically 3-10cm through skin |

---

### Magnetic Implants

**Magnetic implants** provide sensory augmentation — the ability to feel electromagnetic fields.

#### How Magnetic Sensing Works

```
┌─────────────────────────────────────────────────────────────────┐
│                    MAGNETIC SENSING                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   Electromagnetic Field Source        Magnetic Implant          │
│   ┌──────────────────────┐           ┌──────────────────┐       │
│   │                      │           │                  │       │
│   │   Motor / Wire /     │ ~~~~~~~~► │   N  ▐▌  S      │       │
│   │   Transformer        │   EM      │   ◄──┼──►       │       │
│   │                      │  Field    │   vibrates      │       │
│   └──────────────────────┘           └──────────────────┘       │
│                                             │                   │
│                                             ▼                   │
│                                    ┌─────────────────┐          │
│                                    │  Nerve Endings  │          │
│                                    │  Feel vibration │          │
│                                    │  = "New Sense"  │          │
│                                    └─────────────────┘          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### Popular Magnetic Implants

| Model | Type | Coating | Strength | Notes |
|-------|------|---------|----------|-------|
| **xG3 v1** | Cylindrical | Glass | Medium | Standard sensing |
| **xG3 v2** | Cylindrical | Glass | Strong | Enhanced sensitivity |
| **Titan** | Disc | Titanium | Strong | Durable, good sensing |
| **m31** | Disc | Various | Medium | Popular classic design |

#### What You Can Feel

| Source | Sensation | Strength |
|--------|-----------|----------|
| Electric motors | Vibration/buzzing | Strong |
| Transformers | Pulsing | Medium |
| AC power lines | Tingling | Medium |
| Microwave ovens | Strong pulse | Strong |
| Hard drives | Subtle vibration | Weak |
| Speakers | Varies with sound | Varies |

#### Placement Considerations

```
                FINGER TIP PLACEMENT
                
        ┌─────────────────────────────────────┐
        │   FINGERTIP (Most sensitive)        │
        │   ┌───────────┐                     │
        │   │     ●     │  ← Best sensation   │
        │   │   magnet  │    but higher risk  │
        │   └───────────┘                     │
        │                                     │
        │   Pros: Maximum nerve density       │
        │   Cons: High use area, more trauma  │
        └─────────────────────────────────────┘
        
        ┌─────────────────────────────────────┐
        │   KNIFE EDGE / WEBBING              │
        │                                     │
        │   Index ─────┐                      │
        │              │ ●  ← Safer location  │
        │   Thumb ─────┘    Lower sensitivity │
        │                                     │
        │   Pros: Protected area, easy install│
        │   Cons: Less sensitive than finger  │
        └─────────────────────────────────────┘
```

#### Pros & Cons

| ✅ Pros | ❌ Cons |
|---------|---------|
| Genuine sensory augmentation | Can't lift heavy objects |
| Feel invisible EM fields | MRI restrictions |
| Simple passive device | Placement affects sensitivity |
| No programming needed | May interfere with touchscreens |
| Conversation starter | Risk of coating degradation |

---

### LED Implants

**LED implants** contain a small light that illuminates through the skin when powered by an NFC reader.

#### How LED Implants Work

```
┌─────────────────────────────────────────────────────────────────┐
│                       LED IMPLANT OPERATION                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   Step 1: Reader approaches             Step 2: LED activates   │
│                                                                 │
│   ┌──────┐    ┌─────────────┐          ┌──────┐  ┌───────────┐  │
│   │  📱  │───►│   ●  ○      │          │  📱  │  │   💡 ○    │  │
│   │      │    │  LED  NFC   │    ──►   │      │  │  LED  NFC │  │
│   └──────┘    └─────────────┘          └──────┘  └───────────┘  │
│                                                                 │
│   NFC field provides power              LED glows through skin  │
│   to the implant                        (visible ~1cm deep)     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### Available LED Implants

| Model | Chip | LED Color | Functions |
|-------|------|-----------|-----------|
| **xSIID** | NTAG I2C | White/Red/Blue/Green | NFC + Visual feedback |
| **xLED** | None (LED only) | Various | Visual only, no data |
| **FlexDF2** | DESFire EV2 | White | Secure NFC + LED |

#### Use Cases

1. **Visual Confirmation** — See when your implant is being read
2. **Unique Identification** — Glow-in-dark party trick
3. **Authentication Feedback** — Know your scan worked
4. **Art/Expression** — Body illumination

---

## Active Implants

Active implants contain their own power source and can perform complex functions.

### PegLeg

The **PegLeg** is the most well-known active implant project — an implantable Raspberry Pi Zero W.

```
┌─────────────────────────────────────────────────────────────────┐
│                          PEGLEG                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌───────────────────────────────────────────────────────────┐ │
│   │                    BIOCOMPATIBLE SHELL                    │ │
│   │   ┌───────────────────────────────────────────────────┐   │ │
│   │   │            RASPBERRY PI ZERO W                    │   │ │
│   │   │   • 1GHz ARM processor                            │   │ │
│   │   │   • 512MB RAM                                     │   │ │
│   │   │   • WiFi 802.11n                                  │   │ │
│   │   │   • Bluetooth 4.1                                 │   │ │
│   │   │   • MicroSD storage                               │   │ │
│   │   └───────────────────────────────────────────────────┘   │ │
│   │                          │                                │ │
│   │                    ┌─────┴─────┐                          │ │
│   │                    │ QI COIL   │  ← Wireless charging     │ │
│   │                    └───────────┘                          │ │
│   └───────────────────────────────────────────────────────────┘ │
│                                                                 │
│   CAPABILITIES:                                                 │
│   • WiFi access point (creates network)                         │
│   • File sharing server                                         │
│   • Local chat system                                           │
│   • Mesh networking                                             │
│   • Powered through skin via Qi charger                         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

📁 **[View Full PegLeg Documentation →](../pegleg/)**

### Other Active Projects

| Project | Description | Status |
|---------|-------------|--------|
| **Circadia** | Biotelemetry device for health monitoring | Experimental |
| **North Sense** | Compass sense (vibrates facing north) | Discontinued |
| **Grindhouse Northstar** | LED grid, gestures, wireless | Prototype |
| **Lovetron9000** | Adult-oriented vibration device | Experimental |

---

## Medical Implants

While not "biohacking" in the traditional sense, these represent the professional end of the implant spectrum:

| Implant | Purpose | Notes |
|---------|---------|-------|
| **Cochlear Implant** | Restore hearing | Mature technology, widely used |
| **Pacemaker** | Regulate heartbeat | Life-saving, decades of use |
| **Insulin Pump** | Diabetes management | Continuous glucose monitoring |
| **Deep Brain Stimulator** | Parkinson's, epilepsy | Complex neurological interface |
| **Retinal Implant** | Restore vision | Emerging technology |
| **Bone Conduction Implant** | Hearing through skull | Alternative to cochlear |

---

## Comparison Charts

### Quick Comparison: All Implant Types

| Type | Power | Size | Complexity | Risk Level | Cost |
|------|-------|------|------------|------------|------|
| NFC | Passive | Small | Low | Low | $40-200 |
| RFID | Passive | Small | Low | Low | $40-100 |
| Magnetic | Passive | Tiny | Very Low | Low-Medium | $50-150 |
| LED | Passive | Small | Low | Low | $60-150 |
| PegLeg | Active | Large | High | High | $100+ |

### By Use Case

| If You Want To... | Best Option | Why |
|-------------------|-------------|-----|
| Share contact/URL | xNT, xSIID | Phone compatible |
| Clone access cards | xEM, NExT | T5577 compatibility |
| Feel EM fields | xG3 | Magnetic sensing |
| Visual feedback | xSIID | LED indicator |
| Maximum versatility | NExT | Dual frequency |
| Run a computer | PegLeg | Full processing power |
| Secure authentication | Spark 2 | Cryptographic chip |

### By Experience Level

| Level | Recommended | Why |
|-------|-------------|-----|
| **Beginner** | xNT, xEM | Simple, well-documented |
| **Intermediate** | NExT, xSIID | More features, still manageable |
| **Advanced** | xMagic, Spark 2 | Complex capabilities |
| **Expert** | PegLeg, custom | High complexity, DIY |

---

## Choosing the Right Implant

### Decision Framework

Ask yourself these questions:

```
┌─────────────────────────────────────────────────────────────────┐
│                    IMPLANT SELECTION FRAMEWORK                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   1. WHAT IS YOUR PRIMARY USE CASE?                             │
│      □ Convenience (access, payments)                           │
│      □ Data sharing (business card, links)                      │
│      □ Sensory augmentation (feel EM fields)                    │
│      □ Projects/experimentation                                 │
│      □ Computing/networking                                     │
│                                                                 │
│   2. WHAT IS YOUR EXPERIENCE LEVEL?                             │
│      □ Complete beginner                                        │
│      □ Some technical knowledge                                 │
│      □ Experienced with electronics/programming                 │
│      □ Professional/expert                                      │
│                                                                 │
│   3. WHAT IS YOUR RISK TOLERANCE?                               │
│      □ Minimal (proven, well-tested)                            │
│      □ Moderate (established but newer)                         │
│      □ High (experimental, cutting-edge)                        │
│                                                                 │
│   4. WHAT IS YOUR BUDGET?                                       │
│      □ Under $50                                                │
│      □ $50-100                                                  │
│      □ $100-200                                                 │
│      □ $200+                                                    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Recommendation Matrix

| Use Case + Level | Budget | Recommendation |
|------------------|--------|----------------|
| Beginner + Sharing | Low | xNT |
| Beginner + Access | Low | xEM |
| Beginner + Both | Medium | NExT |
| Intermediate + Visual | Medium | xSIID |
| Intermediate + Security | High | Spark 2 |
| Advanced + Sensing | Medium | xG3 v2 |
| Expert + Computing | High | PegLeg |

---

## Where to Buy

### Reputable Suppliers

| Supplier | Region | Specialization |
|----------|--------|----------------|
| [Dangerous Things](https://dangerousthings.com) | Global | Widest selection |
| [IAR (I Am Robot)](https://iamrobot.de) | Europe | European shipping |
| [KSEC Solutions](https://ksec.co.uk) | UK | Tools and implants |
| [Digiwell](https://digiwell.com) | Europe | German supplier |

### What's Included

Most implant kits include:
- Sterilized implant
- Injection assembly (if applicable)
- Instructions
- Authentication certificate
- Aftercare guidance

---

## Next Steps

- 📚 **[Read the Safety Guide →](./safety-guide.md)** — Critical safety information
- 🚀 **[Getting Started Guide →](./getting-started.md)** — Begin your journey
- 📖 **[Glossary →](./glossary.md)** — Understand the terminology

---

<p align="center">
  <br/>
  <i>Still have questions? Check community forums or open an issue!</i>
  <br/><br/>
  <b>⚠️ Always research thoroughly before making decisions. ⚠️</b>
</p>
