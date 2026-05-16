# Conveyor Drive Project

---

## 1. Project Introduction

This project covers the design and documentation of a single-stage spur gear
reducer intended for driving a conveyor belt.

### 1.1. Project Brief

The design task involves creating a compact gearbox with parallel shafts that
transforms the high-speed motion of a standard AC motor into slower,
higher-torque motion suitable for driving a conveyor.

### 1.2. Scope of Documentation

In accordance with the project brief, the deliverables include:
- **3D Assembly** – complete model in Solid Edge with assembly constraints
- **2D Drawings** – detailed drawings of all non-standard parts with tolerances
- **Gear Table** – per DIN 3966 for both gears
- **Bill of Materials (BOM)** – all 18 components of the assembly
- **Technical Calculation** – validation per ISO standards

### 1.3. Final Design

The initial calculation yielded a non-standard module of m = 1.38, which was
rejected in favour of the standard **m = 1.5**. The final design uses the
standardised gear pair **z₁ = 18 / z₂ = 72**, ensuring an exact gear ratio
of **4:1** and a centre distance of **67.5 mm**.

The housing is made from grey cast iron **EN-GJL-250**, while the gears and
shafts are made from steel suitable for heat treatment. Sealing is achieved
with gasket paper on all mating surfaces, and lubrication is provided via a
central grease fitting.

---

## 2. Design Requirements and Definitions

### 2.1. Design Requirements

| Symbol | Parameter | Value |
|:-------|:----------|:------|
| P | Power | 250 W |
| $n_1$ | Input speed | 1800 RPM |
| $n_2$ | Output speed | 450 RPM (4:1 reduction) |
| – | Configuration | Parallel shafts |

### 2.2. Key Engineering Parameters and Definitions

The following parameters are essential for understanding the gear transmission
design and directly affect system performance and service life:

* **Module ($m$):** The fundamental measure of tooth size and the most important standardised parameter. Defined as the ratio of the pitch diameter to the number of teeth ($m = d/z$). All meshing gears must have an identical module.
* **Pitch diameter ($d$):** The theoretical diameter at which two gears roll against each other without slipping. This is the reference line for all other geometric calculations.
* **Centre distance ($a$):** The shortest distance between the shaft centrelines of the driving and driven gears. Critical for accurate housing design.
* **Contact ratio ($\epsilon_\alpha$):** A number indicating the average number of tooth pairs simultaneously in contact. For smooth, quiet operation without impact, this value should exceed $1.2$.
* **Root stress ($\sigma_F$):** The critical bending stress at the tooth root caused by the tangential force. If this stress exceeds allowable limits, tooth fracture may occur.
* **Hertzian contact stress ($\sigma_H$):** The pressure at the tooth flank contact surfaces. This governs the occurrence of **pitting** (surface fatigue).
* **Safety factors ($S_F, S_H$):** The ratio of the material's maximum allowable stress to the actual working stress. In mechanical engineering, values above $1.2$ are targeted to ensure reliability under unexpected operating conditions.

---

## 3. Technical Calculation of the Transmission

This section contains the mathematical analysis and validation of the gear
transmission per ISO standards, consistent with results obtained from the
*Solid Edge Engineering Reference* module.

---

### 3.1. Input Parameters (Drive Specifications)

These values define the operating conditions of the machine.

| Variable | Name | Value | Description |
| :--- | :--- | :--- | :--- |
| $P$ | **Power** | **250 W** | Rated power of the drive motor. |
| $n_1$ | **Input speed** | **1800 RPM** | Rotational speed of the input shaft. |
| $n_2$ | **Output speed** | **450 RPM** | Designed output speed of the gearbox. |
| $\eta$ | **Efficiency** | **0.98** | Loss factor (meshing and bearings). |
| $\alpha$ | **Pressure angle** | **20°** | Standard tooth profile pressure angle. |

---

### 3.2. Kinematics and Torques

Transformation of motion and forces within the transmission for the
standardised gear pair $18/72$.

* **Gear ratio ($i$):**
  $$i = \frac{z_2}{z_1} = \frac{72}{18} = 4.0$$
* **Angular velocity ($\omega_1$):**
  $$\omega_1 = \frac{2 \cdot \pi \cdot 1800}{60} = 188.5 \text{ rad/s}$$
* **Torque on pinion ($T_1$):**
  $$T_1 = \frac{P}{\omega_1} = \frac{250}{188.5} = 1.33 \text{ Nm}$$

---

### 3.3. Gear Geometry

Final dimensions adjusted to the standard module $m = 1.5$.

* **Module ($m$):** **1.5 mm** (Standard profile)
* **Pitch diameters ($d$):**
  $$d_1 = m \cdot z_1 = 27.0 \text{ mm}$$
  $$d_2 = m \cdot z_2 = 108.0 \text{ mm}$$
* **Centre distance ($a$):**
  $$a = \frac{d_1 + d_2}{2} = 67.5 \text{ mm}$$
* **Pitch line velocity ($v$):**
  $$v = \frac{d_1 \cdot \pi \cdot n_1}{60000} = 2.54 \text{ m/s}$$

---

### 3.4. Contact Ratio ($\epsilon_\alpha$)

The contact ratio indicates how many tooth pairs are simultaneously in mesh.
For smooth, quiet operation, **ε_α > 1.2** is required.

#### Formula:

$$\epsilon_\alpha = \frac{1}{2\pi} \left[ z_1 \cdot (\tan\alpha_{a1} - \tan\alpha') + z_2 \cdot (\tan\alpha_{a2} - \tan\alpha') \right]$$

Where:
- **α' = 20°** – pressure angle (standard profile)
- **α_a1, α_a2** – tip circle pressure angles of pinion and gear

#### Tip Circle Pressure Angles:

$$\alpha_{a1} = \arccos\left(\frac{r_1 \cdot \cos\alpha'}{r_{a1}}\right) = 32.25°$$

$$\alpha_{a2} = \arccos\left(\frac{r_2 \cdot \cos\alpha'}{r_{a2}}\right) = 23.89°$$

#### Calculation:

$$\epsilon_\alpha = \frac{1}{2\pi} \left[ 18 \cdot (\tan 32.25° - \tan 20°) + 72 \cdot (\tan 23.89° - \tan 20°) \right]$$

$$\epsilon_\alpha \approx 1.67$$

#### Conclusion:

A contact ratio of **ε_α = 1.67** means that on average **1.67 tooth pairs**
are simultaneously in mesh, which exceeds the minimum of **1.2** and ensures:
- ✅ Smooth and quiet operation without impact
- ✅ Even load distribution
- ✅ Extended tooth service life

---

### 3.5. Gear Forces

Mechanical loads derived from torque $T_1$.

* **Tangential force ($F_t$):**
  $$F_t = \frac{2000 \cdot T_1}{d_1} = 98.5 \text{ N}$$
* **Radial force ($F_r$):**
  $$F_r = F_t \cdot \tan(20^\circ) = 35.8 \text{ N}$$

---

### 3.6. Shaft Design and Diameter Selection

Based on the output torque $T_2 = T_1 \cdot i \cdot \eta \approx 5.3 \text{ Nm}$
and gear forces, the minimum shaft diameter is determined.

* **Allowable shear stress ($\tau_{t, allow}$):** **40 MPa** (C45 material per Decker's table for transmission shafts).
* **Theoretical minimum diameter ($d_{min}$):**
  $$d_{min} = \sqrt[3]{\frac{T_2}{0.2 \cdot \tau_{t, allow}}} = \sqrt[3]{\frac{5300 \text{ Nmm}}{0.2 \cdot 40}} \approx 8.72 \text{ mm}$$
* **Design selection:** A unified diameter of **12.0 mm** is adopted for both shafts.
  * **Rationale:** Compensation for cross-section weakening due to the keyway (DIN 6885) and standardisation with the **6201** bearing series.

---

### 3.7. Shaft-Hub Connection Design and Validation (Key)

The key connection per **DIN 6885** is selected to transfer torque from the
shaft to the gears. The calculation is based on checking the surface pressure
on the key flanks per **Decker**.

#### 3.7.1. Geometry and Component Selection

Based on the adopted shaft diameter $d = 12 \text{ mm}$, standard key dimensions are selected:

| Symbol | Description | Value [mm] | Source |
| :--- | :--- | :--- | :--- |
| $b$ | Key width | 4 | DIN 6885 |
| $h$ | Key height | 4 | DIN 6885 |
| $L$ | Total length | 12 | Selected (gear width 15 mm) |
| $t_1$ | Keyway depth in shaft | 2.5 | DIN 6885 |
| $t_2$ | Keyway depth in hub | 1.8 | DIN 6885 |

#### 3.7.2. Calculation Parameters

The calculation is performed for the critical output shaft where loading is greatest.

* **Torque ($T$):** $5.3 \text{ Nm} = 5300 \text{ Nmm}$
* **Shaft diameter ($d$):** $12 \text{ mm}$
* **Active flank height ($h - t_1$):** $4 \text{ mm} - 2.5 \text{ mm} = 1.5 \text{ mm}$
* **Bearing length ($l_t$):** $L - b = 12 \text{ mm} - 4 \text{ mm} = 8 \text{ mm}$ (Form A key)
* **Allowable pressure ($p_{allow}$):** $\approx 100 \text{ MPa}$ (C45 material per Decker)

#### 3.7.3. Surface Pressure Check

$$p = \frac{2 \cdot T}{d \cdot (h - t_1) \cdot l_t} = \frac{2 \cdot 5300}{12 \cdot 1.5 \cdot 8} \approx \mathbf{73.61 \text{ MPa}}$$

#### 3.7.4. Conclusion

Since $p = 73.61 \text{ MPa} < p_{allow} = 100 \text{ MPa}$:

1. **The selected key DIN 6885 - A 4 x 4 x 12 fully satisfies the strength requirements.**
2. **A load reserve of approx. 26% ensures stable operation under dynamic loading.**
3. **Keyway dimensions $t_1 = 2.5 \text{ mm}$ and $t_2 = 1.8 \text{ mm}$ were used in the Solid Edge model.**

---

### 3.8. Bearing Selection and Calculation

#### 3.8.1. Bearing Configuration

The gearbox uses **4 bearings** arranged symmetrically:
- 2 bearings on the input shaft (pinion, $n_1$ = 1800 RPM)
- 2 bearings on the output shaft (gear, $n_2$ = 450 RPM)

Bearing span on each shaft: **L = 67.5 mm**
Gears are positioned **centrally between the bearings** (symmetrically).

#### 3.8.2. Bearing Loads

Since the gear is centrally positioned, the load is distributed equally between
both bearings on the same shaft:

$$F_{res} = \sqrt{F_t^2 + F_r^2} = \sqrt{98.5^2 + 35.8^2} \approx 104.8 \text{ N}$$

$$F_{bearing} = \frac{F_{res}}{2} \approx 52.4 \text{ N}$$

#### 3.8.3. Bearing Selection – 6201-2RS

Based on the shaft diameter **d = 12 mm**, a standard deep groove ball bearing is selected:

| Parameter | Value |
|:----------|:------|
| Designation | 6201-2RS |
| Bore diameter | 12 mm |
| Outer diameter | 32 mm |
| Width | 10 mm |
| Dynamic load rating (C) | 6.82 kN |
| Static load rating (C₀) | 3.05 kN |
| Sealing | 2RS (rubber seals both sides) |

**Rationale for 2RS selection:** The bearing comes factory-greased and sealed on
both sides – ideal for use with a central grease fitting without additional shaft seals.

#### 3.8.4. Bearing Service Life (L10)

Calculation per **ISO 281**:

$$L_{10} = \left(\frac{C}{F}\right)^3 \cdot \frac{10^6}{60 \cdot n}$$

**Critical bearing – input shaft (1800 RPM):**
$$L_{10} = \left(\frac{6820}{52.4}\right)^3 \cdot \frac{10^6}{60 \cdot 1800} \approx 227{,}000 \text{ hours}$$

**Output shaft bearing (450 RPM):**
$$L_{10} = \left(\frac{6820}{52.4}\right)^3 \cdot \frac{10^6}{60 \cdot 450} \approx 908{,}000 \text{ hours}$$

#### 3.8.5. Conclusion

The calculated service life far exceeds the standard **20,000 hours** for
industrial applications. The **6201-2RS** bearing is conservatively oversized
for this load, which is a deliberate decision due to:
- Low cost of a standard bearing
- Easy sourcing and replacement
- Additional safety margin for conveyor start-up torques

---

### 3.9. Strength Analysis and Safety Factors

Comparison of actual stresses against allowable limits for **C45 steel (normalised)**.

#### A. Tooth Root Safety ($S_F \approx 14.1$)

Calculated root stress is **14.18 N/mm²**.
* **Analysis:** Since the allowable stress for C45 is $\sigma_{F, allow} = 200 \text{ N/mm²}$, the safety factor is exceptionally high.
* **Conclusion:** The design is immune to fatigue tooth fracture at rated load and start-up torques.

#### B. Pitting Safety ($S_H \approx 2.1$)

Hertzian contact stress on the tooth flanks is **260.72 N/mm²**.
* **Analysis:** The stress is below the material's endurance limit ($\sigma_{H, allow} = 550 \text{ N/mm²}$).
* **Significance:** A factor of **2.1** confirms the system will have a long service life without surface fatigue (pitting), which is critical for precise conveyor operation.

---

## 4. Heat Treatment of Components

### 4.1. Overview and Requirements

Heat treatment is essential for achieving the required strength and service life
of critical gearbox components. Based on load analysis and selected materials,
the following requirements are defined:

### 4.2. Gears (pos. 2 and 3) – Steel 42Cr4

**Process: Quench and Temper (Improvement)**

This process is selected as it provides the optimal balance between:
- Surface hardness (resistance to pitting and wear)
- Core toughness (resistance to tooth fracture under impact loading)

| Parameter | Value |
|:----------|:------|
| Process | Quenching + Tempering |
| Quenching medium | Oil |
| Quenching temperature | 850°C |
| Tempering temperature | 550°C |
| Target hardness | 28-35 HRC |

**Rationale:** At a pitch line velocity of v = 2.54 m/s and safety factor
$S_H$ = 2.11, case hardening is not required. Quench and temper to 28-35 HRC
is economical and sufficient for the rated power of 250 W.

**Drawing note:**
```
HEAT TREATMENT: IMPROVE (QUENCH + TEMPER)
HARDNESS: 28-35 HRC
```

### 4.3. Shafts (pos. 4) – Steel C45E

**Process: Induction Hardening of Seats**

Induction hardening is applied selectively only to:
- Bearing seats (ø12 k6)
- Keyway

| Parameter | Value |
|:----------|:------|
| Process | Induction hardening |
| Surface hardness | 45-55 HRC |
| Hardened layer depth | 1.0-1.5 mm |
| Core hardness | 20-25 HRC |

**Rationale:** The core remains tough for torque transmission, while the
hard surface ensures wear resistance at critical bearing contact points.

**Drawing note:**
```
HEAT TREATMENT: INDUCTION HARDENING ON BEARING SEATS AND KEYWAY
SURFACE HARDNESS: 45-55 HRC
CORE HARDNESS: 20-25 HRC
```

### 4.4. Components Not Requiring Heat Treatment

| Component | Material | Reason |
|:----------|:---------|:-------|
| Housing (pos. 1, 9) | EN-GJL-250 | Cast iron – not suitable for HT |
| Covers (pos. 15) | EN-GJL-250 | Same |
| Bearings (pos. 6) | – | Factory treated |
| Bolts, nuts | – | Standard parts |
| Pins (pos. 14) | 115CrV3 | Already hardened (~60 HRC) |

---

## 5. Bill of Materials (BOM)

### 5.1. Complete Parts List

| Pos. | Name | Material | Mass [kg] | Qty. |
|:-----|:-----|:---------|----------:|-----:|
| 1 | Housing – lower part | EN-GJL-250 | 1.719 | 1 |
| 2 | Driving gear (z=18) | Steel - Alloyed:1.7045 , 42Cr4 | 0.052 | 1 |
| 3 | Driven gear (z=72) | Steel - Alloyed:1.7045 , 42Cr4 | 0.912 | 1 |
| 4 | Shaft – universal | Steel - Unalloyed:1.1191 , C45E | 0.077 | 2 |
| 5 | Spacer sleeve | Steel - Structural:1.0037 , S235JR | 0.010 | 2 |
| 6 | Bearing 6201-2RS | Stainless steel | 0.053 | 4 |
| 7 | Retaining ring DIN 471 12x1 | Steel - Unalloyed:1.1221 , C60E | 0.001 | 4 |
| 8 | Key DIN 6885 A 4x4x12 | Steel C45 | 0.001 | 2 |
| 9 | Housing – upper part | EN-GJL-250 | 1.603 | 1 |
| 10 | Grease fitting DIN 71412 M6 | Steel - Structural:1.0037 , S235JR | 0.003 | 1 |
| 11 | Bolt DIN 912 M5x20 | Steel | 0.005 | 8 |
| 12 | Washer DIN 125 M5 | Steel | 0.000 | 16 |
| 13 | Nut DIN 985 M5 | Steel | 0.001 | 8 |
| 14 | Pin DIN 6325 4x14 | Tool Steel 115CrV3 | 0.001 | 2 |
| 15 | Bearing cover – universal | EN-GJL-250 | 0.041 | 2 |
| 16 | Bolt DIN 912 M3x10 | Steel | 0.001 | 8 |
| 17 | Gasket DIN 7603 A M8 | Copper | 0.001 | 1 |
| 18 | Bolt DIN 933 M8x10 | Steel | 0.009 | 1 |

### 5.2. Total Assembly Mass

| Category | Mass [kg] |
|:---------|----------:|
| Housing (pos. 1, 9, 15) | 3.405 |
| Gears (pos. 2, 3) | 0.964 |
| Shafts and sleeves (pos. 4, 5) | 0.174 |
| Bearings (pos. 6) | 0.212 |
| Fasteners (pos. 7, 8, 11-18) | 0.076 |
| **TOTAL** | **~4.831 kg** |

### 5.3. Standard Parts

The following parts are sourced as standard catalogue items and require no
custom manufacture:

- Bearings 6201-2RS – SKF, FAG or equivalent
- Key DIN 6885 A 4x4x12 (Steel C45)
- Retaining rings DIN 471 12x1
- Pins DIN 6325 4x14 (115CrV3)
- Bolts DIN 912 M5x20 and M3x10
- Nut DIN 985 M5
- Washer DIN 125 M5
- Grease fitting DIN 71412 M6
- Gasket DIN 7603 A M8 (copper)
- Bolt DIN 933 M8x10

---

## 6. Final Design Assessment

The standardised system design ($m=1.5, z=18/72$) is rated as **highly reliable**.

### 6.1. Engineering Iteration and Standardisation

A key engineering optimisation was carried out during the design process.
Initial calculations yielded a non-standard **module $m = 1.38$**. Although
theoretically correct, this was rejected in favour of the **standard module $m = 1.5$**.

This transition achieved:
* **Economy:** Use of off-the-shelf gears significantly reduces manufacturing cost and lead time.
* **Maintainability:** Fast and simple part replacement is ensured in case of servicing.
* **Geometric accuracy:** The designed centre distance of **67.5 mm** and precise gear ratio of **4:1** ($z_1 = 18, z_2 = 72$) are maintained.

### 6.2. Static and Dynamic Safety

Tooth root stress analysis confirmed high fracture safety. For the selected
material **C45 steel (normalised)**, the calculated stress is well below the
allowable $200 \text{ N/mm²}$. The bending safety factor ($S_F \approx 14.1$)
guarantees resistance to sudden overloads.

### 6.3. Wear Resistance (Pitting)

The contact stress safety factor **$S_H \approx 2.1$** confirms system stability
against surface fatigue (pitting), which is critical for long-term operation
at 1800 RPM.

### 6.4. Performance and Accuracy

The selected **ISO quality grade 8** ensures an optimal balance between
manufacturing cost and operational quality. The contact ratio
$\epsilon_\alpha = 1.67$ ensures continuous meshing and smooth, quiet operation.

**Final assessment:** The designed gear transmission fully satisfies the
technical, economic and safety criteria.

---

## 7. References

### 7.1. Standards

| Standard | Description |
|:---------|:------------|
| **ISO 1328** | Tolerances for cylindrical gears |
| **ISO 2768-m** | General tolerances – medium class |
| **ISO 281** | Bearing service life calculation |
| **DIN 3966** | Gear data indication on technical drawings |
| **DIN 6885** | Keys – forms and dimensions |
| **DIN 471** | Retaining rings for shafts |
| **DIN 6325** | Cylindrical pins – m6 tolerance |
| **DIN 71412** | Grease fittings – dimensions and types |
| **DIN 7603** | Sealing rings – copper and aluminium |
| **DIN 912** | Socket head cap screws |
| **DIN 933** | Hex head bolts |
| **DIN 985** | Self-locking nuts |
| **DIN 125** | Washers |

### 7.2. Technical Literature

| Author | Title | Publisher |
|:-------|:------|:----------|
| **Decker, K.H.** | Maschinenelemente | Hanser Verlag |
| **Shigley, J.E.** | Mechanical Engineering Design | McGraw-Hill |
| **Niemann, G.** | Maschinenelemente Band 2 | Springer |

### 7.3. Software

| Software | Version | Purpose |
|:---------|:--------|:--------|
| **Solid Edge** | 2024 | 3D modelling and 2D drawings |
| **Python** | 3.x | Technical calculation |
| **Jupyter Notebook** | – | Calculation documentation |

### 7.4. Catalogues

- **SKF Bearing Catalogue** – bearing selection and calculation
- **Misumi Standard Parts** – standard mechanical components

---

## Conclusion

Based on calculations performed in **Python** and validation within the
**Solid Edge Engineering Reference** module, the following conclusions
are drawn regarding the mechanical integrity of the system:

The designed gear transmission fully satisfies the technical, economic and
safety criteria. The transition from the initially calculated module $1.38$
to the standard module $1.5$ represents an example of sound engineering
practice and resource optimisation in mechanical system development.

| Check | Result | Status |
|:------|:-------|:-------|
| Gear ratio | 4:1 | ✅ |
| Contact ratio $\epsilon_\alpha$ | 1.67 > 1.2 | ✅ |
| Tooth fracture safety $S_F$ | 14.1 > 1.2 | ✅ |
| Pitting safety $S_H$ | 2.11 > 1.2 | ✅ |
| Shaft safety | 2.66 > 1.2 | ✅ |
| Key safety | 1.38 > 1.2 | ✅ |
| Bearing life $L_{10}$ | 227,000 h | ✅ |



```python
import math

# =================================================================
# 1. INPUT DATA (standardised gear pair)
# =================================================================
P = 0.25             # Power [kW]
n1 = 1800            # Input speed [RPM]
eta = 0.98           # Efficiency (per Solid Edge report)
alpha_deg = 20       # Pressure angle [degrees]

# Gear geometry (STANDARD MODULE AND PAIR)
m = 1.5              # Standard module [mm]
z1 = 18              # Number of teeth – pinion
z2 = 72              # Number of teeth – gear (i=4)
b = 15.0             # Gear face width [mm]

# Material and allowable stresses (C45 – Normalised)
Yf = 0.308           # Lewis form factor for z=18
ZE = 189.8           # Elasticity factor per SE Report [sqrt(N/mm2)]
sigma_F_dop = 200    # Allowable bending stress [N/mm2]
sigma_H_dop = 550    # Allowable contact stress [N/mm2]

# =================================================================
# 2. KINEMATICS, TORQUES AND GEOMETRY
# =================================================================
i = z2 / z1
n2 = n1 / i
T1 = (P * 1000) / (2 * math.pi * n1 / 60)  # Pinion torque [Nm]
T2 = T1 * i * eta                           # Gear torque [Nm]

d1 = m * z1                                 # Pitch diameter 1 [mm]
d2 = m * z2                                 # Pitch diameter 2 [mm]
a = (d1 + d2) / 2                           # Standard centre distance [mm]
v = (d1 * math.pi * n1) / 60000             # Pitch line velocity [m/s]

# Forces
Ft = (2000 * T1) / d1                       # Tangential force [N]
alpha_rad = math.radians(alpha_deg)
Fr = Ft * math.tan(alpha_rad)               # Radial force [N]

# =================================================================
# 2a. CONTACT RATIO (corrected formula)
# =================================================================
d_a1 = d1 + 2 * m    # Tip diameter – pinion [mm]
d_a2 = d2 + 2 * m    # Tip diameter – gear [mm]
r1 = d1 / 2          # Pitch radius – pinion
r2 = d2 / 2          # Pitch radius – gear
ra1 = d_a1 / 2       # Tip radius – pinion
ra2 = d_a2 / 2       # Tip radius – gear

alpha_a1 = math.acos(r1 * math.cos(alpha_rad) / ra1)
alpha_a2 = math.acos(r2 * math.cos(alpha_rad) / ra2)

epsilon_alpha = (1 / (2 * math.pi)) * (
    z1 * (math.tan(alpha_a1) - math.tan(alpha_rad)) +
    z2 * (math.tan(alpha_a2) - math.tan(alpha_rad))
)

# =================================================================
# 3. STRESS AND SAFETY FACTOR CALCULATION
# =================================================================
# Root stress (bending)
sigma_F = Ft / (b * m * Yf)

# Contact stress (Hertz)
ZH = math.sqrt(2 / (math.sin(alpha_rad) * math.cos(alpha_rad)))
sigma_H = ZE * ZH * math.sqrt((Ft / (b * d1)) * ((i + 1) / i))

# Safety factors
SF = sigma_F_dop / sigma_F
SH = sigma_H_dop / sigma_H

# =================================================================
# 3a. SHAFT CALCULATION
# =================================================================
tau_t_dop = 40          # Allowable torsional stress [N/mm2]
d_vratila = 12.0        # Selected standard diameter [mm]

d_min = (T2 * 1000 / (0.2 * tau_t_dop))**(1/3)
tau_t = (T2 * 1000) / (0.2 * d_vratila**3)
S_shaft = tau_t_dop / tau_t

# =================================================================
# 3b. KEY CALCULATION (DIN 6885)
# =================================================================
b_key = 4.0             # Width [mm]
h_key = 4.0             # Height [mm]
L_key = 12.0            # Total length [mm]
t1 = 2.5                # Keyway depth in shaft [mm]
p_allow = 100.0         # Allowable surface pressure [N/mm2]

l_t = L_key - b_key     # Bearing length (Form A)
h_active = h_key - t1   # Active flank height

p_key = (2 * T2 * 1000) / (d_vratila * h_active * l_t)
S_key = p_allow / p_key

# =================================================================
# 4. ENGINEERING REPORT
# =================================================================
print(f"{'FINAL STANDARDISED CALCULATION ':=^60}")
print(f"Gear ratio (i):                 {i:.2f} (Standard 4:1)")
print(f"Centre distance (a):            {a:.2f} mm (Standard)")
print(f"Module (m):                     {m:.2f} mm")
print(f"Tangential force (Ft):          {Ft:.2f} N")
print("-" * 60)
print(f"{'CONTACT RATIO ':=^60}")
print(f"Tip pressure angle – pinion:    {math.degrees(alpha_a1):.2f}°")
print(f"Tip pressure angle – gear:      {math.degrees(alpha_a2):.2f}°")
print(f"Contact ratio (ε_α):            {epsilon_alpha:.2f}")
print("-" * 60)

if epsilon_alpha > 1.2:
    print(f"STATUS: ε_α = {epsilon_alpha:.2f} > 1.2 – Mesh is SMOOTH and QUIET ✓")
else:
    print(f"WARNING: ε_α = {epsilon_alpha:.2f} < 1.2 – Risk of impact in mesh!")
print("=" * 60)
print(f"NUMBER OF TEETH:                z1 = {z1}, z2 = {z2}")
print(f"TORQUES:                        T1 = {T1:.2f} Nm, T2 = {T2:.2f} Nm")
print(f"PITCH LINE VELOCITY (v):        {v:.2f} m/s")
print("-" * 60)
print(f"{'SHAFT AND KEY CALCULATION ':=^60}")
print(f"Minimum diameter (d_min):       {d_min:.2f} mm")
print(f"Selected diameter:              {d_vratila:.2f} mm")
print(f"Shaft safety factor:            {S_shaft:.2f}")
print("-" * 60)
print(f"Key surface pressure (p):       {p_key:.2f} N/mm2")
print(f"Allowable pressure (p_allow):   {p_allow:.2f} N/mm2")
print(f"Key safety factor:              {S_key:.2f}")
print("=" * 60)
print(f"ROOT STRESS (sigma_F):          {sigma_F:.2f} N/mm2")
print(f"FRACTURE SAFETY (SF):           {SF:.2f} (Allowable: {sigma_F_dop} N/mm2)")
print("-" * 60)
print(f"CONTACT STRESS (sigma_H):       {sigma_H:.2f} N/mm2")
print(f"PITTING SAFETY (SH):            {SH:.2f} (Allowable: {sigma_H_dop} N/mm2)")
print("=" * 60)

if SF > 1.2 and SH > 1.2:
    print("STATUS: Design is VALIDATED and STANDARDISED. All components are safe.")
```
