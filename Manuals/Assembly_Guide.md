# 📘 ZeroG MercuryOne.1 + NebulaFrame 370 + Hydra Bed Assembly Guide

**Last Updated:** 2026  
**Author:** Thai Maker (Icezaza)  

This guide provides technical overview, system architecture, and assembly procedures for converting an Ender 5 series 3D printer into a high-speed CoreXY system using the ZeroG Mercury One.1 platform, NebulaFrame 370 enclosure, and Hydra 3-point kinematic Z-tilt bed leveling.

---

## 🏗️ 1. Project Overview

This project converts Ender 5 / Ender 5 Pro / Ender 5 Plus printers into high-speed CoreXY machines capable of print speeds exceeding **600 mm/s** and accelerations up to **20,000 mm/s²**, optimized for high-temperature engineering filaments like **ABS, ASA, and PC**.

**Key Core Pillars:**
1. **ZeroG Mercury One.1:** CoreXY motion system replacing single-axis X/Y movement, reducing toolhead weight for fast, precise motion.
2. **NebulaFrame 370:** Sealed enclosure frame maintaining ambient chamber temperatures to eliminate warping in high-shrinkage plastics (ABS/ASA/PC).
3. **Hydra Bed System:** 3-point kinematic Z-tilt mechanism driven by 3 independent Z stepper motors for 100% automated bed leveling.
4. **Klipper Firmware Ecosystem:** Advanced motion processing featuring Input Shaper resonance compensation, Pressure Advance, KAMP adaptive meshing, and ShakeTune diagnostics.

---

## 📂 2. Repository Structure

- **`BOM.md`**
  - Detailed Bill of Materials specifying hardware, fasteners, linear rails, belts, motors, and controller pinouts ([View BOM](../BOM.md)).
- **`Config/`**
  - Production Klipper configuration files including `printer.cfg`, `macros.cfg`, `KAMP_Settings.cfg`, `KlipperScreen.conf`, and `crowsnest.conf` ([Open Config Directory](../Config/)).
- **`Archives/`**
  - Compressed `.zip` archives containing original CAD models (`Hydra_5Plus.zip`, `Hydra_5pro.zip`, `Mercury1_1.zip`).
- **`File_To_Print/`**
  - Categorized 3D printable STL files:
    - `HydraBed/` - 3-motor Z-bed mounts & kinematic arms
    - `MercuryXY/` - CoreXY gantry, belt paths, and motor mounts
    - `Skirt/` - Electronics enclosures and lower frame skirts
    - `ToolsHead/` - Orbiter 2.0, Cartographer/Beacon 3D probe mounts, and 5015 fan ducts
- **`Manuals/`**
  - Official PDF instruction manuals and this markdown assembly guide.
- **`Media/`**
  - Test print videos (`Print_Test.mp4`) and build photography.

---

## 🛠️ 3. Pre-Assembly Guidelines

### 3D Printing Recommendations
All components in `File_To_Print/` are load-bearing structural parts operating in a heated chamber environment:
- **Recommended Materials:** ABS, ASA, or PC (PLA and PETG are not recommended due to heat deflection).
- **Perimeters / Walls:** Minimum **4 walls** (5 walls recommended for high-stress joints).
- **Infill Density:** **40%** (Gyroid, Grid, or Honeycomb).
- **Top / Bottom Solid Layers:** **5 layers**.

### Hardware Bill of Materials (BOM)
For exact quantities of M3/M4/M5 screws, brass heat-set inserts, linear rails, belts, and motor models, refer to 📖 **[BOM.md](../BOM.md)**.

---

## ⚙️ 4. Mechanical Assembly & Klipper Configuration

### 4.1 Part Preparation
1. Print all required parts from `File_To_Print/` according to the recommended print settings.
2. Install brass heat-set inserts (M3x5x4mm) into specified mounting holes using a soldering iron.
3. Cut 2020 aluminum extrusions and prepare acrylic/polycarbonate panels according to NebulaFrame 370 dimensions.

### 4.2 Mechanical Assembly
Follow the instructions in `mercury_one_1_instruction_18-02-2024.pdf` located in the `Manuals/` directory:
1. **CoreXY Gantry Installation:** Mount X and Y stepper motors to the frame and route GT2 belts in the CoreXY configuration.
2. **Hydra Bed Assembly:** Convert the stock bed platform to a 3-lead-screw kinematic mount driven by 3 independent Z steppers.
3. **Toolhead Assembly:** Assemble the Orbiter 2.0 extruder, BTT EBB36 CAN board, and probe onto the X-carriage.

### 4.3 Klipper Firmware Setup
1. Install Klipper on your host single-board computer (Raspberry Pi / CB1 running MainsailOS or FluiddPI).
2. Flash Klipper firmware to the main controller board (e.g., BigTreeTech Octopus Pro) and Toolhead MCU (EBB36).
3. Copy all files from the **[`Config/`](../Config/)** directory to your Klipper `printer_data/config/` folder:
   - **[`Config/printer.cfg`](../Config/printer.cfg)**: Configures TMC5160 X/Y drivers, TMC2209 Z steppers, Cartographer/Beacon probe, and bed mesh settings.
   - **[`Config/macros.cfg`](../Config/macros.cfg)**: Contains `PRINT_START`, `PRINT_END`, `CANCEL_PRINT`, and maintenance macros.

### 4.4 Machine Calibration
Execute calibration macros via the Klipper console:
- **Z-Tilt Leveling:** Run `Z_TILT_ADJUST` to automatically level the bed across all 3 Z steppers.
- **Bed Mesh:** Run `BED_MESH_CALIBRATE` (or rely on KAMP auto-mesh during `PRINT_START`).
- **Resonance Compensation:** Run `SHAKETUNE` or Input Shaper calibration using the ADXL345 accelerometer.
- **PID Tuning:** Run PID calibration for both hotend and heated bed (`PID_CALIBRATE`).

---

## 📌 5. Troubleshooting

- **Belt Friction / Binding:** Ensure smooth alignment of all 20T idlers and equal belt tension across A/B loops.
- **Z-Tilt Failures / Motor Binding:** Verify motor stepper assignments (`stepper_z`, `stepper_z1`, `stepper_z2`) and pivot point coordinates in `printer.cfg`.
- **Layer Shifting at High Speeds:** Check TMC5160 run currents (recommended 1.97A for LDO 0.9° steppers) and verify belt tensioning.

---

**⭐ For additional model modifications, CAD files are available in the `Archives/` folder.**
