<div align="center">

# 🚀 ZeroG MercuryOne.1 x NebulaFrame 370 x Hydra Bed

**Handmade by a Thai Maker 🇹🇭**

![CoreXY](https://img.shields.io/badge/Kinematics-CoreXY-red?style=for-the-badge)
![Klipper](https://img.shields.io/badge/Firmware-Klipper-blue?style=for-the-badge)
![Enclosure](https://img.shields.io/badge/Frame-Nebula_370-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT_%7C_CC_BY--NC--SA-green?style=for-the-badge)

</div>

---

## 📊 System Architecture

```mermaid
graph TD
    A[Ender 5 Platform] -->|Conversion| B(ZeroG Mercury One.1 CoreXY)
    B --> C{Key Upgrades}
    C -->|Frame & Enclosure| D[NebulaFrame 370]
    C -->|Bed System| E[Hydra 3-Point Z-Tilt Bed]
    C -->|Toolhead| F[Orbiter 2.0 + Dual 5015]
    
    E -->|Leveling| G[Auto Kinematic Leveling]
    F -->|Control| H[Klipper + Mainsail/Fluidd]
```

## ✨ Highlights

| ⚙️ Hardware / System | 📝 Description |
| :--- | :--- |
| ⚡ **Motion System** | CoreXY Kinematics (capable of >600mm/s speeds) |
| 🔥 **Bed Leveling** | Hydra 3-Point Z-Tilt Kinematic Bed System |
| 🏗️ **Enclosure** | NebulaFrame 370 (Rigid, optimized for ABS/ASA/PC) |
| 🛠️ **Toolhead** | Custom Mount + Orbiter 2.0 Extruder + Beacon 3D |

---

## 📂 Repository Map

```mermaid
mindmap
  root((Project))
    Archives
      [ZIP Packages]
      [Firmware Configs]
      [CAD Models]
    Documents
      [Build Reports]
      [Budget Details]
    File_To_Print
      (HydraBed)
      (MercuryXY)
      (Skirt)
      (ToolsHead)
    Manuals
      [คู่มือการประกอบ.md]
      [Instruction PDFs]
    Media
      [Test Print Videos]
```

---

## 🛠️ Quick Start

| Step | Action | Path/Folder |
| :---: | :--- | :--- |
| **1️⃣** | **อ่านคู่มือประกอบ** (Read the Guide) | 📖 `Manuals/คู่มือการประกอบโปรเจกต์.md` |
| **2️⃣** | **สั่งพิมพ์ชิ้นส่วนพลาสติก** (Print Parts)<br>*(แนะนำ ABS/ASA: 4 Walls, 40% Infill)* | 🖨️ `File_To_Print/` |
| **3️⃣** | **ประกอบชิ้นส่วน และโครงเครื่อง** (Assemble) | 🔧 *ดูตามคู่มือ PDF และไฟล์ CAD* |
| **4️⃣** | **ติดตั้งเฟิร์มแวร์ & คาลิเบรต** (Firmware) | 💾 `Archives/` (แตกไฟล์ ZIP เฟิร์มแวร์) |

---

<div align="center">

**🙌 Credits:** 
[ZeroG Community](https://github.com/ZeroGDesign) | Thai Maker Community

*⭐ If you like this project, please give it a star!*

</div>
