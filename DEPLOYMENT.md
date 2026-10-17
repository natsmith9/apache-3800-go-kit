# 📋 Field Deployment Checklist
**Project:** Apache 3800 Go-Kit  
**Style:** Emcomm & Tactical Auxiliary Station Operational Protocol (ARES Alignment)

This document provides step-by-step instructions to verify, deploy, and clear the go-kit during field operations, training exercises, or emergency call-outs.

---

## 🛑 Pre-Departure Bench Check
Before leaving for the staging area, verify the following:
* [ ] **Battery Capacity:** Confirm the LiFePO4 pack reads between **13.3V – 14.4V** under no load.
* [ ] **Fuse Integrity:** Visually inspect the lower 6-way fuse block. Ensure spare 5A, 10A, and 15A mini-fuses are packed.
* [ ] **Cabling Check:** Confirm all internal Anderson Powerpole connections are fully seated and right-angle coax pigtails are finger-tight on the panel bulkheads.
* [ ] **Peripherals:** Verify your iPad is fully charged, and the Mobilinkd TNC4 internal battery is topped off via USB.

---

## 🚀 Field Setup & Initialization

### Step 1: Structural Placement
1. Position the Apache 3800 case on a flat, stable surface.
2. Open the lid fully to expose the top faceplate panel and cooling ventilation grill.
3. *Note: Avoid operating the station with the lid completely closed during high-power data operations to prevent heat buildup.*

### Step 2: Antenna Deployment
1. Erect your external VHF/UHF antennas (e.g., roll-up slim-jim J-pole or mast-mounted colinear).
2. Ensure at least **10–15 feet of physical separation** between Antenna 1 (Voice/Winlink) and Antenna 2 (Headless APRS) to prevent receiver de-sensitization.
3. Connect the transmission coax lines to **SO-239 Port 1** and **SO-239 Port 2** respectively.

### Step 3: Power Up Sequence
1. Flip the **Master Power Toggle Switch** to the ON position.
2. Verify the **Digital Voltmeter** illuminates and reads **>12.8V**.
3. Toggle the **Cooling Fan** switch to verify the 40mm brushless motor spins freely and discharges ambient air away from the lower sub-floor.

### Step 4: Digital Mode Linking

#### A. Voice & Data Profile (Winlink Operations)
1. Turn on the **Yaesu FTM-150RASP** and set VFO A to your local target Winlink Gateway frequency.
2. Ensure the radio's data speed parameter is matched to your needs (**1200** or **9600** bps matching your soundcard profile).
3. Connect your iPad to the wireless data bridge, fire up **RadioMail**, and launch a **VARA-FM** packet session.

#### B. Headless Tracker Profile (Autonomous APRS)
1. Turn on the secondary radio deck and lock it to the national APRS frequency (**144.390 MHz**).
2. Boot up the **Mobilinkd TNC4** and confirm the blue status LED flashes, indicating a waiting Bluetooth BLE link.
3. Open **APRSfi** on your iPad, pair it with the TNC, and confirm GPS tracking coordinates are refreshing.
4. Once verified, dim or detach your primary radio display screen to save power. The TNC4 will continue tracking completely autonomously in the background.

---

## 📉 Pack-Up & Demobilization
1. Flip the **Master Power Toggle Switch** to OFF.
2. Disconnect external RF feedlines from the panel SO-239 bulkheads and screw on protective dust caps.
3. Secure the handheld microphone back into its top-panel parking bracket.
4. Close the case lid firmly and snap both structural latches down to ensure a watertight environmental seal for transit.
