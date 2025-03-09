# 🎮 SB Keyboard to Macro Keyboard Converter 🎛️  

## 📌 Overview  
This project uses an **Arduino Leonardo** (or compatible board) with a **USB Host Shield** to convert a standard **USB keyboard** into a **macro keyboard**.  
The Arduino reads key presses from the external keyboard and sends specific **commands, shortcuts, or macros** to the computer.  

## 🔥 Features  
✅ **USB Keyboard Input** – Connects an external keyboard via the USB Host Shield.  
✅ **Macro Execution** – Sends custom key combinations instead of default key presses.  
✅ **Num Lock Indicator** – Uses an LED to show the Num Lock state.  
✅ **Custom Key Mappings** – Supports function keys and macros (e.g., `Ctrl + C`, `Ctrl + V`).  
✅ **Multi-key Support** – Handles modifiers like **Shift, Ctrl, and Alt**.  

## 🛠️ Hardware Used  

The current setup uses the following components:  
- 🔹 **Arduino Leonardo (Compatible Board)** – [Robocraze Leonardo R3 Board](https://robocraze.com/products/leonardo-r3-board-compatible-with-arduino)  
- 🔹 **USB Host Shield** – [Robocraze USB Host Shield](https://robocraze.com/products/uno-usb-host-shield-for-arduino)  

💡 *These are the best purchase options I found and personally bought. However, please do your own research before purchasing.*  

⚠️ **Disclaimer:**  
I am **not responsible** for any **fraud, hardware damage**, or issues with your **computer, microcontroller, or HID device**. Proceed at your own risk.  

## 🚀 Installation  

### 1️⃣ Connect the Hardware  
🔌 Attach the **USB Host Shield** to the **Arduino Leonardo**.  
⌨️ Connect the **USB keyboard** to the **USB Host Shield**.  
💡 Connect an **LED to pin 12** (optional, for Num Lock status).  

### 2️⃣ Upload the Code  
🖥️ Open the provided `.ino` file in the **Arduino IDE**.  
📍 Select **Board**: `Arduino Leonardo`.  
🔍 Select the correct **Port**.  
⬆️ Click **Upload**.  

## ⚙️ How It Works  
🖥️ The **Arduino Leonardo** acts as a USB Host using the `USBHost` library.  
🕹️ When a key is pressed on the external keyboard:  
- 🔍 The Arduino **detects the key**.  
- 🎭 If it is a **macro key**, the Arduino sends a **predefined macro**.  
- 💬 Otherwise, it sends the **normal key press** to the computer.  
- 💡 The **Num Lock key** toggles an **LED on pin 12**.  
- 🎯 **Special keys execute additional functions:**  
  - 🔄 `Ctrl + C` (Copy) and `Ctrl + V` (Paste) are automatically mapped.  
  - ⏬ `Page Down (F13)` and ⏭️ `End (F13)` execute additional functions.  

## ⌨️ Example Key Mappings  

| 🔢 Key        | 🎯 Action                          |
|--------------|--------------------------------|
| 🅲 `C`       | `Ctrl + C` (Copy)              |
| 🆅 `V`       | `Ctrl + V` (Paste)             |
| 🔢 `Num Lock` | Toggles LED and Num Lock state |
| ⏬ `Page Down` | Sends `F13 + Page Down`        |
| ⏭️ `End`      | Sends `F13 + End`              |
| ❌ `Esc`      | Sends Escape                   |
| `~`         | Sends `~` character            |

## ⚠️ Important Notes  
🛑 **Hardcoded Macros:**  
The macros in this project are **hardcoded into the Arduino**, meaning **any keyboard should work fine**. However, **there is no room for dynamic macro addition** in this setup.  

### 🔄 Future Expansion Ideas  
💾 **SD Card + JSON Configuration:**  
- Adding an **SD card reader** would allow users to store macros in a JSON file.  
- This way, macros could be **modified dynamically** without reprogramming the Arduino.  

🖥️ **QMK Firmware on Pro Micro or Raspberry Pi Pico:**  
- Switching to **QMK firmware** on a **Pro Micro** or **Pi Pico** would provide full programmability.  
- Users could dynamically reassign macros and key bindings via software.  

## 🔧 Troubleshooting  
⚠️ If the **USB Host Shield** does not initialize, check the **Serial Monitor** for errors.  
🛠️ You can modify key mappings inside the **`KeycodeToAscii()`** function.  
⌨️ The project uses **`Keyboard.h`** to send key presses to the PC.  

## ⚠️ Disclaimer  
📝 This code was originally written on **PlatformIO**, so ensure that you include the **necessary header files** if using a different environment.  

## 🎬 Inspiration  
📺 This project was inspired by the video: **[USB Host Keyboard on Arduino](https://youtu.be/GZEoss4XIgc?si=5EGJQVeLKa6sJi1d)**.  

## 📝 License  
📜 This project is **open-source**. Feel free to modify and share!  

---

🚀 **Enjoy your custom macro keyboard!** 🎛️  
