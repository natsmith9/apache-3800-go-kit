# 🔌 Data Port Pinout Sheet: Yaesu FTM-150RASP to Digirig Mobile

To run high-speed **9600-baud packet** or **VARA-FM Wide**, you must bypass the radio's microphone jack filtering circuits. This sheet documents the exact pin mapping from the rear-panel round **6-Pin Mini-DIN Data Jack** on the Yaesu FTM-150RASP to the **3.5mm TRRS Audio / PTT jacks** on the Digirig Mobile interface.

---

## 📍 Yaesu 6-Pin Mini-DIN Rear Panel Diagram
*(Looking directly at the female jack on the back of the radio deck)*

```text
       [  TOP  ]
        /---_---\

       | 5     1 |
       |  6   2  |
       |  4   3  |
        \_______/
```

### Pin Assignment Table

| Pin # | Pin Name | Signal Description | Target Destination |
| :---: | :--- | :--- | :--- |
| **1** | PKD | Packet Data Input (TX Audio) | Digirig **Audio Jack** (Ring 1 - Audio In) |
| **2** | GND | Signal Ground | Digirig **Audio/PTT** (Sleeve - Common Ground) |
| **3** | PTT | Push-To-Talk (Ground to Transmit) | Digirig **PTT Jack** (Ring 1 - PTT Control) |
| **4** | RX9600 | 9600-Baud Discriminator Output (Unfiltered RX) | Digirig **Audio Jack** (Tip - Audio Out / Wide data) |
| **5** | RX1200 | 1200-Baud De-emphasized Audio Output (Filtered RX) | Optional alternate data line (Not used for 9600/VARA) |
| **6** | SQ | Squelch Status Output | Typically left floating for headless client soundcards |

---

## 🎛 Digirig Mobile TRRS Terminal Mapping

If you are fabricating or modifying your own custom shielded interface jumper cords, wire them to the standard Digirig 3.5mm TRRS male plugs according to the specifications below:

### 1. Digirig "Audio" Port (3.5mm TRRS)
*   **TIP:** Audio Out from Digirig (Feeds into Yaesu **Pin 1 - PKD** for transmission)
*   **RING 1:** Audio In to Digirig (Feeds from Yaesu **Pin 4 - RX9600** or **Pin 5 - RX1200**)
*   **RING 2:** [Left Floating / Not Used]
*   **SLEEVE:** Common System Ground (Connects to Yaesu **Pin 2 - GND**)

### 2. Digirig "PTT" Port (3.5mm TRRS)
*   **RING 1:** Push-To-Talk Control Trigger (Connects to Yaesu **Pin 3 - PTT**)
*   **SLEEVE:** Common System Ground (Connects to Yaesu **Pin 2 - GND**)

### 💡 High-Speed Configuration Tech Tips
1. **Unfiltered Audio:** Ensure your jumper links to **Pin 4 (RX9600)** rather than Pin 5. This allows the high-frequency tones used by VARA-FM Wide to pass through to the soundcard cleanly without distortion.
2. **RF Chokes:** Wrap your custom 6-pin mini-DIN cable around a **Type 43 ferrite snap-on bead** right next to the radio chassis. This blocks stray RF from feeding back into the interface and breaking your iPad's data session.
