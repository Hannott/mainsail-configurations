# Mainsail / Klipper Configuration — Flashforge Guider 2S (High Temperature)

This repository contains a complete, modular Klipper + Mainsail configuration
for a **heavily modified Flashforge Guider 2S High Temperature (HT / 2020)**.

The focus of this configuration is **predictable behavior, low noise, and operational safety**,
with performance available through explicitly selected modes.

---

## ⚠️ Disclaimer

This configuration is **printer-specific** and targets the **Guider 2S High Temperature (HT)** model.

There exists a non-HT Guider 2S variant which differs primarily in the **extruder and hotend design**.
Users of the non-HT model must adapt all extruder-related configuration accordingly.

This configuration assumes:
- Flashforge Guider 2S **High Temperature (HT / 2020)**
- Optical endstops
- TMC2209 stepper drivers (UART)
- Custom wiring, pin aliases, and safety logic

**Do not apply this configuration to another printer without adaptation.**

---

## Design Goals

- Quiet operation by default
- Deterministic and explicit motion behavior
- Safety mechanisms layered on top of physical endstops
- Clear separation between motion, safety, UI, and print lifecycle logic
- Modular, readable configuration structure

Performance is available, but never implicit.

---

## Features

- Multiple selectable motion modes  
  *(Silent / Quiet / Performance / Push)*

- Stall-protected Z axis  
  - Safe homing  
  - Safe manual jogging  
  - Emergency stop behavior on obstruction

- Explicit XY jogging macros  
  - No accidental Z motion  
  - Touch-friendly Mainsail UI integration

- Firmware-based retraction  
  - `G10 / G11` support  
  - Centralized extrusion behavior

- Optical endstops as positional authority

- Input shaping support via external accelerometer

- Touch-optimized Mainsail dashboard  
  *(4.3″ DSI display)*

---

## Repository Structure

- `printer.cfg`  
  Root include file (no hardware values)

- `kinematics.cfg`  
  Global motion limits and kinematic assumptions

- `stepper_*.cfg`, `tmc_drivers.cfg`  
  Motor and driver configuration

- `macros_*.cfg`  
  Motion modes, homing, jogging, safety, and print lifecycle logic

- `ui.cfg`, `buttons.cfg`  
  Mainsail UI behavior and physical controls

All configuration files include a **GPL-v3 license header**.

---

## License

This project is licensed under the  
**GNU General Public License v3.0**.

You are free to use, modify, and redistribute this configuration under the
terms of the GPL-v3 license.

---

## Status

This repository is a **work in progress**.

Configuration, tuning, and validation are ongoing.
Changes and refactors should be expected.

---

## Author

Maintained by **Hannott**  
Published primarily for reference and learning.
