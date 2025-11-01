# EthernetRTL_BW16

## Overview
**EthernetRTL_BW16** is a proof-of-concept adaptation of the Ethernet3 (W5500) library for the **Realtek BW16 (RTL8720DN / Ameba-D)** platform.  
It demonstrates compile-time integration and library recognition for SPI-based W5500 Ethernet connectivity on BW16.

The project serves as a learning and foundation layer for enabling **wired Ethernet communication** on a primarily Wi-Fi-based SoC.

---

## Installation

### Folder Structure (Windows)
Place the extracted folder in your Arduino libraries directory:

```
C:\Users\HP\Documents\Arduino\libraries\EthernetRTL_BW16\
│
├── library.properties
├── src
│   ├── EthernetRTL_BW16.h
│   ├── EthernetRTL_BW16.cpp
│   ├── ioLibrary_Driver
│   │   ├── wizchip_conf.h
│   │   ├── w5500.h
│   │   └── socket.h
│   └── examples
│       └── W5500_TestCompile
│           └── W5500_TestCompile.ino
├── README.md
├── Activity_Log.md
└── docs
    └── media
        └── circuit_image.png
```

Restart Arduino IDE after installation.

---

## Hardware Setup

Reference circuit diagrams:
- `/docs/media/circuit_image.png`
- `/docs/media/Schematic_BW16_W5500.pdf`

⚙️ Power the W5500 via 3.3 V from BW16 (or an external regulator if required).  
Ensure shared **GND** and connect the SPI lines as indicated in the schematic.

---

## Usage

1. Open **File → Examples → EthernetRTL_BW16 → W5500_TestCompile**
2. Compile to confirm proper linkage with `wizchip_conf.h`
3. Expected serial output:
   ```
   W5500_TestCompile: starting
   W5500_TestCompile: header linkage OK
   ```

---

## Next Steps

- Integrate live SPI transactions and W5500 initialization.
- Verify hardware-level connectivity (ping test via 2.4 GHz Wi-Fi bridge or LAN).
- Move toward a hybrid Ethernet/Wi-Fi link mode for Ameba-D.

---

## License

Licensed under the **MIT License** — see the LICENSE file for details.

---

**Project by:** EthernetRTL Team  
**Status:** Work in Progress (as of Oct 2025)
