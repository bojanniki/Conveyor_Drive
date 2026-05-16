# Conveyor Drive – Single-Stage Gearbox

Design and documentation of a single-stage spur gear reducer for driving a conveyor belt.

---

## Project Description

The project covers the complete engineering development of a compact parallel-shaft
gearbox, from initial requirements through to final documentation. The gearbox
transforms the high-speed motion of a standard AC motor (1800 RPM) into slower,
higher-torque motion (450 RPM) suitable for driving a conveyor.

---

## Technical Specifications

| Parameter | Value |
|:----------|:------|
| Power | 250 W |
| Input speed | 1800 RPM |
| Output speed | 450 RPM |
| Gear ratio | 4:1 |
| Gear module | m = 1.5 |
| Gear pair | z₁ = 18 / z₂ = 72 |
| Centre distance | 67.5 mm |
| Shaft diameter | ø 12 mm |
| Total mass | ~4.83 kg |
| Efficiency | 98% |

---

## Safety Factors

| Check | Result | Status |
|:------|:-------|:-------|
| Gear ratio | 4:1 | ✅ |
| Contact ratio ε_α | 1.67 > 1.2 | ✅ |
| Tooth fracture safety S_F | 14.1 > 1.2 | ✅ |
| Pitting safety S_H | 2.11 > 1.2 | ✅ |
| Shaft safety | 2.66 > 1.2 | ✅ |
| Key safety | 1.38 > 1.2 | ✅ |
| Bearing life L₁₀ | 227,000 h | ✅ |

---

## Project Structure

```
Conveyor_Drive/
│
├── CAD Models/
│   └── Solid Edge assembly (.asm)
│
├── Documentation/
│   ├── Housing – lower part
│   ├── Housing – upper part
│   ├── Bearing cover – universal
│   ├── Driving gear (z=18)
│   ├── Driven gear (z=72)
│   └── Shaft – universal
│
├── Calculations/
│   └── Conveyor_Drive.ipynb
│
└── README.md
```

---

## Bill of Materials (BOM)

| Pos. | Name | Material | Qty. |
|:-----|:-----|:---------|-----:|
| 1 | Housing – lower part | EN-GJL-250 | 1 |
| 2 | Driving gear (z=18) | Steel 40Cr GOST 4543-71 | 1 |
| 3 | Driven gear (z=72) | Steel 40Cr GOST 4543-71 | 1 |
| 4 | Shaft – universal | Steel 10 GOST 1050-88 | 2 |
| 5 | Spacer sleeve | Steel 10 GOST 1050-88 | 2 |
| 6 | Bearing 6201-2RS | Stainless steel | 4 |
| 7 | Retaining ring DIN 471 12x1 | Steel 55 GOST 1050-88 | 4 |
| 8 | Key DIN 6885 A 4x4x12 | Steel C45 | 2 |
| 9 | Housing – upper part | EN-GJL-250 | 1 |
| 10 | Grease fitting DIN 71412 M6 | Steel | 1 |
| 11 | Bolt DIN 912 M5x20 | Steel | 8 |
| 12 | Washer DIN 125 M5 | Steel | 16 |
| 13 | Nut DIN 985 M5 | Steel | 8 |
| 14 | Pin DIN 6325 4x14 | Tool Steel 115CrV3 | 2 |
| 15 | Bearing cover – universal | EN-GJL-250 | 2 |
| 16 | Bolt DIN 912 M3x10 | Steel | 8 |
| 17 | Gasket DIN 7603 A M8 | Copper | 1 |
| 18 | Bolt DIN 933 M8x10 | Steel | 1 |

---

## Heat Treatment

| Component | Process | Hardness |
|:----------|:--------|:---------|
| Gears (pos. 2, 3) | Quench and temper | 28-35 HRC |
| Shaft (pos. 4) | Induction hardening of bearing seats | 45-55 HRC (surface) |

---

## Standards

- **ISO 1328** – Gear tolerances
- **ISO 2768-m** – General tolerances
- **ISO 281** – Bearing service life
- **DIN 3966** – Gear data on technical drawings
- **DIN 6885** – Keys
- **DIN 471** – Retaining rings
- **DIN 6325** – Cylindrical pins

---

## Software

| Software | Purpose |
|:---------|:--------|
| Solid Edge 2024 | 3D modelling and 2D drawings |
| Python 3.12 | Technical calculation |
| Jupyter Notebook | Calculation documentation |

---

## Author

**Bojan Nikić**
Date: 2026.

---

*Personal engineering project.*
