# Apache 3800 Dual-VFO VHF/UHF Go-Kit
An open-source, self-contained EMCOMM station featuring the **Yaesu FTM-150RASP** and a headless autonomous **Mobilinkd TNC4** APRS data engine. 

Designed for high-speed packet data, VARA-FM Winlink gateways, and independent simultaneous voice and tracking modes driven wirelessly via iPad apps (**RadioMail** and **APRSfi**).

## 📊 Overview & Features
* **Case Frame:** Built inside a [Harbor Freight Apache 3800 Weatherproof Case](https://harborfreight.com).
* **True Dual-RF Paths:** Complete physical isolation between your main Winlink/Voice communications pipeline and your automated background APRS tracker.
* **High-Speed Data Capable:** 6-pin mini-DIN interface implementation supporting both legacy 1200-baud and modern 9600-baud packet/VARA-FM throughput.
* **100% Headless Operability:** Wireless control via Bluetooth/BLE to optimize power consumption in field environments.

## 🛠 Bill of Materials (BOM)

### 1. RF & Modems

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Dual-Band VHF/UHF Mobile Deck | Yaesu FTM-150RASP |
| 1 | Digital Soundcard Interface | Digirig Mobile (9600-baud config) |
| 1 | Unfiltered Data Cable Link | Digirig 6-pin Mini-DIN Data Cable |
| 1 | Hardware Bluetooth TNC | Mobilinkd TNC4 TNC Engine |
| 1 | Secondary Autonomous Radio | Ultra-Compact HT or Mono-Band Deck |
| 1 | Audio Interconnect Cable | Mobilinkd-to-Radio Shielded Patch Cable |

### 2. Power & Distribution

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Deep-Cycle Station Battery | 12V 12Ah–15Ah LiFePO4 Battery Pack |
| 1 | Central Power Splitter | 6-Way DC Marine Fuse Block / Powerpole Block |
| A/R | Heavy DC Connectors | Genuine Anderson Powerpole Kits (30A) |
| 1 | Diagnostics / Charge Deck | Integrated Voltmeter & Dual USB-C PD Socket |

### 3. Panel Hardware & Interconnects

| Qty | Item Description | Suggested Hardware |
|---|---|---|
| 1 | Case Panel Chassis Insert | Laser-Cut / 3D-Printed ABS Top Plate |
| 2 | Antenna Bulkhead Ports | SO-239 Female-to-Female Panel Mounts |
| 2 | Internal Coaxial Cable Lines | Shielded RG-316 Pigtails (Right-Angle PL-259) |
| 1 | Thermal Management Unit | 12V 40mm Brushless Cooling Fan & Guard |
| 1 | Handset Extension Link | RJ-45 Shielded Panel-Mount Mic Extension |

---

## 📐 Mechanical Layout

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
|    (3.5mm SPKR OUT)       [ VENTILATION GRILL ]       (RJ-45 MIC PASS-THROUGH)  |
+=================================================================================+
                                         ||
                                         || (Internal Sub-Floor Component Array)
                                         \/
+---------------------------------------------------------------------------------+

|                                LOWER LOWER BAY                                  |
|                                                                                 |
|   +--------------------+     +---------------------+     +------------------+   |
|   |  12V 15Ah LiFePO4  | --> | 6-Way DC Fuse Block | --> | Mobilinkd TNC4   |   |
|   |  Battery Pack      |     +---------------------+     +------------------+   |
|   +--------------------+                |                         |             |   |
|                                         v                         v             |   |
|                              [ FTM-150RASP RF DECK ]      [ Secondary Radio ]   |
+---------------------------------------------------------------------------------+
```

---

## 🚀 Deployment Modalities

### 1. Voice and Data Mode (Winlink Operations)
1. Turn on the master panel power toggle.
2. Pair your iPad with your wireless data bridge server.
3. Open **RadioMail** on the iPad, select your connection parameters, and initiate a **VARA-FM** session.
4. The Digirig Mobile manages the hard PTT lines seamlessly while the Yaesu deck delivers clean digital bursts.

### 2. Headless Tracker Mode (Autonomous APRS)
1. Boot the station, confirm local tracking parameters, and configure your beaconing schedules in the **APRSfi** app via BLE.
2. Dim or turn off the primary Yaesu FTM-150 control faceplate to save battery power.
3. Disconnect or stow your iPad away—the **Mobilinkd TNC4** manages position calculations, hardware PTT toggles, and beacon intervals automatically in the background.

---

## ⚖️ License
This project is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** License. 

You are free to copy, redistribute, remix, transform, and build upon this material for any purpose, even commercially, under the following terms:
* **Attribution:** You must give appropriate credit, provide a link to the license, and indicate if changes were made.
* **ShareAlike:** If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
