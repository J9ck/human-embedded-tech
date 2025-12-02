# 🔨 DIY Biohacking Projects

A collection of practical projects you can build with your implants, from simple automations to advanced hardware builds.

---

## Table of Contents

- [Beginner Projects](#beginner-projects)
- [Intermediate Projects](#intermediate-projects)
- [Advanced Projects](#advanced-projects)
- [Smart Home Integration](#smart-home-integration)
- [Security Projects](#security-projects)
- [Wearable Projects](#wearable-projects)

---

## Beginner Projects

### Project 1: Digital Business Card

Share your contact info with a tap using your NFC implant.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     DIGITAL BUSINESS CARD                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐ Easy                                                        │
│   TIME: 5 minutes                                                            │
│   IMPLANTS: xNT, NExT (HF side), xSIID, any NFC                             │
│   TOOLS: Smartphone with NFC, NFC Tools app                                 │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   WHAT YOU'LL DO:                                                            │
│   Write a vCard (contact info) to your implant. When someone taps           │
│   their phone to your hand, your contact info automatically appears.        │
│                                                                              │
│   STEPS:                                                                     │
│                                                                              │
│   1. Open NFC Tools app on your Android phone                               │
│                                                                              │
│   2. Go to WRITE tab                                                        │
│                                                                              │
│   3. Click "Add a record" → "Contact"                                       │
│                                                                              │
│   4. Fill in your info:                                                     │
│      • Name: Your Name                                                       │
│      • Phone: +1-555-123-4567                                               │
│      • Email: you@email.com                                                 │
│      • Company: Your Company                                                │
│      • Title: Your Title                                                    │
│      • Website: https://yoursite.com                                        │
│                                                                              │
│   5. Click "OK" to save the record                                          │
│                                                                              │
│   6. Click "Write" at the bottom                                            │
│                                                                              │
│   7. Hold your implant to your phone's NFC antenna                          │
│                                                                              │
│   8. Wait for confirmation "Write successful"                               │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   USAGE:                                                                     │
│   When someone holds their NFC-enabled phone to your implant,               │
│   they'll get a prompt to save your contact!                                │
│                                                                              │
│   TIPS:                                                                      │
│   • Test with your own phone first                                          │
│   • Keep info concise - limited memory                                      │
│   • vCard takes more space than a simple URL                                │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Project 2: Personal Portfolio Link

Link your implant to your online portfolio or resume.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     PORTFOLIO/RESUME LINK                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐ Easy                                                        │
│   TIME: 2 minutes                                                            │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Smartphone, NFC Tools app                                          │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEPS:                                                                     │
│                                                                              │
│   1. Open NFC Tools → WRITE                                                 │
│                                                                              │
│   2. "Add a record" → "URL/URI"                                             │
│                                                                              │
│   3. Enter your URL:                                                        │
│      https://yourportfolio.com                                              │
│      OR                                                                      │
│      https://linkedin.com/in/yourprofile                                    │
│                                                                              │
│   4. Write to implant                                                       │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   PRO TIP: Use a link shortener or redirect service so you can              │
│   change the destination without rewriting your implant.                    │
│                                                                              │
│   Example services:                                                          │
│   • Linktree (free) - linktree.com                                          │
│   • bit.ly - Custom short links                                              │
│   • Your own domain with redirect                                            │
│                                                                              │
│   MEMORY USAGE:                                                              │
│   • Short URLs use less memory                                               │
│   • NTAG216 has 888 bytes - plenty for URLs                                 │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Project 3: WiFi Password Sharing

Share your WiFi credentials with a tap.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     WIFI PASSWORD SHARING                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐ Easy                                                        │
│   TIME: 3 minutes                                                            │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Smartphone, NFC Tools app                                          │
│                                                                              │
│   ⚠️ SECURITY NOTE: Anyone who scans your implant will see your            │
│   WiFi password. Only do this for guest networks, not your main one!        │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEPS:                                                                     │
│                                                                              │
│   1. Open NFC Tools → WRITE                                                 │
│                                                                              │
│   2. "Add a record" → "Wi-Fi network"                                       │
│                                                                              │
│   3. Enter your network details:                                            │
│      • SSID: Your_Network_Name                                              │
│      • Authentication: WPA/WPA2                                              │
│      • Password: YourPassword123                                            │
│                                                                              │
│   4. Write to implant                                                       │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   WHEN SCANNED:                                                              │
│   Android phones will auto-connect to the WiFi network.                     │
│   iPhones will prompt to join.                                              │
│                                                                              │
│   BETTER OPTION:                                                             │
│   Have a second implant (or use a different finger position)                │
│   dedicated to guest WiFi sharing.                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Intermediate Projects

### Project 4: Phone Unlock with NFC (Android)

Use your implant to unlock your Android phone.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     ANDROID PHONE UNLOCK                                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐⭐ Medium                                                    │
│   TIME: 10 minutes                                                           │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Android phone, Smart Lock feature                                  │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   METHOD 1: Smart Lock (Built-in)                                           │
│   Note: Google is phasing this out - may not work on newer phones           │
│                                                                              │
│   1. Go to Settings → Security → Smart Lock                                 │
│                                                                              │
│   2. Select "Trusted devices"                                               │
│                                                                              │
│   3. Choose "NFC"                                                           │
│                                                                              │
│   4. Tap your implant to register it                                        │
│                                                                              │
│   5. Name your implant ("My Hand Implant")                                  │
│                                                                              │
│   Now your phone stays unlocked when your implant is nearby!                │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   METHOD 2: Tasker Automation (More Reliable)                               │
│                                                                              │
│   Requirements:                                                              │
│   • Tasker app ($3.49)                                                       │
│   • AutoInput plugin (may need)                                              │
│                                                                              │
│   Profile Setup:                                                             │
│   1. New Profile → Event → Net → NFC Tag                                    │
│   2. Scan your implant to register its UID                                  │
│   3. Link to task: Input → Unlock Screen                                    │
│                                                                              │
│   (See Tasker documentation for full setup)                                 │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   ⚠️ SECURITY WARNING:                                                      │
│   Using NFC for phone unlock is less secure than PIN/biometrics.            │
│   Anyone with an NFC reader could potentially copy your UID.                │
│   Use for convenience on non-critical devices only.                         │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Project 5: Access Card Cloning (125kHz)

Clone your gym/work access card to your xEM or NExT implant.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     ACCESS CARD CLONING                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐⭐⭐ Medium-Hard                                             │
│   TIME: 30-60 minutes (first time)                                          │
│   IMPLANTS: xEM, NExT (LF side)                                             │
│   TOOLS: Proxmark3                                                           │
│                                                                              │
│   ⚠️ LEGAL NOTE: Only clone cards you own or have explicit permission      │
│   to clone. Cloning work badges without authorization may be illegal.       │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 1: Identify Your Card Type                                           │
│                                                                              │
│   Place your card on the Proxmark3 LF antenna:                              │
│                                                                              │
│   pm3> lf search                                                            │
│                                                                              │
│   Common results:                                                            │
│   • "EM410x" - Simple, easy to clone                                        │
│   • "HID Prox" - Common for work badges                                     │
│   • "Indala" - Another access card type                                     │
│   • "AWID" - Less common                                                    │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 2: Read Your Card                                                    │
│                                                                              │
│   For EM410x:                                                                │
│   pm3> lf em 410x reader                                                    │
│                                                                              │
│   Output example:                                                            │
│   EM 410x ID 1A2B3C4D5E                                                     │
│   └──────────┬─────────┘                                                    │
│              └── This is your card ID (write this down!)                    │
│                                                                              │
│   For HID:                                                                   │
│   pm3> lf hid reader                                                        │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 3: Write to Implant                                                  │
│                                                                              │
│   Position your implant on the LF antenna:                                  │
│                                                                              │
│   For EM410x to xEM/NExT:                                                   │
│   pm3> lf em 410x clone --id 1A2B3C4D5E                                    │
│                                                                              │
│   For HID to xEM/NExT:                                                      │
│   pm3> lf hid clone -r 2004XXXXXX                                          │
│   (Use the raw value from 'lf hid reader')                                  │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 4: Verify                                                            │
│                                                                              │
│   Read your implant back:                                                    │
│   pm3> lf search                                                            │
│                                                                              │
│   Should show same ID as your original card.                                │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   TROUBLESHOOTING:                                                           │
│                                                                              │
│   "Can't find tag"                                                          │
│   • Move implant slowly across antenna                                      │
│   • Try perpendicular orientation                                           │
│   • Wait longer between attempts                                            │
│                                                                              │
│   "Write failed"                                                            │
│   • Ensure proper antenna contact                                           │
│   • Check implant isn't password protected                                  │
│   • Try: lf t55xx wipe first, then re-clone                                │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Project 6: Arduino Door Lock

Build an NFC-activated door lock.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     ARDUINO NFC DOOR LOCK                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐⭐⭐ Medium-Hard                                             │
│   TIME: 2-4 hours                                                            │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Arduino, PN532, Servo/Electric Strike, Relay                       │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   COMPONENTS:                                                                │
│   • Arduino Uno/Nano - $10-25                                               │
│   • PN532 NFC module - $10-20                                               │
│   • Servo motor OR Electric strike - $10-50                                 │
│   • Relay module (if using electric strike) - $5                            │
│   • LED (green/red) - $1                                                     │
│   • Buzzer - $1                                                              │
│   • Power supply - $10                                                       │
│   • Enclosure - $10                                                          │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   WIRING DIAGRAM:                                                            │
│                                                                              │
│         PN532                Arduino              Lock                       │
│        ┌─────┐              ┌──────┐            ┌──────┐                    │
│        │ VCC ├──────────────┤ 5V   │            │      │                    │
│        │ GND ├──────────────┤ GND  ├────────────┤ GND  │                    │
│        │ SDA ├──────────────┤ A4   │            │      │                    │
│        │ SCL ├──────────────┤ A5   │    RELAY   │      │                    │
│        └─────┘              │      │   ┌────┐   │      │                    │
│                             │ D9 ──┼───┤ IN │───┤ CTRL │                    │
│                             │      │   └────┘   │      │                    │
│                             │ D7 ──┼──[GREEN LED]       │                    │
│                             │ D6 ──┼──[RED LED]         │                    │
│                             │ D5 ──┼──[BUZZER]          │                    │
│                             └──────┘            └──────┘                    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Arduino Code:**

```cpp
// NFC Door Lock - Complete Code
// Compatible with xNT, NExT, xSIID implants

#include <Wire.h>
#include <Adafruit_PN532.h>

#define LOCK_PIN 9
#define GREEN_LED 7
#define RED_LED 6
#define BUZZER 5
#define UNLOCK_DURATION 5000  // 5 seconds

Adafruit_PN532 nfc(-1, -1);  // I2C mode

// Store authorized UIDs here (up to 10)
// Replace with your implant's UID
// ⚠️ SECURITY NOTE: For production use, consider storing UIDs in 
// encrypted EEPROM and implementing proper access management.
// Hardcoded UIDs are suitable for learning/testing only.
uint8_t authorizedUIDs[][7] = {
  {0x04, 0xAB, 0xCD, 0xEF, 0x12, 0x34, 0x56},  // Example UID 1
  {0x04, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66},  // Example UID 2
  // Add more UIDs as needed
};
int numAuthorized = 2;  // Update this when adding UIDs

void setup() {
  Serial.begin(115200);
  
  pinMode(LOCK_PIN, OUTPUT);
  pinMode(GREEN_LED, OUTPUT);
  pinMode(RED_LED, OUTPUT);
  pinMode(BUZZER, OUTPUT);
  
  // Start locked
  digitalWrite(LOCK_PIN, LOW);
  digitalWrite(RED_LED, HIGH);
  
  nfc.begin();
  if (!nfc.getFirmwareVersion()) {
    Serial.println("PN532 not found!");
    while(1);
  }
  
  nfc.SAMConfig();
  Serial.println("NFC Door Lock Ready");
}

void loop() {
  uint8_t uid[7];
  uint8_t uidLength;
  
  if (nfc.readPassiveTargetID(PN532_MIFARE_ISO14443A, uid, &uidLength)) {
    Serial.print("Tag detected: ");
    printUID(uid, uidLength);
    
    if (isAuthorized(uid, uidLength)) {
      unlock();
    } else {
      denyAccess();
    }
    
    delay(1000);  // Debounce
  }
}

bool isAuthorized(uint8_t* uid, uint8_t uidLength) {
  for (int i = 0; i < numAuthorized; i++) {
    bool match = true;
    for (int j = 0; j < uidLength; j++) {
      if (uid[j] != authorizedUIDs[i][j]) {
        match = false;
        break;
      }
    }
    if (match) return true;
  }
  return false;
}

void unlock() {
  Serial.println("ACCESS GRANTED");
  
  // Visual/audio feedback
  digitalWrite(GREEN_LED, HIGH);
  digitalWrite(RED_LED, LOW);
  tone(BUZZER, 1000, 100);
  delay(100);
  tone(BUZZER, 1500, 100);
  
  // Unlock
  digitalWrite(LOCK_PIN, HIGH);
  delay(UNLOCK_DURATION);
  
  // Re-lock
  digitalWrite(LOCK_PIN, LOW);
  digitalWrite(GREEN_LED, LOW);
  digitalWrite(RED_LED, HIGH);
}

void denyAccess() {
  Serial.println("ACCESS DENIED");
  
  // Visual/audio feedback
  for (int i = 0; i < 3; i++) {
    digitalWrite(RED_LED, LOW);
    tone(BUZZER, 200, 100);
    delay(150);
    digitalWrite(RED_LED, HIGH);
    delay(150);
  }
}

void printUID(uint8_t* uid, uint8_t length) {
  for (int i = 0; i < length; i++) {
    Serial.print("0x");
    if (uid[i] < 0x10) Serial.print("0");
    Serial.print(uid[i], HEX);
    Serial.print(" ");
  }
  Serial.println();
}
```

---

## Advanced Projects

### Project 7: Raspberry Pi NFC Login System

Set up your computer to login using your implant.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     RASPBERRY PI NFC LOGIN                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐⭐⭐⭐ Hard                                                  │
│   TIME: 2-3 hours                                                            │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Raspberry Pi, ACR122U or PN532, Linux knowledge                    │
│                                                                              │
│   This project uses PAM (Pluggable Authentication Modules) to allow        │
│   NFC-based login to your Linux system.                                     │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 1: Install Dependencies                                               │
│                                                                              │
│   sudo apt update                                                            │
│   sudo apt install libpam-dev libnfc-dev libpcsclite-dev pcscd             │
│   sudo apt install pcsc-tools libnfc-bin                                    │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 2: Install pam_nfc                                                   │
│                                                                              │
│   git clone https://github.com/nfc-tools/pam_nfc.git                        │
│   cd pam_nfc                                                                │
│   ./configure                                                                │
│   make                                                                       │
│   sudo make install                                                          │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 3: Configure Authorized Tags                                         │
│                                                                              │
│   # Get your implant's UID                                                  │
│   nfc-list                                                                   │
│                                                                              │
│   # Create authorized devices file                                          │
│   sudo nano /etc/nfc-auth                                                   │
│                                                                              │
│   # Add your username and UID:                                              │
│   yourusername:04ABCDEF123456                                               │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   STEP 4: Configure PAM                                                     │
│                                                                              │
│   # Edit login configuration                                                │
│   sudo nano /etc/pam.d/common-auth                                          │
│                                                                              │
│   # Add this line at the top:                                               │
│   auth sufficient pam_nfc.so                                                │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   ⚠️ WARNING: Test in a VM first! Misconfiguration can lock you out!       │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Project 8: Home Assistant Integration

Integrate your implant with your smart home.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     HOME ASSISTANT NFC INTEGRATION                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   DIFFICULTY: ⭐⭐⭐ Medium-Hard                                             │
│   TIME: 1-2 hours                                                            │
│   IMPLANTS: Any NFC implant                                                  │
│   TOOLS: Home Assistant, ESP32 + PN532, ESPHome                             │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   HARDWARE SETUP:                                                            │
│                                                                              │
│        ESP32                PN532                                            │
│       ┌─────┐              ┌─────┐                                          │
│       │ 3.3V├──────────────┤ VCC │                                          │
│       │ GND ├──────────────┤ GND │                                          │
│       │ GPIO21 (SDA)───────┤ SDA │                                          │
│       │ GPIO22 (SCL)───────┤ SCL │                                          │
│       └─────┘              └─────┘                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**ESPHome Configuration:**

```yaml
# esphome/nfc-reader.yaml

esphome:
  name: nfc-reader
  platform: ESP32
  board: nodemcu-32s

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

api:
  password: !secret api_password

ota:
  password: !secret ota_password

logger:

i2c:
  sda: GPIO21
  scl: GPIO22

pn532_i2c:
  update_interval: 1s

binary_sensor:
  - platform: pn532
    uid: 04-AB-CD-EF-12-34-56  # Your implant UID
    name: "Jack's Implant"

# Alternative: Send any scanned UID as a tag_scanned event
pn532:
  on_tag:
    then:
      - homeassistant.event:
          event: esphome.nfc_tag
          data:
            uid: !lambda 'return x;'
```

**Home Assistant Automation:**

```yaml
# automations.yaml

automation:
  - alias: "Implant Scanned - Welcome Home"
    trigger:
      platform: state
      entity_id: binary_sensor.jack_s_implant
      to: "on"
    action:
      - service: light.turn_on
        entity_id: light.living_room
      - service: lock.unlock
        entity_id: lock.front_door
      - service: media_player.play_media
        entity_id: media_player.living_room_speaker
        data:
          media_content_id: "Welcome home, Jack"
          media_content_type: "tts"
```

---

## Smart Home Integration

### Compatible Smart Home Platforms

| Platform | NFC Support | Implant Compatibility | Difficulty |
|----------|-------------|----------------------|------------|
| **Home Assistant** | Via ESPHome/MQTT | Excellent | ⭐⭐⭐ |
| **SmartThings** | Limited | Requires bridge | ⭐⭐⭐⭐ |
| **Apple HomeKit** | Via Homebridge | Moderate | ⭐⭐⭐⭐ |
| **Google Home** | Via HA integration | Moderate | ⭐⭐⭐ |
| **Hubitat** | Via custom driver | Good | ⭐⭐⭐ |

### Ideas for Smart Home Automation

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     SMART HOME AUTOMATION IDEAS                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ENTRY/EXIT:                                                                │
│   • Scan to unlock door                                                      │
│   • Turn on lights when entering                                            │
│   • Disarm security system                                                  │
│   • Start "Welcome Home" routine                                            │
│                                                                              │
│   ROOM-SPECIFIC:                                                             │
│   • Scan in bedroom = Sleep mode (lights off, thermostat down)             │
│   • Scan in office = Work mode (lights on, music starts)                   │
│   • Scan in kitchen = Start cooking timer, play recipe                      │
│                                                                              │
│   CONVENIENCE:                                                               │
│   • Scan near TV = Turn on and open Netflix                                 │
│   • Scan at desk = Wake up computer                                         │
│   • Scan at coffee maker = Start brewing                                    │
│                                                                              │
│   SECURITY:                                                                  │
│   • Scan to arm/disarm alarm                                                │
│   • Scan to lock all doors                                                  │
│   • Emergency scan = Alert contacts                                         │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Security Projects

### Two-Factor Authentication Concept

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     2FA WITH IMPLANT                                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   CONCEPT: Use your implant as the "something you have" factor              │
│                                                                              │
│   Traditional 2FA:                                                           │
│   Password (know) + Phone code (have) = Access                              │
│                                                                              │
│   Implant 2FA:                                                               │
│   Password (know) + Implant scan (have) = Access                            │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   ⚠️ IMPORTANT SECURITY NOTES:                                              │
│                                                                              │
│   Basic NFC implants (xNT, etc.) use STATIC UIDs.                          │
│   This is NOT true cryptographic 2FA because:                               │
│   • UIDs can be read and cloned                                             │
│   • No challenge-response authentication                                    │
│   • Physical proximity still required (mitigates some risk)                │
│                                                                              │
│   FOR TRUE CRYPTOGRAPHIC 2FA:                                               │
│   • Use VivoKey Spark - has actual crypto capabilities                     │
│   • Supports FIDO2/WebAuthn standards                                       │
│   • Cannot be cloned                                                        │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   SIMPLE 2FA IMPLEMENTATION (UID-based, for non-critical systems):         │
│                                                                              │
│   1. Set up NFC reader at login workstation                                 │
│   2. Application requires:                                                   │
│      a. Username/password                                                   │
│      b. NFC scan within 30 seconds                                          │
│   3. Match UID against database                                             │
│   4. Grant access if both factors valid                                     │
│                                                                              │
│   Use case: Office door that requires badge AND implant                     │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Wearable Projects

### NFC Ring Alternative

Before getting an implant, test with an NFC ring.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     NFC RING TESTING                                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   WHY TEST WITH A RING FIRST:                                               │
│   • Same technology as implants                                              │
│   • Test reader compatibility                                                │
│   • Learn NFC before permanent implant                                      │
│   • Find ideal use cases                                                    │
│   • Non-permanent commitment                                                │
│                                                                              │
│   RECOMMENDED NFC RINGS:                                                     │
│                                                                              │
│   • McLear Ring ($50-90)                                                    │
│     - Payment enabled (in some regions)                                     │
│     - High quality, comfortable                                             │
│                                                                              │
│   • CXJ NFC Ring ($10-20)                                                   │
│     - Budget option                                                          │
│     - NTAG216 chip (same as xNT)                                            │
│     - Great for testing                                                      │
│                                                                              │
│   • VivoKey Apex Ring ($150+)                                               │
│     - Cryptographic capabilities                                             │
│     - Test before Apex implant                                              │
│                                                                              │
│   ─────────────────────────────────────────────────────────────────────     │
│                                                                              │
│   TESTING CHECKLIST:                                                         │
│   □ Does it work with your phone?                                           │
│   □ Does it work with target access readers?                                │
│   □ Is the read range acceptable?                                           │
│   □ Does the antenna orientation matter?                                    │
│   □ Is the form factor practical for daily use?                             │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Project Ideas Quick Reference

| Project | Difficulty | Implant Type | Time |
|---------|------------|--------------|------|
| Digital Business Card | ⭐ | Any NFC | 5 min |
| Portfolio Link | ⭐ | Any NFC | 2 min |
| WiFi Sharing | ⭐ | Any NFC | 3 min |
| Phone Unlock | ⭐⭐ | Any NFC | 10 min |
| Access Card Clone | ⭐⭐⭐ | xEM/NExT | 30-60 min |
| Arduino Door Lock | ⭐⭐⭐ | Any NFC | 2-4 hrs |
| Pi NFC Login | ⭐⭐⭐⭐ | Any NFC | 2-3 hrs |
| Home Assistant | ⭐⭐⭐ | Any NFC | 1-2 hrs |
| Computer Login | ⭐⭐⭐⭐ | Any NFC | 2-3 hrs |
| Custom 2FA | ⭐⭐⭐⭐⭐ | Spark/Apex | 4+ hrs |

---

## Next Steps

| Topic | Link | Description |
|-------|------|-------------|
| **Tools Guide** | [Tools & Equipment](tools-and-equipment.md) | Get the right tools |
| **Safety** | [Safety & Legal](safety-and-legal.md) | Stay safe |
| **Implants** | [Implants Guide](implants-guide.md) | Learn about implants |
| **Glossary** | [Glossary](glossary.md) | Technical terms |

---

<p align="center">
  <a href="tools-and-equipment.md">← Tools & Equipment</a> •
  <a href="../README.md">Wiki Home</a> •
  <a href="safety-and-legal.md">Safety & Legal →</a>
</p>
