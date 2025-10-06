# Ender 3 Klipper Setup

## Overview
This repository contains my configuration and setup files for running **Klipper firmware** on an **Ender 3** with an **SKR-mini-E3 V3.0**. The goal is to improve print quality, speed, and reliability by leveraging Klipper's advanced features.

> **Note:** This configuration uses a different stepper motor for the extruder, a BLTouch, and other upgrades. See the Hardware Modifications section for details.

## Hardware Modifications
This setup includes several upgrades to the stock Ender 3:

- **Extruder Motor:** `17HM19-2004S1` stepper motor. Adjust `rotation_distance` and `run_current` in `printer.cfg` accordingly.
    - **Model:** 17HM19-2004S1  
    - **Step Angle:** 0.90°  
    - **Holding Torque:** 0.46 Nm (~65 oz-in)  
    - **Current:** 2.00 Amps/Phase  

- **BLTouch:** **BLTouch v3.1** auto bed leveling sensor for improved first-layer accuracy.
    - **Probe Type:** Capacitive/Mechanical  
    - **Mount:** Standard Ender 3 mount  
    - **Wiring:** Connected to dedicated BLTouch pins on SKR-mini-E3 V3.0  
    - **Features:** Auto bed leveling, Z-offset configuration, safe homing, dynamic probing  

- **Hotend:** **Phaetus Dragonfly Hotend BMS** for reliable high-temperature printing.
    - **Type:** All-metal, high-flow hotend  
    - **Supports:** PLA, PETG, ABS, and other high-temp filaments  
    - **Notes:** Requires PID and max temperature calibration in `printer.cfg`  

- **High-Temperature Sensor Cartridge:** Upgrade M3x15MM 300°C thermistor cartridge  
    - **Compatibility:** Dragonfly BMS BMO / Dragon Hotend, VORON V2.4, V0.1, V1.8 3D printers  
    - **Purpose:** Accurate temperature sensing for high-temp printing  
    - **Notes:** Ensure proper wiring and PID calibration  

- **Bed:** Magnetic PEI bed for improved adhesion and easier print removal.  
    - **Type:** Flexible, removable magnetic sheet  
    - **Surface:** PEI-coated  
    - **Notes:** Ensure proper Z-offset calibration after installation  

- **Filament Tubing:** **Capricorn PTFE tubing** for smoother filament feeding and higher-temp printing.  
    - **Type:** High-quality PTFE, low friction  
    - **Diameter:** 4mm ID, 6mm OD (standard for Ender 3)  
    - **Notes:** Recommended for PLA, PETG, ABS, and other high-temp filaments  

## Features
- Custom Klipper firmware configuration for the Ender 3  
- Optimized for SKR E3.0 board  
- Supports common Ender 3 upgrades:
  - **BLTouch auto bed leveling**  
  - **Filament sensors**  
  - **Phaetus Dragonfly Hotend BMS**  
  - **Magnetic PEI bed**  
- Macro scripts for common operations  
- Integration with **Fluidd/Mainsail** for web-based control  
- Tuned motion and temperature settings for improved print quality  

## Installation
1. Flash **SKR E3.0** with the appropriate Klipper firmware.  
2. Install **Klipper** on a Raspberry Pi or host machine.  
3. Upload configuration files to `~/klipper/config`.  
4. Configure BLTouch in `printer.cfg` (probe pin, offsets, bed mesh settings, dynamic probing).  
5. Restart Klipper and calibrate your printer (steps/mm, PID tuning, Z-offset, etc.).  
6. Access your printer via **Fluidd** or **Mainsail**.

> ⚠️ Always verify hardware connections and firmware settings before powering the printer.

## Planned Upgrades
Future enhancements to improve power management, cooling, and reliability. These will be implemented **when I have time**, and `.step` files will be uploaded **when possible**:

- **Mean Well Power Supply:** More stable and reliable power delivery for higher power demands.  
- **Custom Under-Printer PSU Shroud:** Safely houses the Mean Well PSU and improves cable management and airflow.  
- **Buck Converter for Raspberry Pi:** Powers the Pi from the printer's main supply for a clean single power source.  
- **Upgraded Enclosure with Noctua Fans:** Houses electronics, provides active cooling, reduces fan noise, and maintains stable temperatures.  
- **Filament Runout Sensor:** Detects filament depletion or breakage, pauses prints, and allows replacement without ruining the print.

> **Notes:** All upgrades will be implemented in stages, with proper calibration and safety checks.

## Notes
- This setup is tailored for my Ender 3 and may need adjustments for other printers.  
- Firmware files and configuration settings are provided as a reference.  
- Contributions and suggestions are welcome — use caution when applying changes to your own printer.  


## Resources / Datasheets
- [Klipper Documentation](https://www.klipper3d.org/)  
- [Fluidd Web Interface](https://docs.fluidd.xyz/)  
- [Mainsail Web Interface](https://docs-os.mainsail.xyz/)  
- [BIGTREETECH-SKR-mini-E3](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master)  
- [Dragonfly-BMS](https://github.com/Phaetus/Dragonfly-BMS)  
- [Ender-3](https://github.com/Creality3DPrinting/Ender-3)  
- [BLTouch](https://www.antclabs.com/bltouch)  
