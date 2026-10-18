# Apache 3800 Dual-VFO VHF/UHF Go-Kit
An open-source, self-contained EMCOMM station built inside a [Harbor Freight Apache 3800 Weatherproof Case](https://harborfreight.com). 

Designed with a modular evolution path—starting as a robust core dual-VFO field station, expanding into an advanced headless digital data bridge, and scaling into a fully autonomous remote-antenna APRS node.

## 📊 Overview & Architecture
- **Case Frame:** Harbor Freight Apache 3800 Weatherproof Hard Case.
- **Phased Deployment Design:** Scales from a clean, single-deck mobile station (Phase 1) to an x86-driven digital gateway (Phase 2) and a sealed, remote-antenna autonomous telemetry node (Phase 3).
- **High-Speed Data Capable:** 6-pin mini-DIN interface implementation supporting both legacy 1200-baud packet and modern 9600-baud / VARA-FM throughput.

---

## 🛠 Phased Bill of Materials (BOM) & Roadmap

### 🛠 Phase 1: Core Dual-VFO Field Station
*Focuses on a self-contained voice and 1200-baud BLE packet/APRS setup with integrated panel audio routing.*

| Qty | Item Description | Hardware / Specifications |
|---|---|---|
| 1 | Dual-Band VHF/UHF Mobile Deck | Yaesu FTM-150RASP (55W/50W Dual-Receive) |
| 1 | Hardware Bluetooth/USB KISS TNC | Mobilinkd TNC4 TNC Engine |
| 1 | 6-Pin Mini-DIN TNC Cable | Mobilinkd MiniDIN-6 Cable Set (1200/9600 baud) |
| 1 | Station Power Source | 12V 15Ah LiFePO4 Battery Pack |
| 1 | DC Fuse Distribution Block | Blue Sea Systems 5035 ST Blade 6-Circuit Fuse Block |
| 1 | Diagnostics & USB Charging | 12V Dual USB-C PD Socket + LED Voltmeter (w/ Cutoff Switch) |
| 1 | Audio Routing Panel | Panel-Mount 3.5mm External Speaker & Headphone Jacks |
| 1 | Internal Coaxial Jumper | 2ft Double-Shielded RG-400 PL-259 Jumper |
| A/R | Power Distribution Harness | 12/14 AWG Stranded Wire & Genuine Anderson Powerpoles (30A) |
| 1 | Panel Chassis Top Plate | Custom Cut 1/4" ABS Sheet |
| 1 | Bulkheads & Enclosure Hardware | SO-239 Bulkhead, 12V 40mm Exhaust Fan & Guard, RJ-45 Mic Pass-Through |

### Phase 2: Advanced Data & VARA-FM Bridge (Future Expansion)
*Adds an isolated second RF path and a native x86 compute node to run headless Windows, local Wi-Fi, and VARA-FM Winlink nodes.*

| Qty | Item Description | Hardware / Specifications |
|---|---|---|
| 1 | Headless x86 Compute Bridge | 12V Native Intel N100 Pico-PC (e.g., MeLE Quieter 4C) |
| 1 | Digital Soundcard Interface | Digirig Mobile (9600-baud config) + Mini-DIN-6 Cable |
| 1 | Secondary Autonomous Radio | Ultra-Compact HT or Mono-Band VHF Deck |
| 1 | Standalone GPS Receiver | VK-172 u-blox7 USB GPS Dongle |
| 1 | Secondary Coaxial Jumper | 2ft RG-400 PL-259 Jumper & 2nd SO-239 Bulkhead Port |

### Phase 3: Sealed Autonomous Remote-Antenna Node (Future Expansion)
*Configures the go-kit as a zero-tablet, weather-sealed field base station. The Apache case remains closed and latched while feedlines run externally to a deployed field antenna.*

| Qty | Item Description | Hardware / Specifications |
|---|---|---|
| 1 | External Feedline Run | Weather-Respected RG-8X or LMR-240 Coax (25ft / 50ft spooled) |
| 1 | Portable Field Antenna Options | Roll-Up J-Pole, Portable Dipole, or Lightweight Mast-Mounted Ground Plane |
| 1 | Feedline Bulkhead Pass-Through | Weatherproof Case Feedline Feed-Thru / Quick-Disconnect Panel |
| 1 | Autonomous Power Timer / Solar | Optional Solar Charge Controller & Panel for multi-day unattended grid independence |

---

## 🚀 Deployment Modalities

### 1. Phase 1: Voice & BLE Packet Station (Current)
1. Turn on the station power via the Blue Sea fuse block branches.
2. Pair your iPad or phone directly to the **Mobilinkd TNC4** via Bluetooth Low Energy (BLE).
3. Use **RadioMail** or mobile APRS apps for 1200-baud packet Winlink and real-time position reporting while managing tactical voice nets on the Yaesu FTM-150RASP VFO A.

### 2. Phase 2: High-Speed VARA-FM Gateway
1. Power on the internal Intel N100 x86 bridge, which auto-boots headlessly and spins up a local Wi-Fi hotspot and VARA-FM server.
2. Connect your tablet to the internal Wi-Fi network to run native x86 VARA-FM sessions via the Digirig Mobile interface.
3. Keep the secondary radio and TNC4 running an independent background APRS tracking loop.

### 3. Phase 3: Sealed Autonomous Remote-Antenna Node
1. Connect a portable roll-up J-pole or field dipole to the exterior Apache case bulkhead connector using a dedicated external feedline.
2. Configure the station for autonomous periodic beaconing, packet digipeating, or unattended Winlink gateway operation.
3. Latch and seal the Apache 3800 case lid completely—protecting all internal batteries, compute nodes, and radios from weather, dust, and condensation while operating remotely in the field.

---

## ⚖️ License
This project is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** License.
