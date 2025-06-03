
# 🚫 BlueJammer – **For Educational Use Only**

> **Disclaimer:** Jamming communication signals is illegal in many countries. This project is intended strictly for educational and research purposes. Use responsibly and comply with all local laws and regulations.

---

## 📦 Required Hardware

- **ESP32-WROOM**  

- **NRF24L01+ PA/LNA (2.4 GHz)**  

- **Switch** (Optional)  
  (Can be used to change between modes of jamming)

- **Electrolytic Capacitor (10µF – 100µF)**  
  (Used to stabilize the power supply to the NRF24 module)

---

## 🧰 Driver Installation

> ⚠️ **Important:** Make sure your computer has the correct **USB-to-Serial drivers** installed to communicate with the ESP32.

- Many ESP32 boards use the **Silicon Labs CP210x** USB-to-UART bridge.
- If your board isn't detected by the Arduino IDE or other tools, download the CP210x drivers from:  
  👉 [https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)

---

## 📚 Required Libraries

- **ESP32 Board Support Package**  
  Install via the Arduino Board Manager:
  - Open Arduino IDE → Preferences  
  - Add this URL to **Additional Board Manager URLs**:  
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
  - Go to **Tools → Board → Board Manager**, search for **esp32**, and install “esp32 by Espressif Systems”

- [`RF24`](https://github.com/nRF24/RF24) by TMRh20 - For communication with the NRF24L01 module.

- [`ezButton`](https://arduinogetstarted.com/tutorials/arduino-button-library)  by ArduinoGetStarted.com - Simplifies switch/button handling logic.

---

## 🔌 NRF24L01 Pin Connections

> You can choose either HSPI or VSPI for SPI communication on the ESP32.

### HSPI Configuration:
- `SCK`  → GPIO **14**  
- `MISO` → GPIO **12**  
- `MOSI` → GPIO **13**  
- `CSN`  → GPIO **15**  
- `CE`   → GPIO **16**

### VSPI Configuration:
- `SCK`  → GPIO **18**  
- `MISO` → GPIO **19**  
- `MOSI` → GPIO **23**  
- `CSN`  → GPIO **21**  
- `CE`   → GPIO **22**

---

## 📡 Channel Ranges (2.4GHz Spectrum Reference)

- **Bluetooth**: Channels **0–78**
- **BLE (Bluetooth Low Energy)**: Channels **0–39**
- **Wi-Fi (2.4GHz)**: Channels **1–14**
- **Drones (2.4GHz band)**: Channels **1–125** (May vary)

> Note: This tool operates in the 2.4 GHz ISM band, which overlaps with many consumer wireless technologies.

---

## 🔧 Setup Instructions

1. Install CP210x or appropriate USB drivers (see above).
2. Connect the hardware as per the pin configuration above.
3. Install the required libraries in your Arduino IDE.
4. Select the correct ESP32 board and port.
5. Upload the code from this repository to your ESP32 board.
6. Power the system using a stable 3.3V supply (especially for the NRF24L01+ PA/LNA).
7. Use with caution and responsibility.

---

## ⚠️ Legal Notice

This project is intended **only** for testing and understanding the behavior of wireless communications under interference. Do not use this for malicious purposes.

> **You are solely responsible for using this software and hardware in a legal and ethical manner.**
