# Ender 3 Klipper Setup

## Overview
This repository contains my personal configuration and setup files for running **Klipper firmware** on an **Ender 3** with an **SKR E3.0 board**. The goal of this project is to improve print quality, speed, and reliability by leveraging Klipper's advanced features.

## Features
- Custom Klipper firmware configuration for the Ender 3
- Optimized for SKR E3.0 board
- Supports common Ender 3 upgrades (BLTouch, filament sensors, etc.)
- Macro scripts for common operations
- Integration with **Fluidd/Mainsail** for web-based control
- Tuned motion and temperature settings for improved print quality

## Installation
1. **Flash SKR E3.0** with the appropriate Klipper firmware.
2. Install **Klipper** on a Raspberry Pi or other host machine.
3. Upload the configuration files from this repository to the `~/klipper/config` directory.
4. Restart Klipper and calibrate your printer (steps/mm, PID tuning, etc.).
5. Access your printer via **Fluidd** or **Mainsail**.

> ⚠️ Always verify your hardware connections and firmware settings before powering the printer.

## Notes
- This setup is tailored for my specific Ender 3 configuration and may need adjustments for your printer.
- Firmware files and configuration settings are provided as a reference.
- Contributions and suggestions are welcome, but use caution when applying changes to your own printer.

## Resources
- [Klipper Documentation](https://www.klipper3d.org/)
- [Fluidd Web Interface](https://docs.fluidd.xyz/)
- [Mainsail Web Interface](https://get.mainsail.xyz/)
