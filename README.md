# EthernetRTL_BW16

Work-in-progress Arduino library for Ai-Thinker **BW16 (RTL8720DN)** + **WIZnet W5500** Ethernet module.

This project demonstrates proof-of-concept compilation and setup for using the W5500 with the BW16 platform, built on the Realtek AmebaD SDK and Arduino core.

---

## ⚙️ Installation

1. Download the ZIP file of this repository from GitHub.
2. Extract the contents into your Arduino libraries directory:
   ```
   Documents/
   └── Arduino/
       └── libraries/
           └── EthernetRTL_BW16/
               ├── library.properties
               ├── src/
               │   ├── EthernetRTL_BW16.h
               │   ├── EthernetRTL_BW16.cpp
               │   └── ioLibrary_Driver/
               │       ├── wizchip_conf.h
               │       ├── w5500.h
               │       └── socket.h
               ├── examples/
               │   └── W5500_TestCompile/
               │       └── W5500_TestCompile.ino
   
   ``

3. Restart Arduino IDE.

---

## 🧠 Description

The library provides a base framework for integrating the **WIZnet W5500** Ethernet controller with the **BW16** (Realtek RTL8720DN) dual-band Wi-Fi + BLE module via SPI.  
At this stage, the implementation verifies **successful compilation** and **header linkage**, confirming toolchain compatibility.

Hardware testing and network validation will follow.

---

## 🔌 Hardware Setup

⚠️ **Note of Caution**  
**BW16 module variants may differ in pin labeling or SPI pin mapping** (particularly MOSI, MISO, SCK, and CS).  
Always verify your specific board’s pinout from the manufacturer’s datasheet or silkscreen before wiring.  
Incorrect connections can prevent SPI communication or, in rare cases, damage the W5500 or BW16.

Refer to `/docs/media/circuit_image.png` for the wiring diagram.

> The BW16 operates at 3.3 V logic.  
> Connect the W5500’s SPI interface (SCK, MISO, MOSI, CS) accordingly, and share a common ground.  
> The module can be powered from the BW16’s 3.3 V pin or a dedicated 3.3 V regulator.

Refer to `/docs/media/circuit_image.png` for the wiring diagram.

> The BW16 operates at 3.3 V logic.  
> Connect the W5500’s SPI interface (SCK, MISO, MOSI, CS) accordingly, and share a common ground.  
> The module can be powered from the BW16’s 3.3 V pin or a dedicated 3.3 V regulator.

---
⚙️ Firmware / Variant Note

⚠️ Important:
The BW16 module exists in several hardware and firmware variants, and not all of them use the same Arduino pin mapping.
If you find that SPI communication (MOSI, MISO, SCK, or CS) does not behave as expected when connecting the W5500 module, your Realtek AmebaD “variant.cpp” file may require remapping.

Details and a working example can be found in Mikey’s BW16 repository:
https://github.com/mikey60/BW16-RTL8720DN-Module-Arduino

In short, the variant.cpp file located in

C:\Users\<your_user>\AppData\Local\Arduino15\packages\realtek\hardware\AmebaD\<version>\variants\rtl8721d\


defines the Arduino-to-hardware pin mappings.
Some BW16 modules need small edits there for SPI to function correctly.

For now, this project assumes that your module’s default AmebaD mapping is compatible.
If SPI activity appears on the wrong pins, revisit this section for correction.


## 🧩 Example Sketch

Example: `W5500_TestCompile.ino` (under `/examples/W5500_TestCompile/`)

This sketch confirms library linkage and SPI compile success.

---

## 🗓️ Activity Log

See [`Activity_Log.md`](Activity_Log.md) for project updates, milestones, and planned enhancements.

---

## 📄 License

Released under the [MIT License](LICENSE).

---

## 🚀 Status

**Stage:** Proof of Concept  
**Next steps:** Hardware verification, TCP/IP test, Ethernet3_BW16 integration, and PCB layout preparation.
