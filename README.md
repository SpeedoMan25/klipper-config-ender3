# Ender 3 Klipper Setup

## Overview
This repository contains my personal configuration and setup files for running **Klipper firmware** on an **Ender 3** with an **SKR-mini-E3 V3.0**. The goal of this project is to improve print quality, speed, and reliability by leveraging Klipper's advanced features.

> **Note:** This configuration uses a different stepper motor for the extruder as well as a BLTouch. See the Hardware Modifications section for details.

## Hardware Modifications
This configuration is tailored for an Ender 3 with a variety of upgrades.
- **Extruder Motor:** The stock motor has been replaced with a `17HM19-2004S1` stepper motor. Key specifications are listed below. You will need to adjust your `rotation_distance` and `run_current` in `printer.cfg` to match your specific extruder and this motor.
    - **Model:** 17HM19-2004S1
    - **Step Angle:** 0.90°
    - **Holding Torque:** 0.46 Nm
    - **Current:** 2.00 Amps/Phase
- **BLTouch:** This setup includes a **BLTouch v3.1** auto bed leveling sensor for improved first layer accuracy and bed leveling.
    - **Probe Type:** Capacitive/Mechanical
    - **Mount:** Standard Ender 3 mount
    - **Wiring:** Connected to the dedicated BLTouch pins on the SKR-mini-E3 V3.0
    - **Features:** Auto bed leveling, Z-offset configuration, safe homing, dynamic probing
- **Hotend:** The printer uses a **Phaetus Dragonfly Hotend BMS** for reliable high-temperature printing.
    - **Type:** All-metal, high-flow hotend
    - **Supports:** PLA, PETG, ABS, and other high-temperature filaments
    - **Notes:** Requires calibration of PID and max temperature in `printer.cfg`
- **High-Temperature Sensor Cartridge:**  
    - **Model:** Upgrade M3x15MM 300°C Thermistor Cartridge  
    - **Compatibility:** Dragonfly BMS BMO Hotend / Dragon Hotend, VORON V2.4, V0.1, V1.8 3D Printers  
    - **Purpose:** Accurate temperature sensing for high-temp printing  
    - **Notes:** Ensure proper wiring and PID calibration for safe operation
- **Bed:** Equipped with a **magnetic PEI bed** for improved adhesion and easier print removal.
    - **Type:** Flexible, removable magnetic sheet
    - **Surface:** PEI coated for better filament sticking
    - **Notes:** Ensure proper Z-offset calibration after installation
- **Filament Tubing:** Uses **Capricorn PTFE tubing** for smoother filament feeding and higher-temperature printing.
    - **Type:** High-quality PTFE, low-friction
    - **Diameter:** 4mm inner diameter, 6mm outer diameter (standard for Ender 3)
    - **Notes:** Recommended for high-temp filaments like PETG and ABS
    
## Features
- Custom Klipper firmware configuration for the Ender 3
- Optimized for SKR E3.0 board
- Supports common Ender 3 upgrades:
  - **BLTouch auto bed leveling**
  - Filament sensors
  - **Phaetus Dragonfly Hotend BMS**
  - **Magnetic PEI bed**
- Macro scripts for common operations
- Integration with **Fluidd/Mainsail** for web-based control
- Tuned motion and temperature settings for improved print quality

## Installation
1.  **Flash SKR E3.0** with the appropriate Klipper firmware.
2.  Install **Klipper** on a Raspberry Pi or other host machine.
3.  Upload the configuration files from this repository to the `~/klipper/config` directory.
4.  Configure BLTouch in `printer.cfg` (probe pin, offsets, bed mesh settings, dynamic probing).
5.  Restart Klipper and calibrate your printer (steps/mm, PID tuning, Z-offset, etc.).
6.  Access your printer via **Fluidd** or **Mainsail**.

## Planned Upgrades
These are future enhancements planned for the Ender 3 Klipper setup to improve power management, cooling, and overall reliability. These upgrades will be implemented **when I have time**, and associated `.step` files will be uploaded **when possible**.
- **Mean Well Power Supply:**  
  - Upgrade from the stock PSU to a **Mean Well** for more stable and reliable power delivery.
  - Will improve system safety and allow for higher power demands from additional upgrades.
- **Custom Under-Printer Power Supply Shroud:**  
  - Enclosure to safely house the Mean Well PSU under the printer.
  - Improves cable management and airflow.
- **Buck Converter for Raspberry Pi:**  
  - Power the Pi directly from the printer's main power supply using a buck converter.
  - Provides a single, clean power source for the entire setup.
  - Ensures reliable operation of Klipper without needing a separate power adapter.
- **Upgraded Enclosure with Noctua Fans:**  
  - Enclosure will house electronics and provide active cooling using **Noctua fans**.
  - Helps maintain stable temperatures for both the electronics and the Mean Well PSU.
  - Reduces fan noise while ensuring efficient airflow.
- **Notes:**  
  - All upgrades are planned and may be implemented in stages.
  - Proper calibration and safety checks will be performed after installation.
  - `.step` files for custom parts will be uploaded when possible.
- **Filament Runout Sensor:**  
  - Adds a **sensor to detect when filament runs out or breaks** during a print.
  - Will pause the printer and allow filament replacement without ruining the print.
  - Compatible with Klipper's `filament_runout_sensor` configuration.

> ⚠️ Always verify your hardware connections and firmware settings before powering the printer.

## Notes
- This setup is tailored for my specific Ender 3 configuration and may need adjustments for your printer.
- Firmware files and configuration settings are provided as a reference.
- Contributions and suggestions are welcome, but use caution when applying changes to your own printer.

## Resources (If Not Listed Here Check Datasheets)
- [Klipper Documentation](https://www.klipper3d.org/)
- [Fluidd Web Interface](https://docs.fluidd.xyz/)
- [Mainsail Web Interface](https://docs-os.mainsail.xyz/)
- [BIGTREETECH-SKR-mini-E3](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master)
- [Dragonfly-BMS](https://github.com/Phaetus/Dragonfly-BMS)
- [Ender-3](https://github.com/Creality3DPrinting/Ender-3)
- [BLTouch](https://www.antclabs.com/bltouch)
