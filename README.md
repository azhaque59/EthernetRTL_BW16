PREAMBLE
The goal of this effort is to leverage the 5GHz capability coupled with the cost effectiveness of the BW16 to make a WiFi to Ethernet Bridge.
Until recently this dual capability was unavailable in the small microcontrollers in the market
Secondly, Ethernet.h has gradually improved over time and is now available as Ethernet3.h. This can dovetail seamlessly in the Arduino environment with tweaking for use with the Ameba BW16, thus making it attractive for hobbyists around the world

EthernetRTL_BW16
=================

Work-in-progress Arduino library for Ai-Thinker BW16 (RTL8720DN) + WIZnet W5500 Ethernet module.

Purpose:
This library provides a compile-verified stub and driver integration layer for the
WIZnet ioLibrary_Driver (W5500) adapted to the Realtek Ameba-D / Ai-Thinker BW16 platform.

Version 1.0.0: Compilation verified only (no hardware test yet).

Installation:
1. Extract this folder into Documents\Arduino\libraries\EthernetRTL_BW16
2. Restart Arduino IDE.
3. Open File -> Examples -> EthernetRTL_BW16 -> W5500_TestCompile
4. Compile to verify successful header linkage.

Next Steps (To DO):
- Connect BW16 to W5500 via SPI.
- Validate link and test basic ping.
- Publish schematic and hardware setup.

Roadmap:
v1.0.0  Compile verified only (this release)
v1.1.0  Hardware validated (ping verified)
v1.2.0  Full Wi-Fi ↔ Ethernet bridge

Additional Resources:
1.https://www.amebaiot.com/en/amebad-bw16-arduino-getting-started/
2. https://github.com/mikey60/BW16-RTL8720DN-Module-Arduino
3.https://github.com/ambiot/ambd_arduino/tree/master/Arduino_package
