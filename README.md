# SonghubRemoteESP32V2.0

ESP32 Firmware for Songhub Remote.

---

## 🔑 License & Activation

This firmware requires an activation key to unlock its full functionality. 

### How Activation Works:
1. Upon first boot, the ESP32 will create a Wi-Fi hotspot.
2. Open the web interface by typing the IP address into your browser. (192.168.4.1)
3. The screen will display a **Hardware ID (HWID)** or a specific code. OR (Click activate)
4. You must provide this HWID to the developer to generate a unique activation key.
5. Enter the activation key into the web interface. Once verified, the device will unlock and the Bluetooth keypad functions will become active.

---

## 🔌 Hardware Wiring Guide (4x4 Keypad)

To use this firmware, connect your standard 4x4 Matrix Keypad to the ESP32-WROOM-32 as shown below. 

*Note: The `Keypad.h` library uses the ESP32's internal pull-up resistors, so **no external resistors are required**.*

| Keypad Pin | ESP32 Pin | Keypad Row/Column |
| :--- | :--- | :--- |
| **R1** (Row 1) | **GPIO 13** | `1, 2, 3, A` |
| **R2** (Row 2) | **GPIO 12** | `4, 5, 6, B` |
| **R3** (Row 3) | **GPIO 14** | `7, 8, 9, C` |
| **R4** (Row 4) | **GPIO 27** | `*, 0, #, D` |
| **C1** (Col 1) | **GPIO 26** | `1, 4, 7, *` |
| **C2** (Col 2) | **GPIO 25** | `2, 5, 8, 0` |
| **C3** (Col 3) | **GPIO 33** | `3, 6, 9, #` |
| **C4** (Col 4) | **GPIO 32** | `A, B, C, D` |

### 💡 Important Wiring Tips:
1. **Do Not Connect Power:** The keypad has 8 pins (R1-R4, C1-C4). **Do not** connect any of these wires to `3.3V` or `GND`.
2. **Pin Orientation:** Looking at the front of the keypad, the leftmost pin on the header is usually `R1`, and the rightmost is `C4`.
3. **Testing:** Once flashed, connect to the "Videoke Remote" Wi-Fi and open the web interface. Press a physical button on the keypad. If the web interface displays the wrong number (e.g., pressing '5' shows '8'), it means your Row or Column wires are swapped. Simply swap the wires to fix it.

### Getting an Activation Key:
To purchase or request an activation key, please contact me directly on Facebook:
* **Developer:** AldenM
* **Facebook Page:** [Click here to message me on Facebook](https://www.facebook.com/profile.php?id=61596062224543)

---

---

## 📖 How to Use the Songhub Remote

This remote acts as a Bluetooth keyboard for your TV, PC, or Smartphone, and is controlled via the built-in Wi-Fi Web Interface.

### 1. How to Connect (TV, PC, or Mobile)
1. **Power the ESP32:** Plug the ESP32 into a power source (like a phone charger or TV USB port).
2. **Connect to Wi-Fi:** On your phone or PC, go to Wi-Fi settings and connect to the network named **"Videoke Remote"** (or "Videoke Remote (Unactivated)").
3. **Open the Remote:** Open a web browser (Chrome, Safari, etc.) and type `192.168.4.1` in the address bar. You will see the Remote UI.
4. **Pair via Bluetooth:** 
   * Turn on Bluetooth on your Smart TV, PC, or Phone. 
   * Search for new devices and pair with **"Videoke Remote"**.
   * Once connected, the status dot on the web interface will turn **Green** (Bluetooth Connected).

---

### 2. Button Functions (Web UI & Physical Keypad)

Here is what each button does when connected to your device:

#### 🔢 Number Keys (0 - 9)
*   **Function:** Types the numbers directly into your TV/PC.
*   **Use Case:** Use this to input the **Song Code** on your Videoke system. The web screen will display the 6-digit code you are typing. 

#### 🅰️ 'A' Button (Melody)
*   **Use Case:** Used to toggle the **Melody/Vocal Guide** on/off in most Videoke software.

#### 🅱️ 'B' Button (Reserve/Enter)
*   **Use Case:** Used to **Reserve** a song after typing the code, or to confirm a selection.

#### ©️ 'C' Button (Clear All)
*   **Use Case:** Use this if you typed the wrong song code and want to start over.

#### 🇩 'D' Button (Background)
*   **Use Case:** Used to toggle the **Background Video (BGV)** on or off.

#### ⭐ '*' Button (Stop)
*   **Use Case:** Stops the current song playing.

#### #️⃣ '#' Button (Play/Pause)
*   **Use Case:** Pauses or plays the current song.

  

## ⚠️ Disclaimer
*   **No Unauthorized Distribution:** The compiled `.bin` file provided in this repository is for personal use only. Do not sell, redistribute, or claim this firmware as your own.
*   **Hardware Risk:** Flash this firmware at your own risk. Ensure you are using the correct ESP32 board (ESP32-WROOM-32) and wiring the keypad correctly. The developer is not responsible for bricked devices or damaged hardware.
*   **Reverse Engineering:** Attempting to bypass the activation system, extract the source code, or modify the compiled binary is strictly prohibited.
