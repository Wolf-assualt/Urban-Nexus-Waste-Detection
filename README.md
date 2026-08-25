# Urban-Nexus-Waste-Detection

**An autonomous floating device that detects, collects, and reports water waste — in oceans, seas, ponds, and drainage systems.**

> Status: **Prototype / In Progress**

---

## The problem

Waste in water bodies — oceans, seas, ponds, and even urban drainage — usually goes undetected until it's a visible, large-scale problem. Manual monitoring doesn't scale, and by the time cleanup crews are called in, the damage to the ecosystem is already done.

Urban Nexus is a low-cost, deployable device designed to catch this earlier: sensing water quality in real time, physically collecting waste as it goes, and automatically alerting cleanup services when the situation is beyond what it can handle on its own.

## How it works

Urban Nexus operates in three stages:

### 1. Sense
The unit floats on a buoyant platform (built from sealed plastic bottles or a similar lightweight material) and carries onboard sensors that continuously monitor water quality — including **pH level** and **dissolved mineral/solid content (TDS)** — to detect signs of pollution or contamination.

### 2. Collect
An attached **net mechanism** gathers surface waste as the device moves through the water. It can operate:
- **Automatically** — triggered when sensor readings cross a pollution threshold
- **Manually** — via remote control, for targeted collection

### 3. Escalate
If the volume of detected waste is large — beyond what the device can handle alone — Urban Nexus **sends a signal to nearby ocean/water cleaning services**, flagging the location for a larger cleanup response.

```
   [ Float + Sensors ]
          |
          v
   pH / TDS reading -----> below threshold -----> continue monitoring
          |
          v
   above threshold
          |
          v
   [ Net collects waste ] ----> waste volume high? ----> [ Alert sent to cleanup service ]
```

## Components (planned / target hardware)

| Part | Purpose |
|---|---|
| Sealed plastic bottles / pontoon frame | Buoyancy — keeps the unit afloat |
| Waterproof enclosure (IP65+) | Houses electronics above the waterline |
| ESP32 microcontroller | Core controller — WiFi + Bluetooth built in, drives sensors and motor |
| Analog pH sensor module | Measures water pH |
| TDS sensor | Measures dissolved solids, as a proxy for mineral/pollution content |
| Turbidity sensor *(optional)* | Detects water murkiness / suspended waste |
| Servo or DC gear motor | Opens/closes the collection net |
| GSM module (e.g. SIM800L) *(optional)* | Sends alerts in areas without WiFi coverage |
| Solar panel + Li-ion battery | Powers the unit for unattended deployment |

## Alert mechanism

- **Near shore / WiFi range:** ESP32 sends an HTTP request/webhook to a server when thresholds are crossed
- **Open water / no WiFi:** GSM module sends an SMS or API call instead

## Roadmap

- [ ] Finalize sensor calibration for pH and TDS readings
- [ ] Build and waterproof the floating enclosure
- [ ] Implement automatic net-trigger logic based on sensor thresholds
- [ ] Add remote-control collection mode
- [ ] Integrate alert system (WiFi webhook / GSM fallback)
- [ ] Field test in a controlled pond environment
- [ ] Add solar charging for extended deployment

## Tech stack

`ESP32` `C++ (Arduino framework)` `pH Sensor` `TDS Sensor` `Embedded Systems` `IoT`

## Author

**Yuvarajan J** — ECE undergraduate, Sri Sairam College of Engineering, Bangalore
[yuva0051@gmail.com](mailto:yuva0051@gmail.com)

---

*This project is in active development. Contributions, suggestions, and feedback are welcome.*
