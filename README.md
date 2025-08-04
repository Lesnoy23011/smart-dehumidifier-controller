# Smart Dehumidifier Controller with Home Assistant & ESP32

An open-source solution for whole-house dehumidifier control using ESP32, ESPHome, and Home Assistant. Designed for flexibility, this system replaces commercial wired controllers with distributed sensor logic and full Home Assistant integration—giving you fine-grained control over humidity, CO₂, particulate matter, and fresh air intake.

---

## ❌ The Problem with Existing Systems

Most commercial whole-house dehumidifier controllers use a single humidity sensor, typically at the wall panel, and allow just one additional wireless sensor at best. This approach struggles to maintain consistent humidity across medium or large homes, especially with air dampers or zoning systems in place.

---

## ✅ Project Goals and Advantages

This controller:

- Uses an **ESP32-based relay board** to switch the dehumidifier compressor/fan using standard 24V AC logic
- Integrates seamlessly with **Home Assistant** via **ESPHome**
- Aggregates **multiple humidity, CO₂, and air quality sensors** from around the home
- Automates ERVs, air dampers, or make-up air systems as needed
- Allows full configuration of setpoints, deadbands, timers, and conditional logic through HA's native automation tools

---

## ⚙️ Core Components

- [LILYGO T-Relay ESP32 Board](https://www.lilygo.cc/products/t-relay-esp32)
- ESPHome firmware flashed to ESP32
- Home Assistant (any installation method)
- Zigbee or ESPHome-compatible humidity/CO₂/PM2.5 sensors
- (Optional) Make-up air system, air dampers, ERV, or fan controller

---

🔌 Power Supply Notes
This project uses a 24V AC to 12V DC buck converter, which is mounted inside the custom enclosure. The STL case is designed specifically to fit this model:

🔗 AC to DC Converter on Amazon (B0983GW7YJ)

⚙️ Why this matters:
In HVAC systems, 24V AC is a standard control voltage used to actuate relays for compressors, fans, dampers, and thermostats. This converter allows you to safely step down 24V AC (available in most HVAC wiring) to 12V DC to power the LILYGO ESP32 T-Relay module and its onboard relays — eliminating the need for an additional power brick.

---
## 🛠 How It Works

1. The ESP32 acts as a relay controller, exposing two switches to Home Assistant.
2. Home Assistant uses its built-in **Generic Hygrostat** platform to enable smart dehumidification control.
3. Sensors placed throughout the house feed into Home Assistant.
4. Automations are used to:
   - Turn the dehumidifier on/off
   - Open/close air dampers
   - Trigger fresh air intake systems when CO₂ or humidity thresholds are exceeded

---

## 🏠 Real-World Use

Tested across multiple residential installations in South Florida—where high heat and humidity are persistent. System has proven extremely reliable in maintaining indoor comfort, reducing mold risk, and optimizing energy efficiency.

---

## 📷 Upcoming Additions

- 📸 Wiring diagram & setup photos
- 🧩 Sample ESPHome YAML configuration
- 🖼️ Home Assistant dashboard screenshots
- 🧱 STL files for custom enclosures (3D printed)

---

## 💡 Future Development Ideas

- Add weather-aware dehumidification (forecast-based logic)
- Mobile-friendly dashboard panel
- OTA updates and better error handling in ESPHome

---

## 📜 License

MIT License (will be added in future update)

---

*Built by Maksim Tsarenko. Contributions welcome once public hardware and software files are posted.*
