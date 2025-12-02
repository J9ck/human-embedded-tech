# Implants Guide

This guide provides detailed information about the various types of implantable devices used in human embedded technology.

---

## Overview

Implants can be categorized by their function, frequency, and complexity. Understanding these categories will help you choose the right implant for your needs.

---

## RFID Implants

### Low-Frequency (LF) — 125kHz

| Implant | Chip Type | Capabilities | Best For |
|---------|-----------|--------------|----------|
| **xEM** | T5577 | Writable, multi-format | Cloning access cards |
| **xHT** | Hitag S 2048 | High memory | Advanced access systems |

**Common Use Cases:**

- Cloning workplace access badges
- Replacing gym key fobs
- Home automation triggers

**Compatibility Notes:**

- Works with most older access control systems
- HID, EM4100, and similar protocols
- Range: typically 1-3 cm

---

### High-Frequency (HF) — 13.56MHz

| Implant | Chip Type | Capabilities | Best For |
|---------|-----------|--------------|----------|
| **xNT** | NTAG216 | 888 bytes storage, NFC | Sharing data, URLs |
| **xSIID** | NTAG I2C + LED | NFC + visual feedback | Interactive applications |
| **Spark 2** | P71 secure element | Cryptographic operations | Digital identity |

**Common Use Cases:**

- Storing URLs, business cards, or contact info
- Two-factor authentication
- Smartphone interaction
- Visual confirmation with LED variants

**Compatibility Notes:**

- Works with most modern smartphones
- NFC Forum Type 2 compliant
- Range: typically 1-5 cm

---

### Dual-Frequency Implants

| Implant | Frequencies | Capabilities | Best For |
|---------|-------------|--------------|----------|
| **NExT** | 125kHz + 13.56MHz | Combined LF + HF | Versatility |

**Why Dual-Frequency?**

- One implant, two functions
- Clone legacy badges AND use modern NFC
- Reduced number of implants needed

---

## Magnetic Implants

### Sensing Magnets

| Implant | Type | Coating | Strength |
|---------|------|---------|----------|
| **xG3** | Neodymium | Titanium nitride | Standard |
| **Titan** | Neodymium | Titanium | Enhanced |

**What They Do:**

- Detect electromagnetic fields
- Provide haptic feedback near motors, transformers, live wires
- Pick up small metal objects
- Party tricks (holding objects, moving iron filings)

**Sensory Experience:**

The magnet vibrates in the presence of alternating electromagnetic fields, providing a "sixth sense" for detecting:

- Live electrical wires
- Motors and transformers
- Speakers and headphones
- Security systems

**Placement Considerations:**

| Location | Pros | Cons |
|----------|------|------|
| Fingertip | High sensitivity | Risk during manual work |
| Webbing | Safer location | Less sensitivity |
| Tragus (ear) | Novel sensation | Surgical placement needed |

---

## LED Implants

### Subdermal Lights

| Implant | Type | Activation | Purpose |
|---------|------|------------|---------|
| **xSIID** | NFC + LED | RF field | Scan confirmation |
| **Northstar** | Standalone LED | Touch/magnet | Cosmetic |

**Applications:**

- Visual confirmation when scanning
- Cosmetic/aesthetic enhancement
- Signaling/identification

---

## Biocomputing Implants

### Advanced Implants

These are more experimental and complex:

| Project | Description | Status |
|---------|-------------|--------|
| **PegLeg** | Raspberry Pi Zero W implant | Experimental |
| **Circadia** | Biometric sensor implant | Historical |

**PegLeg Features:**

- Creates WiFi hotspot
- Hosts file sharing
- Enables local chat
- Powered wirelessly via Qi

!!! danger "Advanced Warning"
    Biocomputing implants are experimental and carry significantly higher risks than passive implants. They should only be considered by experienced biohackers with proper medical support.

---

## Choosing Your Implant

### Decision Matrix

| Need | Recommended Implant |
|------|---------------------|
| Clone access badges | xEM or NExT |
| Share URLs/contact info | xNT or xSIID |
| Visual feedback | xSIID |
| Maximum versatility | NExT |
| Sense EM fields | xG3 |
| Cryptographic security | Spark 2 |

### Questions to Ask

1. **What's my primary use case?**
2. **Do I need visual feedback?**
3. **Which systems do I need to interact with?**
4. **Where will it be placed?**
5. **What's my risk tolerance?**

---

## Installation

### Professional Installation

Always use a professional installer:

- Body modification artists with implant experience
- Medical professionals willing to perform the procedure
- [Dangerous Things Partner Map](https://dangerousthings.com/partners/)

### Procedure Overview

1. **Consultation** — Discuss placement and expectations
2. **Preparation** — Sterilization of area
3. **Anesthesia** — Local numbing (optional but recommended)
4. **Insertion** — Using proper implant injector or scalpel
5. **Closure** — Sterile bandaging
6. **Aftercare** — Following proper healing protocols

### Aftercare

- Keep the area clean and dry
- Watch for signs of infection
- Allow 2-4 weeks for full healing
- Avoid strenuous activity with the implant area

---

## Compatibility

### Reader Compatibility

| Implant Type | Compatible Readers |
|--------------|-------------------|
| 125kHz RFID | Proxmark3, HID readers, EM readers |
| 13.56MHz NFC | Smartphones, ACR122U, PN532 |
| Dual-frequency | All of the above |

### Smartphone Compatibility

Most modern smartphones can read HF/NFC implants:

- ✅ Android (most devices with NFC)
- ✅ iPhone (7 and newer, with limitations)
- ❌ Older phones without NFC

---

## Safety Considerations

### MRI Compatibility

| Implant Type | MRI Safe? |
|--------------|-----------|
| Glass-encased RFID | ⚠️ Conditional |
| Magnetic implants | ❌ NO |
| Biocomputers | ❌ NO |

!!! danger "MRI Warning"
    Always inform medical staff about ALL implants before any imaging procedure. Some implants can heat up, move, or be damaged by MRI machines.

### Longevity

Most well-installed implants can last indefinitely:

- Glass encapsulation provides excellent protection
- No battery = no degradation over time
- Biocompatible coatings prevent rejection

---

## Further Reading

- [Getting Started](getting-started.md)
- [Tools & Equipment](tools-and-equipment.md)
- [Safety & Legal](safety-and-legal.md)
- [Glossary](glossary.md)
