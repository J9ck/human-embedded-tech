# Tools & Equipment

This guide covers the essential tools and equipment used in human embedded technology, from reading and writing implants to experimentation and development.

---

## Essential Hardware

### RFID/NFC Readers & Writers

#### Proxmark3

The gold standard for RFID/NFC work.

| Variant | Price Range | Best For |
|---------|-------------|----------|
| **Proxmark3 Easy** | ~$50-80 | Beginners, basic operations |
| **Proxmark3 RDV4** | ~$300+ | Advanced work, better antennas |

**Capabilities:**

- Read, write, clone, and emulate RFID/NFC tags
- Support for LF (125kHz) and HF (13.56MHz)
- Sniff communications between readers and cards
- Analyze unknown card types

**Firmware:**

- **Iceman Firmware** — Recommended community firmware with more features
- Regular updates and active development

**Basic Commands:**

```bash
# Read a low-frequency tag
lf search

# Read a high-frequency tag
hf search

# Clone an EM4100 badge to T5577
lf em 410x clone --id <ID>

# Read NTAG info
hf mfu info
```

---

#### ACR122U

A budget-friendly USB NFC reader/writer.

| Feature | Specification |
|---------|---------------|
| **Frequency** | 13.56MHz only |
| **Interface** | USB |
| **Price** | ~$30-50 |

**Best For:**

- Reading/writing NFC tags
- Simple implant interaction
- Budget setups

---

#### PN532 Module

An Arduino-compatible NFC module.

| Feature | Specification |
|---------|---------------|
| **Frequency** | 13.56MHz |
| **Interface** | I2C, SPI, UART |
| **Price** | ~$10-20 |

**Best For:**

- DIY projects
- Arduino integration
- Custom reader builds

---

### Smartphones

Your phone can be a powerful NFC tool:

#### Android

- **NFC Tools** — Read/write NFC tags
- **TagWriter** — Write NDEF data
- **NFC TagInfo** — Detailed tag analysis

#### iPhone

- Built-in NFC reading (iOS 11+)
- **NFC Tools** app for basic operations
- More limited than Android for writing

---

## Development Tools

### Arduino Ecosystem

| Component | Purpose | Price |
|-----------|---------|-------|
| **Arduino Uno/Nano** | Microcontroller base | ~$20-30 |
| **RC522 Module** | 13.56MHz RFID | ~$5-10 |
| **PN532 Module** | NFC reader/writer | ~$10-20 |
| **RDM6300** | 125kHz RFID reader | ~$5-10 |

**Example Project: NFC Reader**

```cpp
#include <SPI.h>
#include <MFRC522.h>

#define RST_PIN 9
#define SS_PIN 10

MFRC522 mfrc522(SS_PIN, RST_PIN);

void setup() {
  Serial.begin(9600);
  SPI.begin();
  mfrc522.PCD_Init();
  Serial.println("Scan an NFC tag...");
}

void loop() {
  if (!mfrc522.PICC_IsNewCardPresent()) return;
  if (!mfrc522.PICC_ReadCardSerial()) return;

  Serial.print("UID: ");
  for (byte i = 0; i < mfrc522.uid.size; i++) {
    Serial.print(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " ");
    Serial.print(mfrc522.uid.uidByte[i], HEX);
  }
  Serial.println();
}
```

---

### Raspberry Pi

Perfect for more complex projects:

| Model | Best For |
|-------|----------|
| **Pi Zero W** | Compact projects, PegLeg |
| **Pi 4** | Development, testing |
| **Pi Pico** | Microcontroller applications |

---

## Software Tools

### Desktop Applications

| Software | Platform | Purpose |
|----------|----------|---------|
| **Proxmark3 Client** | All | Interface with Proxmark |
| **libnfc** | Linux/Mac | Open-source NFC library |
| **NFC-Tools** | Windows | GUI for NFC operations |

### Mobile Apps

| App | Platform | Features |
|-----|----------|----------|
| **NFC Tools** | Android/iOS | Read/write/emulate |
| **TagWriter** | Android | Write NDEF records |
| **NXP TagInfo** | Android | Detailed chip info |

### Libraries & SDKs

| Library | Language | Purpose |
|---------|----------|---------|
| **libnfc** | C | Low-level NFC access |
| **nfcpy** | Python | NFC communication |
| **node-nfc** | JavaScript | Node.js NFC bindings |

---

## Safety Equipment

### For Installation Environments

| Item | Purpose |
|------|---------|
| **Autoclave/Sterilizer** | Sterilize equipment |
| **Sterile gloves** | Prevent contamination |
| **Antiseptic solution** | Clean installation site |
| **Sterile bandages** | Post-procedure care |
| **Sharps container** | Safe disposal |

---

## Recommended Starter Kits

### Budget Kit (~$100)

| Item | Est. Cost |
|------|-----------|
| Proxmark3 Easy | $60 |
| NFC stickers (practice) | $10 |
| NFC Tools app | Free |
| USB extension cable | $5 |

### Intermediate Kit (~$300)

| Item | Est. Cost |
|------|-----------|
| Proxmark3 Easy | $60 |
| ACR122U | $40 |
| Arduino Nano | $20 |
| PN532 + RC522 modules | $20 |
| Test implants/tags | $50 |
| Accessories & cables | $30 |

### Advanced Kit (~$500+)

| Item | Est. Cost |
|------|-----------|
| Proxmark3 RDV4 | $300 |
| ACR122U | $40 |
| Raspberry Pi 4 Kit | $80 |
| Multiple reader modules | $50 |
| Development components | $50+ |

---

## Suppliers

### Implants & Kits

| Supplier | Specialization |
|----------|----------------|
| [Dangerous Things](https://dangerousthings.com) | Implants, kits, accessories |
| [KSEC Solutions](https://www.ksec.co.uk/) | Proxmark, security tools |
| [Lab401](https://lab401.com/) | Security research tools |

### Electronics

| Supplier | Notes |
|----------|-------|
| [Adafruit](https://adafruit.com) | Arduino, components |
| [SparkFun](https://sparkfun.com) | Development boards |
| [AliExpress](https://aliexpress.com) | Budget components |
| [Amazon](https://amazon.com) | General electronics |

---

## Tool Maintenance

### Proxmark3 Care

- Keep firmware updated
- Store with antenna protection
- Clean contacts periodically
- Use quality USB cables

### Reader Module Care

- Handle with ESD precautions
- Keep antenna coils undamaged
- Store in anti-static bags

---

## Further Reading

- [Getting Started](getting-started.md)
- [Implants Guide](implants-guide.md)
- [DIY Projects](diy-projects.md)
- [Resources](resources.md)
