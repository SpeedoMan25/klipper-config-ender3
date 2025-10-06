# Ender 3 Klipper Setup

## Overview
This repository contains my personal configuration and setup files for running **Klipper firmware** on an **Ender 3** with an **SKR-mini-E3 V3.0**. The goal of this project is to improve print quality, speed, and reliability by leveraging Klipper's advanced features.

> **Note:** This configuration uses a different stepper motor for the extruder. See the Hardware Modifications section for details.

## Hardware Modifications

This configuration is tailored for an Ender 3 with a variety of upgrades.

- **Extruder Motor:** The stock motor has been replaced with a `17HM19-2004S1` stepper motor [31]. Key specifications are listed below. You will need to adjust your `rotation_distance` and `run_current` in `printer.cfg` to match your specific extruder and this motor.
    - **Model:** 17HM19-2004S1 [31]
    - **Step Angle:** 0.90° [11]
    - **Holding Torque:** 0.46 Nm [11]
    - **Current:** 2.00 Amps/Phase [11]

## Features
- Custom Klipper firmware configuration for the Ender 3
- Optimized for SKR E3.0 board
- Supports common Ender 3 upgrades (BLTouch, filament sensors, etc.)
- Macro scripts for common operations
- Integration with **Fluidd/Mainsail** for web-based control
- Tuned motion and temperature settings for improved print quality

## Installation
1.  **Flash SKR E3.0** with the appropriate Klipper firmware.
2.  Install **Klipper** on a Raspberry Pi or other host machine.
3.  Upload the configuration files from this repository to the `~/klipper/config` directory.
4.  Restart Klipper and calibrate your printer (steps/mm, PID tuning, etc.).
5.  Access your printer via **Fluidd** or **Mainsail**.

> ⚠️ Always verify your hardware connections and firmware settings before powering the printer.

## Notes
- This setup is tailored for my specific Ender 3 configuration and may need adjustments for your printer.
- Firmware files and configuration settings are provided as a reference.
- Contributions and suggestions are welcome, but use caution when applying changes to your own printer.

## Resources
- [Klipper Documentation](https://www.klipper3d.org/)
- [Fluidd Web Interface](https://docs.fluidd.xyz/)
- [Mainsail Web Interface](https://docs-os.mainsail.xyz/)
- [BIGTREETECH-SKR-mini-E3](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master)
