# 🔋 Thermal & Battery Management Log
**Operational Focus:** Voltage Stability Optimization & Heat Sink Preservation

Because the components are tightly enclosed within a sealed plastic case, monitoring voltage sag and managing duty cycles is crucial to maintaining field reliability. Use this log format and baseline data sheet to evaluate your go-kit's operational parameters during continuous field exercises.

---

## 📈 Baseline Operational Thresholds

### 1. Voltage Monitoring (LiFePO4 Chemistry)
*   **Nominal Operating Voltage:** 13.2V – 13.3V
*   **Maximum Charge State:** 14.4V – 14.6V
*   **Critical Low Voltage Floor:** **11.5V** *(Disconnect loads immediately to prevent damage to cells!)*
*   **Voltage Sag Limit:** Under a 50-watt transmission frame, a drop of up to **0.5V–0.7V** is normal. If the display sags below **11.8V during transmission**, drop the radio's power level down to Medium (25W) or Low (10W).

### 2. Thermal Duty Cycle Parameters
*   **Idle Mode:** Power deck cooling fan can remain OFF if ambient external temps are under 75°F.
*   **Winlink Voice/Data Mode:** Turn the cooling fan **ON**. High-speed VARA data bursts keep the transmitter at a high duty cycle, generating rapid heat inside the lower sub-floor.
*   **Headless APRS Mode:** The low-power secondary tracker deck creates minimal heat. If operating hidden below the panel, run the cooling fan for **5 minutes every hour** to cycle out stale ambient air.

---

## 📝 Field Performance Log Sheets

Copy this blank template entry into your deployment field notes to log performance trends under varying ambient operational loads.

### Log Entry Template
```text
Date: [YYYY-MM-DD] | Operator Call Sign: [        ] | Incident/Exercise: [               ]
--------------------------------------------------------------------------------------
[00:00] Initial Voltmeter (No Load): ______ V | Ambient Temperature: ______ °F
[00:00] Primary Mode Engaged: [ ] Winlink Data / [ ] Headless APRS / [ ] Voice Concurrent
[00:00] Fan Configuration:   [ ] Continuous    / [ ] Intermittent  / [ ] OFF

Hourly Status Tracking:
+------+--------------+----------------+-------------+-------------------------------+

| Time | Load Volts   | TX Sag Volts   | Fan Status  | Operational Notes             |
+------+--------------+----------------+-------------+-------------------------------+

|      |       V      |       V        |  [ON / OFF] |                               |
|      |       V      |       V        |  [ON / OFF] |                               |
|      |       V      |       V        |  [ON / OFF] |                               |
|      |       V      |       V        |  [ON / OFF] |                               |
+------+--------------+----------------+-------------+-------------------------------+

Final Battery Recovery Volts (No Load after shutdown): ______ V
```

### 💡 Field Best Practices
*   **Shade Your Kit:** Keep the open Apache 3800 case out of direct sunlight whenever possible. Sunlight hitting the custom black/dark ABS top panel will accelerate thermal saturation.
*   **Monitor the Fans:** If the internal 40mm cooling fan exhaust air begins to feel significantly hot to the touch during a heavy Winlink traffic pileup, extend your data transmission intervals to give the FTM-150RASP internal heat sinks time to shed heat.
