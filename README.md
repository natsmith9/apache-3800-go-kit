# Apache 3800 Dual-VFO VHF/UHF Go-Kit
An open-source, self-contained EMCOMM station featuring the **Yaesu FTM-150RASP**, a headless **Intel N100 x86 Data Bridge**, and an isolated **Mobilinkd TNC4** APRS data engine. 

Designed for high-speed packet data, native VARA-FM WIDE Winlink gateways, and independent simultaneous voice and autonomous tracking modes driven wirelessly via iPad apps (**RadioMail** and **aprs.fi**) or standalone internal compute.

## 📊 Overview & Features
- **Case Frame:** Built inside a [Harbor Freight Apache 3800 Weatherproof Case](https://harborfreight.com).
- **True Dual-RF Paths:** Complete physical isolation between your main Winlink/Voice communications pipeline and your automated background APRS tracker to prevent VFO contention.
- **Native x86 VARA-FM Bridge:** Incorporates a native 12V Intel N100 Pico-PC running headless Windows and a local Wi-Fi hotspot, exposing VARA-FM TCP ports (`8300`/`8301`) directly to iOS clients without emulation latency.
- **High-Speed Data Capable:** 6-pin mini-DIN interface implementation supporting both legacy 1200-baud and modern 9600-baud packet/VARA-FM WIDE throughput.
- **Dual-Mode APRS Operability:** Supports direct iOS BLE control via **aprs.fi** or 100% autonomous, iPad-off position beaconing and digipeating via the internal x86 node and USB GPS receiver.

---

## 🛠 Bill of Materials (BOM)

### 1. RF, Compute & Modems

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Dual-Band VHF/UHF Mobile Deck | Yaesu FTM-150RASP |
| 1 | Headless x86 Data & Wi-Fi Bridge | 12V Native Intel N100 Pico-PC (e.g., MeLE Quieter4C / NucBox G5) |
| 1 | Digital Soundcard Interface | Digirig Mobile (9600-baud config) |
| 1 | Unfiltered Data Cable Link | Digirig 6-pin Mini-DIN Data Cable (w/ Mix-31 Ferrite) |
| 1 | Hardware Bluetooth/USB KISS TNC | Mobilinkd TNC4 TNC Engine |
| 1 | Secondary Autonomous Radio | Ultra-Compact HT or Mono-Band VHF Deck |
| 1 | Audio Interconnect Cable | Mobilinkd-to-Radio Shielded Patch Cable (w/ Mix-31 Ferrite) |
| 1 | Standalone Position Receiver | USB GPS Receiver Dongle (u-blox7 VK-172 or magnetic puck) |

### 2. Power & Distribution

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Deep-Cycle Station Battery | 12V 12Ah–15Ah LiFePO4 Battery Pack |
| 1 | Central Power Splitter | 6-Way DC Marine Fuse Block / Powerpole Distribution Block |
| A/R | Heavy DC Connectors | Genuine Anderson Powerpole Kits (15A/30A) |
| 1 | 12V Compute Power Lead | 5.5x2.5mm DC Barrel (or 12V USB-C Trigger) to Powerpole Cable |
| 1 | Diagnostics / Charge Deck | Integrated Voltmeter & Dual USB-C PD Socket |

### 3. Panel Hardware & Interconnects

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Case Panel Chassis Insert | Laser-Cut / 3D-Printed ABS Top Plate |
| 2 | Antenna Bulkhead Ports | SO-239 Female-to-Female Panel Mounts |
| 2 | Internal Coaxial Cable Lines | Double-Shielded RG-400 Pigtails (Right-Angle PL-259) |
| 1 | Thermal Management Unit | 12V 40mm Brushless Exhaust Fan, Guard & Opposite Intake Louver |
| 1 | Handset Extension Link | RJ-45 Shielded Panel-Mount Mic Extension |

---

## 📐 Mechanical & Signal Layout

```text
+---------------------------------------------------------------------------------+
|                                 MAIN TOP PANEL                                  |
|                                                                                 |
|   [ MASTER POWER TOGGLE ]   [ DIGITAL VOLTMETER ]   [ DUAL USB-C POWER DELIVERY ]|
|                                                                                 |
|       (SO-239 ANTENNA 1)                             (SO-239 ANTENNA 2)         |
|      Main FTM-150RASP Loop                         Dedicated Headless APRS      |
|                                                                                 |
|                   [ FTM-150RASP CONTROL FACEPLATE FLUSH MOUNT ]                 |
|                                                                                 |
|  (3.5mm SPKR)    [ INTAKE LOUVERS ]       [ 40mm EXHAUST ]    (RJ-45 MIC PORT)  |
+=================================================================================+
                                         ||
                                         || (Internal Sub-Floor Component Array)
                                         \/
+---------------------------------------------------------------------------------+
|                                 LOWER BAY DECK                                  |
|                                                                                 |
|   +--------------------+     +---------------------+     +------------------+   |
|   |  12V 15Ah LiFePO4  | ==> | 6-Way DC Fuse Block | ==> | Secondary Radio  |   |
|   |  Battery Pack      |     +---------------------+     +------------------+   |
|   +--------------------+        ||              ||                ^             |
|                                 || (12V DC)     || (12V DC)       | (Audio/PTT) |
|                                 \/              \/                v             |
|                   +-------------------+    +------------------+  +----------+   |
|                   | FTM-150RASP DECK  |    | Intel N100 x86   |  | Mobilinkd|   |
|                   +-------------------+    | Headless Bridge  |  |   TNC4   |   |
|                             ^              +------------------+  +----------+   |
|                             | (6-Pin DIN)     |       |     |         ^         |
|                             v                 |       |     +---------+         |
|                   +-------------------+       |       |      (USB/BLE KISS)     |
|                   |  Digirig Mobile   | <-----+       +---> [ USB GPS Dongle ]  |
|                   +-------------------+  (USB Audio/COM)                        |
+---------------------------------------------------------------------------------+
```

---

## 🚀 Deployment Modalities

### 1. Voice and High-Speed Data Mode (Winlink Operations)
1. Turn on the **Master Panel Power Toggle**. The Intel N100 bridge auto-boots via BIOS power-loss recovery, logs in headlessly, launches **VARA-FM**, and broadcasts its local Wi-Fi hotspot.
2. Connect your iPad to the Go-Kit Wi-Fi network.
3. Open **RadioMail** on the iPad, point the VARA-FM modem IP to the N100 bridge (`192.168.137.1:8300`), and initiate a session.
4. The N100 and Digirig Mobile manage the hard PTT and 9600-baud DSP handshakes natively while the Yaesu FTM-150RASP delivers clean RF bursts.

### 2. Interactive Tracker Mode (iPad BLE APRS)
1. Boot the station and pair your iPad directly to the **Mobilinkd TNC4** via Bluetooth Low Energy (BLE).
2. Open **aprs.fi** on the iPad to view real-time local station telemetry, send two-way APRS messages, and push position beacons using the iPad's internal GPS.
3. The secondary APRS radio handles all 144.390 MHz traffic independently, leaving the FTM-150RASP completely free for voice nets or Winlink traffic.

### 3. Headless Autonomous Mode (Zero-Tablet APRS / Digipeater)
1. Boot the station with the **USB GPS Dongle** and **Mobilinkd TNC4** connected to the Intel N100 bridge.
2. The N100's background APRS client (PinPoint APRS / YAAC / Direwolf) reads NMEA coordinates from the USB GPS and keys the secondary radio via the TNC4 on a scheduled beacon interval.
3. Dim or power off the FTM-150RASP faceplate and stow your iPad completely powered off—the Go-Kit operates as a self-contained autonomous tracker or field fill-in digipeater.

---

## 🔧 Pre-Deployment System Configuration (x86 Appliance Setup)
To ensure the Intel N100 behaves as a turnkey field appliance without requiring a monitor or keyboard:
- **BIOS Auto-Boot:** Set `Restore on AC/Power Loss` to **Power On** so the node boots immediately when the master 12V switch is flipped.
- **Headless Startup:** Configure Windows auto-logon (`netplwiz`) and place shortcuts for `VARA FM.exe`, your APRS client, and a local Wi-Fi Hotspot PowerShell script inside `shell:startup`.
- **Update Lockout:** Disable Windows Update automatic restarts and active-hours reboots to prevent mid-deployment downtime.

---

## ⚖️ License
This project is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** License. 

You are free to copy, redistribute, remix, transform, and build upon this material for any purpose, even commercially, under the following terms:
- **Attribution:** You must give appropriate credit, provide a link to the license, and indicate if changes were made.
- **ShareAlike:** If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
