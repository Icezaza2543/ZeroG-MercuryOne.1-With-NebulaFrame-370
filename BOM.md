# 🔩 Bill of Materials (BOM) - ZeroG MercuryOne.1 x NebulaFrame 370 x Hydra Bed

**Project:** ZeroG Mercury One.1 CoreXY Conversion + NebulaFrame 370 + Hydra Bed  
**Author:** Thai Maker (Icezaza)  
**Target Printer Platform:** Ender 5 / Ender 5 Pro / Ender 5 Plus  

---

## 📑 1. Core Electronics & Hardware Specs

| Category | Component | Specification / Model | Qty | Notes |
| :--- | :--- | :--- | :---: | :--- |
| **Main Controller** | Mainboard | BigTreeTech Octopus Pro (STM32H723) | 1 | 32-bit controller, high-speed USB/CAN |
| **Toolhead MCU** | Toolhead CAN Board | BTT EBB36 v1.1 / v1.2 (CANbus) | 1 | Mounts directly on Orbiter 2.0 |
| **Host System** | Single Board Computer | Raspberry Pi 3/4 / CB1 | 1 | Runs Klipper, Mainsail, Moonraker |
| **X/Y Steppers** | High-Speed Motors | LDO-42STH48-2804AH-R (2.8A, 0.9°) | 2 | CoreXY Motion (Driven by TMC5160 @ 1.97A) |
| **Z Steppers** | Hydra Bed Motors | NEMA17 (42DND887C-20D18 1.7A) | 3 | 3-Point Independent Z-Tilt Kinematic Bed |
| **X/Y Drivers** | Stepper Drivers | BTT TMC5160 Pro / TMC5160 (SPI) | 2 | High current & high speed motion |
| **Z Drivers** | Stepper Drivers | BTT TMC2209 (UART) | 3 | Quiet operation with stealthChop/spreadCycle |
| **Toolhead Extruder**| Extruder | Orbiter 2.0 Dual Drive | 1 | Lightweight direct-drive extruder |
| **Surface Probe** | 3D Bed Scanner | Cartographer 3D / Beacon 3D Probe | 1 | High-speed Eddy Current Surface Scanner |
| **Part Cooling** | Blower Fan | 5015 Dual Ball Bearing Fan (24V) | 1 | Single/Dual 5015 Duct Mount |
| **Hotend Fan** | Cooling Fan | 3010 Axial Fan (24V) | 1 | EBB36 Toolhead Cooling |
| **Resonance Test** | Accelerometer | ADXL345 (Integrated on EBB36) | 1 | Input Shaper Calibration |

---

## 🏗️ 2. Mechanical & Linear Motion (Kinematics)

| Component | Specification | Qty | Notes |
| :--- | :--- | :---: | :--- |
| **Linear Rails (X-Axis)** | MGN12H (300mm / 350mm / 450mm based on Ender model) | 1 | Heavy-duty top-rail carriage mount |
| **Linear Rails (Y-Axis)** | MGN12H | 2 | Side rail positioning |
| **Linear Rails (Z-Axis)** | MGN12H | 3 | Hydra 3-point vertical guides |
| **GT2 Belt (X/Y)** | GT2 6mm or 9mm Gates Unitta Belt | ~4.5m | CoreXY belt loop routing |
| **Pulleys (Toothed)** | 20T GT2 Pulley (5mm bore) | 2 | X/Y Stepper Motor Shafts |
| **Idlers (Smooth)** | 20T Smooth Idler (5mm bore) | 6 | Gantry corner & tensioners |
| **Idlers (Toothed)** | 20T Toothed Idler (5mm bore) | 8 | Gantry corner & tensioners |
| **Lead Screws** | T8x4 / T8x8 Lead Screw + Anti-backlash Nut | 3 | Hydra Z-Axis motor drives |

---

## 🔩 3. Fasteners & Brass Inserts (Hardware BOM)

| Fastener Type | Dimensions | Approximate Qty | Application |
| :--- | :--- | :---: | :--- |
| **Heat-Set Inserts** | M3 x 5mm x 4mm (Brass) | 60+ | All 3D Printed Parts |
| **Button Head Screws**| M3 x 6mm | 40+ | Rail mounting & brackets |
| **Button Head Screws**| M3 x 8mm | 50+ | Frame & component mounts |
| **Button Head Screws**| M3 x 12mm | 30+ | Motor mounts & joints |
| **Button Head Screws**| M3 x 16mm / 20mm | 20+ | Toolhead & fan mounts |
| **Socket Head Screws**| M4 x 10mm / 12mm | 20+ | Frame extrusions |
| **Socket Head Screws**| M5 x 10mm / 16mm | 16+ | Corner brackets & bed mounts |
| **T-Nuts** | M3 T-Nuts for 2020 Aluminum Profile | 50+ | Rail & skirt mounting |
| **T-Nuts** | M4 / M5 T-Nuts for 2020 Profile | 30+ | Heavy joint mounting |

---

## 🖼️ 4. Frame & Enclosure (NebulaFrame 370)

| Material | Description / Dimensions | Qty | Application |
| :--- | :--- | :---: | :--- |
| **Aluminum Extrusions** | 2020 T-Slot Aluminum Profile | Cut to spec | Upper frame expansion & enclosure |
| **Enclosure Panels** | Acrylic or Polycarbonate Panels (3mm - 4mm) | 5 Sheets | Top, Sides, Front Doors for ABS/PC printing |
| **Insulation / Skirt** | 3D Printed Skirts (`File_To_Print/Skirt`) | 1 Set | Bottom enclosure & electronics housing |

---

## 🖨️ 5. Recommended 3D Printing Settings for Parts

| Parameter | Value |
| :--- | :--- |
| **Material** | **ABS** or **ASA** (Polycarbonate optional for high ambient temp) |
| **Wall Loops / Perimeters** | Minimum **4 Walls** (5 recommended for stress joints) |
| **Top / Bottom Layers** | **5 Solid Layers** |
| **Infill Density** | **40%** |
| **Infill Pattern** | Gyroid, Grid, or Honeycomb |
| **Layer Height** | 0.2mm |

---

<div align="center">
  <b>For Klipper Configuration files, please refer to the <a href="Config/">Config/</a> directory.</b>
</div>
