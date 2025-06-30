# RFID
In our project we are introducing RFID as a door opener, collects data of the User ID, and opens the door automatically. 
Here's a professional and informative `README.md` for your RFID-based access control system with an Arduino:

---

# 🔐 RFID-Based Access Control with Arduino

This Arduino project uses an **RFID reader** (MFRC522), a **servo motor**, **LED indicators**, and a **buzzer** to create a simple access control system. When an authorized RFID tag is scanned, the servo unlocks a "door", and access is granted with audio-visual feedback. Unauthorized tags trigger an access denied response.

---

## 🧰 Components Used

| Component        | Description               |
| ---------------- | ------------------------- |
| Arduino Uno/Nano | Microcontroller           |
| MFRC522 RFID     | RFID reader module        |
| Servo Motor      | SG90 or similar           |
| LEDs             | 1x Green, 1x Red          |
| Buzzer           | Piezoelectric buzzer      |
| RFID Tags        | Cards/fobs to test access |
| Resistors        | 220Ω (optional for LEDs)  |
| Jumper Wires     | For connections           |
| Breadboard       | For prototyping           |

---

## 🗂️ Files

* `main.ino` – Contains the full Arduino code to control the system.

---

## 📌 How It Works

1. **Initialization**:

   * The RFID reader and servo are initialized.
   * LEDs and buzzer are set to idle.

2. **Card Detection**:

   * The system continuously checks for RFID tags.
   * On detection, it reads and prints the UID.

3. **Access Control**:

   * If the UID matches a pre-authorized value (`83 23 38 BB`), access is granted.
   * Otherwise, access is denied.

4. **Servo Action**:

   * If authorized, the servo rotates to open (180°), waits 5 seconds, then returns to closed position (0°).

---

## ✅ UID Configuration

To authorize a new tag:

1. Open the **Serial Monitor**.
2. Scan the tag and read the UID printed.
3. Replace the line in the code:

```cpp
if (content.substring(1) == "83 23 38 BB")
```

With your tag's UID (uppercase, space-separated).

---

## 🔌 Wiring Diagram

| MFRC522 Pin | Arduino Pin |
| ----------- | ----------- |
| SDA (SS)    | 10          |
| SCK         | 13          |
| MOSI        | 11          |
| MISO        | 12          |
| RST         | 9           |
| 3.3V        | 3.3V        |
| GND         | GND         |

Additional pins:

| Component | Arduino Pin |
| --------- | ----------- |
| Servo     | 3           |
| LED Green | 4           |
| LED Red   | 5           |
| Buzzer    | 2           |

---

## 🔧 Dependencies

Install these libraries in the Arduino IDE:

* [`MFRC522`](https://github.com/miguelbalboa/rfid)
* `Servo.h` (built-in)
* `SPI.h` (built-in)

To install a library:
**Sketch → Include Library → Manage Libraries → Search → Install**

---

## 📝 Notes

* RFID tags must be placed within a few centimeters of the reader.
* Ensure the servo is powered correctly, especially if using external power.
* You can expand this system with EEPROM, LCD, or a real door lock.

---

## 📷 Preview

![Preview of Setup]()

---

## 📜 License

This project is open-source and free to use under the MIT License.

---

