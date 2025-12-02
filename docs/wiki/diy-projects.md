# DIY Projects

Hands-on projects to help you learn and experiment with human embedded technology. Start with external projects before considering any implants.

---

## Beginner Projects

### Project 1: NFC Business Card

**Difficulty:** ⭐ Easy  
**Time:** 15 minutes  
**Cost:** ~$5

Create a digital business card that shares your contact info when tapped.

#### Materials

- NFC sticker or keychain tag (NTAG213/215/216)
- Smartphone with NFC
- NFC Tools app

#### Steps

1. Download NFC Tools on your phone
2. Open the app and tap "Write"
3. Add a record → Contact
4. Fill in your information
5. Tap "Write" and hold the NFC tag to your phone
6. Test by scanning with another phone

#### Variations

- Link to your LinkedIn profile
- Share your portfolio website
- Create a vCard with full contact details

---

### Project 2: URL Redirect Tag

**Difficulty:** ⭐ Easy  
**Time:** 10 minutes  
**Cost:** ~$3

Program an NFC tag to open any URL when scanned.

#### Materials

- NFC tag (NTAG213 minimum)
- Smartphone with NFC

#### Steps

1. Open NFC Tools
2. Write → Add a record → URL
3. Enter your website URL
4. Write to the tag
5. Anyone who scans it will be redirected to your site

#### Ideas

- Personal resume/portfolio
- Wi-Fi setup page
- Social media profile
- YouTube video

---

### Project 3: Arduino NFC Reader

**Difficulty:** ⭐⭐ Moderate  
**Time:** 1-2 hours  
**Cost:** ~$25

Build a basic NFC reader with Arduino.

#### Materials

- Arduino Uno or Nano
- MFRC522 or PN532 module
- Jumper wires
- Breadboard
- USB cable

#### Wiring (MFRC522)

| MFRC522 Pin | Arduino Pin |
|-------------|-------------|
| SDA | 10 |
| SCK | 13 |
| MOSI | 11 |
| MISO | 12 |
| IRQ | Not connected |
| GND | GND |
| RST | 9 |
| 3.3V | 3.3V |

#### Code

```cpp
#include <SPI.h>
#include <MFRC522.h>

#define SS_PIN 10
#define RST_PIN 9

MFRC522 rfid(SS_PIN, RST_PIN);

void setup() {
  Serial.begin(9600);
  SPI.begin();
  rfid.PCD_Init();
  Serial.println("NFC Reader Ready!");
  Serial.println("Scan a tag...");
}

void loop() {
  if (!rfid.PICC_IsNewCardPresent()) return;
  if (!rfid.PICC_ReadCardSerial()) return;

  Serial.print("Tag UID: ");
  for (byte i = 0; i < rfid.uid.size; i++) {
    Serial.print(rfid.uid.uidByte[i] < 0x10 ? "0" : "");
    Serial.print(rfid.uid.uidByte[i], HEX);
    Serial.print(" ");
  }
  Serial.println();

  rfid.PICC_HaltA();
  rfid.PCD_StopCrypto1();
}
```

#### Extensions

- Add an LCD display
- Trigger actions based on specific UIDs
- Log scans to an SD card

---

## Intermediate Projects

### Project 4: NFC Door Lock

**Difficulty:** ⭐⭐⭐ Intermediate  
**Time:** 3-5 hours  
**Cost:** ~$50-80

Create a door lock that opens with NFC tags (or implants).

#### Materials

- Arduino Uno/Nano
- PN532 NFC module
- Electric door strike or magnetic lock
- Relay module
- 12V power supply
- Enclosure

#### Concept

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   NFC Tag   │───▶│  PN532 +    │───▶│   Relay +   │
│  (or hand)  │    │  Arduino    │    │    Lock     │
└─────────────┘    └─────────────┘    └─────────────┘
```

#### Security Considerations

- Store authorized UIDs in EEPROM
- Add timeout after failed attempts
- Consider adding a backup key mechanism
- Use secure enclosure for electronics

#### Code Snippet

```cpp
// Authorized UIDs
byte authorizedUID[][4] = {
  {0xDE, 0xAD, 0xBE, 0xEF},
  {0xCA, 0xFE, 0xBA, 0xBE}
};

bool isAuthorized(byte* uid) {
  for (int i = 0; i < sizeof(authorizedUID)/4; i++) {
    if (memcmp(uid, authorizedUID[i], 4) == 0) {
      return true;
    }
  }
  return false;
}
```

---

### Project 5: Proxmark3 Badge Cloning

**Difficulty:** ⭐⭐⭐ Intermediate  
**Time:** 1-2 hours  
**Cost:** ~$60+ (Proxmark3)

Learn to read and clone RFID badges.

#### Requirements

- Proxmark3 (Easy or RDV4)
- Target RFID badge (that you own/have permission to clone)
- T5577 writable tags

#### Steps

**1. Identify the Card Type**

```bash
# For low-frequency cards
lf search

# For high-frequency cards
hf search
```

**2. Read the Card**

```bash
# Example for EM4100 cards
lf em 410x reader
```

**3. Clone to T5577**

```bash
# Clone EM4100 to T5577
lf em 410x clone --id <card_id>
```

!!! warning "Legal Notice"
    Only clone cards you own or have explicit permission to copy. Cloning access cards without authorization may be illegal.

---

### Project 6: LED Status Indicator

**Difficulty:** ⭐⭐ Moderate  
**Time:** 2-3 hours  
**Cost:** ~$30

Build a visual indicator that lights up when an NFC tag is detected.

#### Materials

- Arduino Nano
- PN532 module
- RGB LED or NeoPixel strip
- Enclosure

#### Features

- Green flash for authorized tags
- Red flash for unknown tags
- Blue pulse while scanning

---

## Advanced Projects

### Project 7: PirateBox Setup

**Difficulty:** ⭐⭐⭐⭐ Advanced  
**Time:** 4-6 hours  
**Cost:** ~$50

Create an offline file-sharing and chat system (foundation for PegLeg concepts).

#### Materials

- Raspberry Pi Zero W
- MicroSD card (8GB+)
- Power supply

#### Overview

This creates a local WiFi network with:

- Anonymous file sharing
- Local chat
- No internet connection required

See the [PegLeg documentation](../pegleg/README.md) for detailed setup instructions.

---

### Project 8: Custom NDEF Application

**Difficulty:** ⭐⭐⭐⭐ Advanced  
**Time:** 5-10 hours  
**Cost:** ~$20

Develop a custom Android app that interacts with NFC implants.

#### Concepts

- Read NDEF messages
- Write custom data
- Trigger app actions
- Authentication flows

#### Technologies

- Android Studio
- NFC API
- NDEF message format

---

### Project 9: Biometric + NFC Two-Factor

**Difficulty:** ⭐⭐⭐⭐⭐ Expert  
**Time:** 10+ hours  
**Cost:** ~$100+

Combine NFC with another factor for enhanced security.

#### Concept

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│  NFC Scan   │ +  │  Fingerprint│ =  │   Access    │
│  Factor 1   │    │   Factor 2  │    │   Granted   │
└─────────────┘    └─────────────┘    └─────────────┘
```

#### Components

- NFC reader module
- Fingerprint sensor
- Arduino or Raspberry Pi
- Secure authentication logic

---

## Project Ideas

Looking for more inspiration? Here are additional project concepts:

### Home Automation

- NFC-triggered lighting scenes
- Smart home control panel
- Presence detection system

### Security

- Two-factor authentication device
- Encrypted message storage
- Secure password manager trigger

### Creative

- Interactive art installation
- NFC-activated music player
- Wearable tech integration

### Utility

- Pet door with NFC collar
- Tool checkout system
- Time tracking for projects

---

## Best Practices

### When Building Projects

1. **Start simple** — Get basics working before adding complexity
2. **Test thoroughly** — Verify at each step
3. **Document everything** — You'll thank yourself later
4. **Consider security** — Especially for access control projects
5. **Share your work** — Help others learn from your experience

### Safety

- Always practice with external tags before considering implants
- Never work with implants directly until you're confident with the technology
- Test all projects extensively before deployment

---

## Resources

### Tutorials & Guides

- [Arduino NFC Tutorial](https://www.arduino.cc/)
- [Proxmark3 Wiki](https://github.com/RfidResearchGroup/proxmark3/wiki)
- [Dangerous Things YouTube](https://www.youtube.com/dangerousthings)

### Community

- [Dangerous Things Forum](https://forum.dangerousthings.com/)
- [Biohack.me](https://biohack.me/)

---

## Further Reading

- [Getting Started](getting-started.md)
- [Tools & Equipment](tools-and-equipment.md)
- [Implants Guide](implants-guide.md)
- [Resources](resources.md)
