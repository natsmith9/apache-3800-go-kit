## 🔧 Mechanical Fabrication & Chassis Assembly

This section covers the mechanical preparation, 3D printing, and panel machining required to drop an equipment deck into the Harbor Freight Apache 3800 lower tub.

---

### 1. Perimeter Mounting Frame (3D Print)
To avoid drilling mounting holes through the exterior shell or compromising the IP65 rubber lid gasket, the top deck is suspended from a rigid internal rim supported by the case's internal ribbing.

* **Design Source:** [Apache 3800 Panel Bracket by JohnS - N0CTL on Printables](https://www.printables.com/model/1478000-apache-3800-panel-bracket)
* **Architecture:** 4-piece modular frame (two U-shaped end caps, two straight center rails) linked via sliding dovetails to allow printing on standard 250×210 mm beds (e.g., Prusa MK3S / MK4S).
* **Insert Compatibility:** Features pre-modeled vertical bores sized for **M3 knurled brass heat-set inserts**[cite: 3].

#### Slicer Settings (PETG / ABS Recommended)
* **Perimeters / Wall Loops:** 4 to 5 (ensures dovetail keys and screw channels print solid).
* **Top / Bottom Layers:** 4 layers minimum.
* **Infill:** 35% to 45% (Gyroid or Grid).
* **Nozzle / Layer Height:** 0.4 mm nozzle @ 0.20 mm Structural.
* **Thermal Note:** Avoid standard PLA. Enclosed vehicle trunks reach internal temperatures exceeding 50°C (122°F), which will cause PLA brackets to creep and loosen under clamp load.

#### Bracket Assembly & Tub Mounting
1. **Join Frame:** Clean brim remnants from dovetail pins and slots. Dry-fit the 4 pieces on a flat surface, apply a thin coat of medium-viscosity CA glue or plastic adhesive into each joint, and press together[cite: 3].
2. **Set Threaded Inserts:** Using a soldering iron set between 220°C and 240°C, seat M3 brass heat-set inserts into each top-face pilot hole until flush.
3. **Anchor Frame:** Lower the bonded frame onto the internal shelf of the Apache 3800. Secure the bracket against the internal ribs using short #6 stainless steel screws from the inside, or bed the bottom edge in a bead of black polyurethane adhesive.

---

### 2. 1/4" ABS Deck Machining
The equipment plate is cut from a **12" × 16" sheet of 1/4" (6 mm) Haircell-Textured ABS**. The textured side faces upward to resist scratches, scuffs, and glare.

```text
       <----------------------- 14.80" - 14.85" ----------------------->
      +------------------------------------------------------------------+  ^
      | (R)                                                          (R) |  |
      |                                                                  |  |
      |   [CONTROLS]             [TRANSCVR DECK]             [EXHAUST]   |  | 10.55" - 10.60"
      |                                                                  |  |
      |                                                                  |  |
      | (R)                                                          (R) |  v
      +------------------------------------------------------------------+

```
#### Tooling & Feeds
* **Outer Perimeter & Corner Radii:** Rough-cut using a variable-speed jigsaw fitted with a 10–14 TPI bi-metal or plastic blade. Run at medium-low stroke speed with zero orbital action to prevent friction melting. Finish straight runs with a clamped fence guide.
* **Corner Radii:** File the corners to match the internal 0.75" to 0.85" (19–21 mm) corner fillet profile of the case.
* **Circular Ports (USB-C/Voltmeter, SO-239s, Audio Jacks):** Use a step drill bit (Unibit) backed with scrap plywood. Step bits ream clean 1-1/8", 5/8", and 1/4" holes in ABS without grabbing or cracking the plastic.   
* **40 mm Fan Port:** Cut using a 1-1/2" bi-metal hole saw run at low RPM, chamfering the perimeter edge slightly.   
* **Rectangular Cutouts (Latching Push Buttons, RJ-45 Coupler):** Bore 1/4" pilot holes inside each inside corner, cut perimeter relief lines with a fine jigsaw blade, and hand-file to final dimensions with a medium flat bastard file.

---
### 3. Sub-Floor Component Staging & Clearances
* **Battery Well (Left Bay):** Position the 15Ah LiFePO4 battery pack against the front-left bottom floor to distribute weight near the carry handle.   
* **RF Isolation:** Route the primary RG-400 jumper along the rear-right wall directly from the FTM-150 deck to Bulkhead 1, maintaining physical separation from the Blue Sea DC fuse harness.   
* **Deck Fasteners:** Fasten the completed ABS panel to the N0CTL perimeter bracket using M3 × 10 mm stainless steel button-head hex drive machine screws.

---

### Phase 1 Execution Checklist

| Status | Item Description | Source / Spec | Notes |
|:---:|---|---|---|
| [x] | Apache 3800 Weatherproof Case | Harbor Freight | Base shell on hand[cite: 1] |
| [x] | 12/14 AWG Wire & 30A Powerpoles | Standard Stock | DC harness materials on hand[cite: 2] |
| [ ] | Yaesu FTM-150RASP Transceiver | Ham Radio Outlet / DXE | Dual-band 55W/50W deck (~$297)[cite: 1, 2] |
| [ ] | Mobilinkd TNC4 + Mini-DIN-6 Cable | Mobilinkd | Hardware BLE KISS TNC (~$168–$172)[cite: 2] |
| [x] | 12V 15Ah LiFePO4 Battery | Amped Outdoors / Bioenno | Sub-floor battery power (~$100)[cite: 2] |
| [x] | Blue Sea 5035 6-Way Blade Fuse Block | Marine Supply | Common ground bus distribution (~$38)[cite: 2] |
| [x] | 12V Dual USB-C PD + Voltmeter Socket | Amazon | 1-1/8" cylindrical socket w/ cutoff switch (~$13)[cite: 1, 2] |
| [x] | 3.5mm Switching Audio Jacks | Electronics Supply | Headphone & external speaker panel routing (~$8)[cite: 1, 2] |
| [ ] | Dual WW / Red 12V LED Strip + SPDT Toggle | Amazon / Marine Supply | Switchable night-vision illumination (~$15)[cite: 1, 2] |
| [ ] | Illuminated 12V Latching Push Buttons | Baomain / Amazon | Rectangular console controls (~$12)[cite: 1] |
| [x] | 2ft RG-400 Coax Jumper + SO-239 Bulkhead | Shireen / DX Engineering | Double-shielded PTFE feedline (~$33)[cite: 1, 2] |
| [ ] | 3D-Printed N0CTL Perimeter Frame | Gwinnett Library Makerspace | 4-piece PETG bracket + M3 brass inserts[cite: 3] |
| [ ] | 12" × 16" × 1/4" Haircell ABS Sheet | Duco / OnlineMetals | Faceplate blank, 40mm fan & RJ-45 coupler (~$37)[cite: 1, 2] |

---

### Immediate Action Plan
1. Download the STL files directly from the [Printables repository](https://www.printables.com/model/1478000-apache-3800-panel-bracket) and slice the four dovetail segments using PrusaSlicer with 4 perimeters and 40% gyroid infill[cite: 3].
2. Reserve print time on the Prusa MK4S at the Norcross library branch to run the PETG frame sections.
3. Glue the dovetail joints, install the M3 heat-set inserts, and drop the assembled frame into the Apache 3800 tub to verify alignment before scoring and cutting the 1/4" ABS deck[cite: 3].
