# 🌪️ Storm Chaser & Tornado Monitor — Complete Sounding Playbook

> **A comprehensive field guide to reading Skew-T Log-P soundings, hodographs, and severe weather parameters for storm chasers, weather enthusiasts, and emergency managers.**

---

## 📋 Table of Contents

- [What Is a Sounding?](#-what-is-a-sounding)
- [Reading the Skew-T Chart](#-reading-the-skew-t-log-p-chart)
  - [The Temperature Profile](#the-temperature-profile-red-line)
  - [The Dew Point Profile](#the-dew-point-profile-green-line)
  - [Wind Barbs](#wind-barbs)
  - [Key Atmospheric Levels](#key-atmospheric-levels)
  - [CAPE and CIN Areas](#cape-and-cin-shaded-areas)
- [Reading the Hodograph](#-reading-the-hodograph)
  - [Shape and Curvature](#shape-and-curvature)
  - [Storm Motion Vectors](#storm-motion-vectors)
  - [Storm Relative Helicity](#storm-relative-helicity-srh)
- [Key Parameters Reference](#-key-parameters-reference)
  - [Instability Parameters](#instability-parameters)
  - [Shear Parameters](#shear-parameters)
  - [Moisture Parameters](#moisture-parameters)
  - [Composite Indices](#composite-indices)
- [Operational Thresholds](#-operational-thresholds)
- [SARS & Analog Matching](#-sars--sounding-analog-matching)
- [The STP Histogram](#-significant-tornado-parameter-stp--ef-rating-histogram)
- [Real-World Sounding Analysis](#-real-world-sounding-analysis-example)
- [Storm Chaser Field Playbook](#-storm-chaser-field-playbook)
  - [Morning Assessment](#morning-assessment-57-am-local)
  - [Afternoon Re-Evaluation](#afternoon-re-evaluation-122-pm-local)
  - [Initiation Watch](#initiation-watch-25-pm-local)
  - [Active Chase Protocol](#active-chase-protocol)
  - [Abort Conditions](#-abort-conditions-red-flags)
- [Safe Positioning Rules](#-safe-positioning-rules)
- [Model Guidance Notes](#-model-guidance-notes)
- [Quick Reference Cheat Sheet](#-quick-reference-cheat-sheet)
- [Glossary](#-glossary)

---

## 🌩️ What Is a Sounding?

A **Skew-T Log-P sounding** is a vertical cross-section of the atmosphere at a specific location and time. Twice daily, weather balloons (radiosondes) are launched worldwide, measuring **temperature, dew point, pressure, wind speed, and wind direction** at every altitude from the surface to roughly 30+ km. These measurements are then plotted on a standardized diagram.

Storm chasers and meteorologists use soundings to answer a fundamental question:

> **"Can this atmosphere produce severe thunderstorms and tornadoes today — and if so, how intense?"**

A full SHARPpy/Pivotal Weather sounding display contains **six major panels**, each answering a different part of that question:

| Panel | Location | What It Shows |
|-------|----------|---------------|
| **Skew-T diagram** | Top-left (large) | Temperature, dew point, and wind profile from surface to stratosphere |
| **Upper hodograph** | Top-right upper | Wind shear spiral — the tornado predictor |
| **Lower hodograph** | Top-right lower | Zoomed 0–3 km wind detail |
| **Parameter tables** | Bottom-left | All numerical indices at a glance |
| **Storm vectors / SARS** | Bottom-center | Storm motion, inflow vectors, historical analogs |
| **STP histogram** | Bottom-right | Composite tornado parameter + EF-rating probability |

---

## 📊 Reading the Skew-T Log-P Chart

The Skew-T diagram is the core of the sounding. Understanding its geometry is the first step.

### Why "Skewed"?

The temperature axis is **tilted 45° to the right** (skewed). Without this tilt, temperature and dew point lines would nearly overlap and be unreadable. The skew allows both to be plotted clearly across the entire diagram. The pressure (altitude) axis is **logarithmic** on the Y-axis — equal distances represent equal fractional changes in pressure, which roughly corresponds to equal distances in altitude.

```
High altitude (low pressure) ──── TOP of chart
                                   │
                                   │  Lines slant right as you go up
                                   │  (that's the "skew")
                                   │
Low altitude (high pressure) ── BOTTOM of chart
```

### The Temperature Profile (Red Line)

The **red line** traces temperature at every pressure level from the surface up.

- **Isothermal or inversion layers** (temperature increases with height) appear as the red line moving right as you go up — these are **caps** that suppress convection.
- **Steep lapse rates** (temperature drops rapidly with height) appear as the red line plunging sharply left — these fuel explosive thunderstorm growth.
- The **critical mid-level lapse rate** (700–500 mb) is one of the most important features: values above **7°C/km** indicate strong potential instability.

**What to look for:**

```
✅ Steep red line angle (upper levels) = strong instability aloft
✅ Surface-based temperature inversion breaking by afternoon = cap erosion
⚠️  Isothermal layer (red line goes flat or right) = capping inversion
❌ Very cold mid-level temperatures = potential for giant hail
```

### The Dew Point Profile (Green Line)

The **green line** traces moisture (dew point) at every pressure level.

- When **red and green converge** → the air is saturated → cloud or fog exists at that level.
- A **wide gap between red and green** = dry air at that level (important for fire weather, also entrainment into storms).
- A **moist layer at low levels** (green line staying near red line in the lowest few km) = rich moisture pool — the fuel for CAPE.

**Key dew point layers:**

| Layer | What to look for |
|-------|-----------------|
| Surface–850 mb | Deep moisture? Dew points 60°F+ strongly favorable for severe wx |
| 850–700 mb | Dry intrusion here = "dry punch" that enhances buoyancy above |
| 700–500 mb | Dry air here strengthens evaporative cooling in downdrafts |
| Above 500 mb | Usually dry — normal |

### Wind Barbs

Wind barbs on the **right side** of the Skew-T show the wind at each pressure level. Reading them is straightforward once you know the key:

```
   ╱  Long barb  = 10 knots
   ╱  Short barb = 5 knots
   ▼  Triangle   = 50 knots
   
   Staff direction = wind coming FROM that direction
```

**Examples:**

```
  ──┤    = 10 kt from the west
  ──┤┤   = 20 kt from the west  
  ──┤╲   = 15 kt from the west
  ──▶    = 50 kt from the west
```

**What to watch in the barbs:**

- **Backing winds** with height (counterclockwise rotation: S → SE → E going up) = warm air advection, favorable veering shear
- **Veering winds** (clockwise: S → SW → W → NW going up) = classic supercell shear profile
- **Sudden directional shift** at a level = frontal boundary or jet streak
- **Speed increase with height** = wind shear = potential for storm organization

### Key Atmospheric Levels

These are marked on the Skew-T with horizontal lines or dots:

#### LCL — Lifted Condensation Level
> **The cloud base.** Where a surface parcel cools to its dew point and condensation begins.

- **< 750 m AGL** → Strongly favorable for tornadoes (low cloud bases)
- **750–1000 m AGL** → Favorable for tornadoes
- **1000–1500 m AGL** → Marginal tornado environment
- **> 1500 m AGL** → Suppresses tornado potential significantly

> 🌪️ **Why it matters:** Low cloud bases mean the rotating mesocyclone has less distance to the ground. Studies show LCL height is one of the strongest discriminators between tornadic and non-tornadic supercells.

#### LFC — Level of Free Convection
> **Where the storm becomes self-sustaining.** Above this level, a lifted parcel is warmer than the surrounding environment and rises freely.

- High LFC (> 3000 m) with strong CIN = hard to initiate but explosive if it does
- Low LFC (< 1500 m) = easy initiation, often earlier in the day

#### EL — Equilibrium Level
> **The storm top.** Where the rising parcel cools back to the environmental temperature and stops accelerating.

- Higher EL = deeper storm = more total CAPE
- EL near 200 mb (12 km) or higher = very deep convection, large hail and tornado potential
- The actual storm top (anvil) is usually near or slightly above the EL

#### The Tropopause
> **The boundary between troposphere and stratosphere.** Storms cannot easily penetrate this layer — it acts as a "lid" that forces the anvil to spread horizontally. Overshooting tops that punch through it indicate extremely vigorous updrafts.

### CAPE and CIN Shaded Areas

The Skew-T shows two critical shaded regions:

#### CAPE — Convective Available Potential Energy (positive area, orange/red)

CAPE represents the **total buoyant energy** available to a rising air parcel. It is the area between the parcel temperature curve and the environmental temperature curve, from the LFC to the EL.

```
         EL ──── TOP of positive area
          │
          │  ████████  ← CAPE area
          │  ████████     (parcel warmer than environment)
          │  ████████
          │
         LFC ─── BOTTOM of positive area
```

| CAPE Value | Interpretation |
|------------|---------------|
| 0–500 J/kg | Marginal — weak convection possible |
| 500–1500 J/kg | Moderate — strong thunderstorms likely |
| 1500–3000 J/kg | Large — severe thunderstorms, possible tornadoes |
| > 3000 J/kg | Extreme — violent updrafts, large hail, tornado outbreak potential |

> ⚠️ **CAPE alone is not enough.** High CAPE without shear produces tall, pulse-type thunderstorms — dangerous for hail and lightning but not well-organized. You need both CAPE AND shear for supercells.

#### CIN — Convective Inhibition (negative area, blue)

CIN is the **cap** — negative buoyancy that must be overcome before a parcel can reach the LFC and explode into a thunderstorm. It is the area where the environment is warmer than the parcel.

```
         LFC ─── TOP of CIN area
          │
          │  ░░░░░░░░  ← CIN area
          │  ░░░░░░░░     (environment warmer than parcel)
          │
        Surface ─────── BOTTOM of CIN area
```

| CIN Value | Interpretation |
|-----------|---------------|
| 0 to -25 J/kg | Very weak cap — storms can fire easily, often chaotic/messy |
| -25 to -75 J/kg | **Sweet spot** — discrete supercells most likely here |
| -75 to -150 J/kg | Strong cap — storms need significant forcing to initiate |
| > -150 J/kg | Very strong cap — convection very unlikely without extreme forcing |

> 🎯 **The cap is your friend as a storm chaser.** A moderate cap keeps storms discrete and separated. Zero cap = storms fire everywhere and interact with each other, making positioning dangerous and difficult.

---

## 🌀 Reading the Hodograph

The hodograph is often called the **most important tornado predictor** on a sounding. It plots the wind vector at each altitude as a single point, then connects those points with a line — creating a spiral shape.

### Understanding the Coordinate System

```
        N (360°)
         │
W ───────┼─────── E
(270°)   │       (090°)
         │
        S (180°)
         
Rings = wind speed in knots (10, 20, 30, 40...)
Each dot = wind at a specific altitude
```

**How to read it:** Starting at the origin (calm), the line traces outward in the direction the wind is blowing FROM at each altitude. The **distance from the origin** = wind speed. As altitude increases, you follow the line outward from its starting dot.

### Shape and Curvature

The shape of the hodograph spiral is diagnostic:

#### Straight Hodograph
```
  ← ─────────────  ←
   1km  3km  6km
```
- Unidirectional shear
- Squall lines and bow echoes
- Minimal tornado potential
- Very fast storm motion (splitting cells race apart)

#### Curved Hodograph (clockwise)
```
     ↑ 6km
    ╱
   3km
  │
  1km
  ↓ surface
```
- **Streamwise vorticity** — spin tilts INTO the updraft
- Classic supercell environment
- **Tornado potential significantly elevated**
- The longer and more curved the lower segment, the better

#### Elongated / Long Hodograph
```
                         ←──────────── 6km
                        /
                    3km
                  /
              1km
           /
    surface
```
- Very strong deep-layer shear
- Classic HP supercell or long-track tornado potential
- Storm motion fast — positioning difficult

### Storm Motion Vectors

The hodograph typically shows **three motion vectors** plotted as labeled dots:

| Vector | What It Means |
|--------|--------------|
| **Bunkers Right (259/36 LM in example)** | Predicted motion of right-moving supercell — the typical tornado-producing storm |
| **Bunkers Left** | Predicted motion of left-moving supercell — moves north, anti-cyclonic rotation, less common |
| **Corfidi Upshear (UP)** | Tracks upshear-propagating MCS systems |
| **Corfidi Downshear** | Tracks downshear-propagating MCS systems |

> 🚗 **For chasers:** The Bunkers Right vector tells you which direction and speed the supercell will move. This is critical for positioning. A storm moving NE at 40 kt requires very different intercept tactics than one drifting SE at 15 kt.

### Storm Relative Helicity (SRH)

SRH is the **area swept between the storm motion vector and the hodograph curve**. It measures how much spin (helicity) the storm's updraft can "import" from the environment.

```
         Hodograph
         curve
        ╱─────────
       ╱  SRH area ╲
      ╱  ████████    ╲
     ╱  █████████     ╲
Storm motion vector
```

| 0–1km SRH | Interpretation |
|-----------|---------------|
| < 100 m²/s² | Minimal — weak rotation possible |
| 100–150 m²/s² | Marginal — some supercell rotation |
| 150–300 m²/s² | **Notable** — significant tornado threat |
| 300–500 m²/s² | Large — violent tornadoes possible |
| > 500 m²/s² | Extreme — major tornado outbreak conditions |

> ⚠️ **The 0–1 km SRH layer is the most critical.** It measures the spin closest to the ground — where tornadoes form. A hodograph that has most of its curvature in the 0–1 km layer is far more threatening than one that is curved only at mid-levels.

---

## 📐 Key Parameters Reference

### Instability Parameters

These appear in the left portion of the parameter table (PCL, CAPE, CINH columns).

#### CAPE Types

| Parameter | Full Name | Notes |
|-----------|-----------|-------|
| **SBCAPE** | Surface-Based CAPE | Uses actual surface conditions. Best for early-morning or nocturnal events. |
| **MLCAPE** | Mixed-Layer CAPE | Averages the lowest 100 mb of the atmosphere. Most representative for afternoon convection. **Use this as your primary CAPE.** |
| **MUCAPE** | Most Unstable CAPE | Finds the parcel with highest theta-e. Best for elevated convection and when a warm moist layer exists above the surface. |
| **FCST CAPE** | Forecast CAPE | Applies a forecast temperature/moisture to estimate afternoon instability. Useful for morning soundings. |

#### Lapse Rates

| Parameter | Full Name | Threshold |
|-----------|-----------|-----------|
| **Sfc-3km LR** | Surface to 3 km lapse rate | > 9°C/km = extreme low-level instability |
| **3-6km LR** | 3 to 6 km lapse rate | > 7°C/km = strong mid-level instability |
| **700-500mb LR** | Classic mid-level lapse rate | > 7°C/km = significant, > 8°C/km = explosive |
| **850-500mb LR** | Deep lapse rate | Used in composite indices |

---

### Shear Parameters

| Parameter | Full Name | Favorable Threshold | Notes |
|-----------|-----------|--------------------|----|
| **0–1km Shear** | Bulk shear, surface to 1 km | > 20 kt | Most important for tornado longevity |
| **0–3km Shear** | Bulk shear, surface to 3 km | > 30 kt | Low-level jet signature |
| **0–6km Shear** | Bulk shear, surface to 6 km | **> 35 kt** | Primary supercell discriminator |
| **Eff. Shear (EBWD)** | Effective Bulk Wind Difference | > 40 kt | Uses effective inflow layer — better than fixed-layer shear |
| **SFC-6km SR Wind** | Surface to 6 km storm-relative wind | > 30 kt | Used in SCP composite |
| **EHI** | Energy-Helicity Index | > 1.0 | CAPE × SRH product |

---

### Moisture Parameters

| Parameter | What It Measures | Notes |
|-----------|-----------------|-------|
| **PW** | Precipitable Water (inches) | Total column moisture. > 1.5" = heavy rain risk. > 2.0" = flash flood risk |
| **MeanW** | Mean Mixing Ratio (g/kg) | Boundary layer moisture. > 12 g/kg is rich. > 16 g/kg is extremely moist |
| **LowRH** | Low-level Relative Humidity | High % → narrow DCAPE, less evaporation |
| **MidRH** | Mid-level Relative Humidity | Low % → high DCAPE, strong rear-flank downdraft |
| **DownT** | Downdraft Temperature | How cold the RFD air is — affects tornado maintenance |

---

### Composite Indices

These single numbers combine multiple ingredients to diagnose storm type and intensity.

#### STP — Significant Tornado Parameter

> **The most important single number for tornado potential.**

$$STP = \frac{MLCAPE}{1500} \times \frac{2000-MLLCL}{1000} \times \frac{0\text{-}1SRH}{150} \times \frac{EBWD}{45}$$

| STP Value | Interpretation |
|-----------|---------------|
| < 0.5 | Tornadoes very unlikely |
| 0.5–1.0 | Marginal — brief tornadoes possible |
| **1.0–3.0** | **Significant tornado threat — Watch criteria met** |
| 3.0–6.0 | Major tornado outbreak potential |
| > 6.0 | Historically exceptional — violent, long-track tornadoes |

#### SCP — Supercell Composite Parameter

Diagnoses whether the atmosphere supports supercell thunderstorms.

| SCP Value | Interpretation |
|-----------|---------------|
| < 1 | Supercells unlikely |
| 1–4 | Supercell environment |
| > 4 | Very favorable supercell environment |

#### SHIP — Significant Hail Parameter

Focuses on giant hail (≥ 2 inch) potential.

| SHIP Value | Interpretation |
|------------|---------------|
| < 0.5 | Significant hail unlikely |
| 0.5–1.0 | Some hail possible |
| > 1.0 | Significant hail (2"+) likely in supercells |

#### BRN — Bulk Richardson Number

Ratio of CAPE to shear — discriminates storm type.

| BRN Value | Storm Type |
|-----------|-----------|
| < 10 | Too much shear — storms shear apart |
| **10–45** | **Supercell range** |
| 45–50 | Multicell borderline |
| > 50 | Multicell clusters, pulse storms |

#### EHI — Energy-Helicity Index

```
EHI = (MLCAPE × SRH) / 160,000
```

| EHI Value | Interpretation |
|-----------|---------------|
| < 1.0 | Minimal |
| 1.0–2.0 | Tornado possible |
| **> 2.0** | **Significant tornado likely** |
| > 4.0 | Violent tornado potential |

---

## 🎯 Operational Thresholds

Use this table as a **rapid-scan reference** when evaluating a sounding in the field. Color coding represents threat level.

### The Big Three (Required Together for Tornado Watch)

```
┌─────────────────────────────────────────────────────────────────┐
│  MLCAPE ≥ 1000 J/kg  +  0-1km SRH ≥ 150  +  0-6km ≥ 35 kt    │
│         = Tornado Watch baseline criteria                        │
└─────────────────────────────────────────────────────────────────┘
```

### Full Threshold Matrix

| Parameter | 🟢 Low Risk | 🟡 Marginal | 🟠 Significant | 🔴 Extreme |
|-----------|------------|------------|---------------|-----------|
| **MLCAPE** | < 500 J/kg | 500–1500 | 1500–3000 | > 3000 |
| **0–1km SRH** | < 100 m²/s² | 100–150 | 150–300 | > 300 |
| **0–3km SRH** | < 150 m²/s² | 150–250 | 250–500 | > 500 |
| **0–6km Shear** | < 25 kt | 25–35 | 35–50 | > 50 |
| **LCL Height** | > 1500 m | 1000–1500 | 750–1000 | < 750 m |
| **STP** | < 0.5 | 0.5–1.0 | 1.0–3.0 | > 3.0 |
| **EHI** | < 0.5 | 0.5–1.0 | 1.0–2.5 | > 2.5 |
| **SHIP** | < 0.5 | 0.5–1.0 | 1.0–2.0 | > 2.0 |
| **CIN** | > -10 or < -200 | -10 to -25 | **-25 to -75** (sweet spot) | -75 to -150 |

> 🔑 **Key principle:** No single parameter is sufficient. A sounding with extreme CAPE but straight hodograph (no shear) will not produce tornadoes. A sounding with extreme SRH but zero CAPE cannot even produce a thunderstorm. **You must evaluate the combination.**

### Storm Type Decision Matrix

```
              HIGH SHEAR
                  │
    Squall Lines  │  Supercells / Long-track tornadoes
    Bow Echoes    │  Giant Hail / EF4-5 potential
                  │
──────────────────┼──────────────────
                  │
    Pulse Storms  │  Pulse Severe
    Marginal      │  Large Hail / brief tornadoes
                  │
              LOW SHEAR
         LOW CAPE    HIGH CAPE
```

---

## 🔍 SARS — Sounding Analog Matching

SARS (Sounding Analog Retrieval System) searches a database of **thousands of historical soundings** from severe weather events and finds the closest matches to the current sounding's shape and parameters.

### How to Interpret SARS Output

The display shows two columns:

| Column | What It Means |
|--------|--------------|
| **SUPERCELL** | Percentage of matched historical soundings that produced supercells |
| **SGFNT HAIL** | Percentage that produced significant (≥ 2") hail |

**Reading the numbers:**
- `72/107` means: 72 matched soundings found, 107 total in database segment
- A match percentage **> 50%** is notable
- **"No Quality Matches"** means the current sounding is unusual — either very benign or extremely unusual

> ⚠️ **No matches can mean two things:** The atmosphere is either so benign that it matches no severe weather events historically (good!) OR it's so extreme that it falls outside historical ranges (very bad!). Always look at the raw parameters too.

---

## 📊 Significant Tornado Parameter (STP) & EF Rating Histogram

The bottom-right panel of the sounding display shows a **bar chart** with probabilities for each EF rating and a "NONTOR" (non-tornadic) category.

### Reading the Histogram

```
Probability
  │
  │  ████
  │  ████
  │  ████
  │  ████   ███
  │  ████   ███    ██
  │  ████   ███    ██    █
  └──────────────────────────
   EF4+  EF3   EF2   EF1  EF0  NONTOR
```

| Bar | Meaning |
|-----|---------|
| **EF4+** | Violent/catastrophic tornado potential |
| **EF3** | Major tornado potential |
| **EF2** | Significant tornado |
| **EF1** | Moderate tornado |
| **EF0** | Weak/brief tornado |
| **NONTOR** | Most likely outcome is no tornado |

**Sub-indices shown:**
- `based on LCL`: STP contribution from cloud base height
- `based on ESRH`: STP contribution from effective SRH
- `based on EBWD`: STP contribution from effective shear
- `based on STP_fixed`: Traditional fixed-layer STP

> 💡 When the **NONTOR bar dominates**, the atmosphere is not supporting tornadoes. When **EF2–EF3 bars are prominent**, take it seriously. When **EF4+ is non-trivial**, this is a life-threatening event.

---

## 🔬 Real-World Sounding Analysis Example

**Sounding:** GFS 2026-03-25 18z, F030 — Valid Fri 2026-03-27 00z — AT: 41.25°N, 88.0°W  
**Location:** Near Joliet/Kankakee, Illinois  
**Model:** GFS (30-hour forecast)

### Raw Data from the Display

| Parameter | Value | Assessment |
|-----------|-------|-----------|
| Surface Temp / Dew Point | 43°F / 47°F | Near-saturated surface layer |
| SBCAPE | -2028 J/kg | **Strongly capped — no surface instability** |
| MLCAPE | 0 J/kg | No mixed-layer instability |
| MLCIN | 0 J/kg | — |
| LCL (ML) | 286 m AGL | ✅ Excellent if storms could fire |
| LFC | 286 m | — |
| EL | 416 m | Very shallow — no real storm depth |
| 0–1km SRH | **-35 m²/s²** | ❌ Negative (anticyclonic) |
| 0–3km SRH | 263 m²/s² | ⚠️ Elevated mid-level helicity |
| Eff. SRH | `--` | No effective inflow layer exists |
| 0–6km Bulk Shear | 35 kt | Marginal supercell threshold |
| Eff. Shear (EBWD) | `--` | No effective layer |
| STP (cin) | **0.0** | No tornado parameter |
| SHIP | 0.0 | No hail parameter |
| BRN Shear | 255 m²/s² | — |
| PW | 1.24 in | Modest moisture |
| SARS Supercell | No Quality Matches | Non-severe analog |
| SARS Sgfnt Hail | No Quality Matches | Non-severe analog |
| Psbl Haz Type | **NONE** | Non-event forecast |
| EF Histogram | Dominated by NONTOR | Tornado very unlikely |

### Interpretation

```
╔══════════════════════════════════════════════════════════════╗
║  BOTTOM LINE: This is a non-event sounding.                  ║
║                                                              ║
║  Despite a very favorable LCL height (286m) and moderate    ║
║  0–3km SRH (263), the near-zero CAPE and extreme capping    ║
║  inversion prevent any convective development. Storms        ║
║  simply cannot fire or sustain themselves in this setup.     ║
╚══════════════════════════════════════════════════════════════╝
```

**What IS favorable (if instability were present):**
- ✅ LCL: 286 m — exceptional tornado height
- ✅ 0–3km SRH: 263 m²/s² — solid mid-level helicity
- ✅ 0–6km shear: 35 kt — marginal supercell range

**What IS NOT favorable:**
- ❌ MLCAPE: 0 J/kg — no fuel for convection
- ❌ 0–1km SRH: -35 m²/s² — actually anticyclonic near the surface
- ❌ Effective inflow layer: does not exist
- ❌ SARS: no matches

### What to Watch For

If a **surface boundary** (warm front, outflow boundary, dryline surge) moves into this area and provides lifting, even **modest daytime heating** could break the cap and allow some convection to fire. In that scenario, the low LCL and mid-level SRH would become significant.

> 📡 **Model note:** This is GFS F030 (30-hour forecast). GFS frequently mishandles mesoscale boundaries and surface moisture. Always cross-reference with **HRRR or NAM** for events within 18 hours. If the HRRR shows a different picture (more instability), weight the HRRR more heavily.

---

## 🗺️ Storm Chaser Field Playbook

### Morning Assessment (5–7 AM Local)

**Goal:** Determine if the day has chase potential and identify the target area.

---

#### Step 1 — Check for Instability

```
Is MLCAPE ≥ 500 J/kg in any forecast model?
├── NO  → Non-chase day (unless boundary expected to significantly enhance)
│         Monitor anyway — models can be wrong by 2–4 hours on cap erosion
└── YES → Continue to Step 2
```

**Data sources to check:**
- SPC Mesoanalysis (www.spc.noaa.gov/exper/mesoanalysis/)
- HRRR model soundings for target area
- RAP soundings
- Observed 12z radiosonde from nearest station

---

#### Step 2 — Evaluate the Cap

```
What is MLCIN?
├── 0 to -10 J/kg   → Very weak cap — explosive, chaotic initiation possible
│                     Storms will fire everywhere — difficult positioning day
├── -10 to -50 J/kg → Favorable cap — discrete supercells most likely
│                     Sweet spot for storm chasing
├── -50 to -100     → Moderate cap — storms need strong forcing or afternoon heating
│                     Monitor for boundary focus points
└── < -100 J/kg     → Strong cap — initiation very unlikely
                      Unless extreme forcing (strong front, elevated terrain)
```

---

#### Step 3 — Check Low-Level Moisture

| Check | Threshold | Action |
|-------|-----------|--------|
| Surface dew point | ≥ 55°F good, ≥ 60°F favorable, ≥ 65°F excellent | Higher = more CAPE, lower LCL |
| 850mb dew point | ≥ 10°C | Indicates deep moisture layer |
| Mixing ratio | ≥ 12 g/kg | Rich moisture pool |
| PW | ≥ 1.25 in | Supports heavy precipitation with storms |

---

#### Step 4 — Evaluate Shear

```
0–6km Bulk Shear:
├── < 25 kt → No supercell potential. Multicell/pulse storms at best.
├── 25–35 kt → Marginal. Marginal supercells possible near strong boundaries.
├── 35–50 kt → Good. Classic supercell environment if CAPE is present.
└── > 50 kt → Excellent. Long-track supercells and major tornadoes possible.

0–1km SRH:
├── < 100 → Minimal near-surface spin
├── 100–150 → Marginal
├── > 150 → Notable — add this to your threat assessment
└── > 300 → Significant tornado threat elevated substantially
```

---

#### Step 5 — Read the Hodograph

Look for these shapes in the 0–6 km portion:

```
FAVORABLE (tornado potential):          UNFAVORABLE:
                                        
    ↑ 6km                                   6km ────────────── ←
   ╱                                    3km ──────────────
  3km                                   1km ────── ← surface
  │                  Clockwise
  1km ↓              curved spiral      Linear/straight = 
  ↓ surface                             squall line, no rotation
```

**Key question:** Does the hodograph have a distinct **clockwise curve in the 0–1 km layer**? That's the tornado signature.

---

#### Step 6 — Calculate/Read STP

```
STP ≥ 1.0 AND all three Big Three criteria met?
├── YES → This is a tornado watch-level environment. Plan your chase.
│         Note EF histogram for intensity guidance.
└── NO  → Tornado unlikely but monitor for boundary enhancement
          STP can change rapidly with afternoon heating and boundary focus
```

---

### Afternoon Re-Evaluation (12–2 PM Local)

**Goal:** Refine target, confirm cap erosion timing, identify initiation focus.

#### Updates to Pull

- [ ] Latest HRRR (runs hourly — use the most recent)
- [ ] SPC Mesoscale Discussions (check for updated outlooks)
- [ ] Surface analysis (locate actual fronts, drylines, outflow boundaries)
- [ ] Observed surface dew points at your target (has moisture recovered?)
- [ ] Latest visible satellite (look for cloud streets, cumulus development)

#### Signs the Day is Coming Together

```
✅ Cumulus towers building in your target area (cap eroding)
✅ Surface dew points rising (moisture pooling)
✅ Surface winds backing to southerly (veering wind profile developing)
✅ Clearing skies on the warm side of the boundary (daytime heating)
✅ 850mb winds increasing (low-level jet developing early)
```

#### Signs the Day is NOT Coming Together

```
❌ No cumulus development by 2 PM despite expected timing
❌ Dew points falling (dry air advection)
❌ Surface winds going easterly or northerly (cold air advection)
❌ Overcast skies limiting heating (stratus deck not clearing)
❌ HRRR has backed off on CAPE vs. morning run
```

---

### Initiation Watch (2–5 PM Local)

**Goal:** Identify the first storm to become supercellular and position safely.

#### Radar Signatures to Watch For

| Signature | Meaning | Action |
|-----------|---------|--------|
| **Rotating updraft base** | Storm becoming supercellular | Begin positioning SE of storm |
| **Hook echo developing** | Mesocyclone forming | Confirm tornado potential, prepare for possible tornado |
| **TVS (Tornado Vortex Signature)** | Tight rotation detected by radar | Storm is producing/likely to produce tornado |
| **Large/giant hail core** | Very strong updraft | Extreme caution — don't core punch |
| **Bow echo forming** | Storm going linear | Move SE quickly — derecho risk |

---

### Active Chase Protocol

#### Positioning Checklist

```
Before approaching any supercell:
├── [ ] Confirmed storm motion vector (from hodograph/radar trend)
├── [ ] Positioned SOUTH or SOUTHEAST of storm
├── [ ] Escape route identified (east or south paved road)
├── [ ] Fuel > 1/2 tank
├── [ ] All team members aware of storm motion direction
└── [ ] Communication plan established (NOAA Weather Radio + spotter network)
```

#### Storm Quadrants — Know Where You Are

```
                    NW ←─── Storm motion ───→ NE
                     │                         │
          DANGEROUS  │      SUPERCELL          │  DANGEROUS
          (forward   │      CORE               │  (hail core
           flank     │                         │   and RFD)
           downdraft)│                         │
                     │                         │
    ─────────────────┼─────────────────────────┼──────────────
                     │                         │
           SAFE ✅   │    INFLOW NOTCH ✅      │   SAFE ✅
           (SE)      │    (best view,           │   (E)
                     │     good escape)         │
                    SW                          SE
                     
             ← Storm center approximately here
```

**Never be north or northwest of an active supercell.**

#### Tornado Sighted — Decision Protocol

```
Tornado confirmed on ground:
│
├── Is it moving toward me?
│   ├── YES → IMMEDIATELY move at 90° to the right (south or east)
│   │         Do NOT try to outrun it directly away — it's too fast
│   └── NO  → Maintain current position or back up slowly
│
├── Is visibility deteriorating?
│   ├── YES → Rain-wrapped tornado risk — back out NOW
│   └── NO  → Monitor, stay in position if escape route clear
│
└── Is a second tornado forming?
    ├── YES → Multiple-vortex event — wider danger zone, back out
    └── NO  → Maintain safe observation position
```

---

### 🚨 Abort Conditions (Red Flags)

These conditions should trigger an immediate change in strategy or full abort:

> **🔴 FULL ABORT — Leave the area immediately**

- Tornado moving directly toward your position with no clear escape route
- Multiple tornadoes simultaneously (difficult to track all of them)
- Heavy rain/hail completely obscures visibility (rain-wrapped tornado risk)
- Night-time tornado conditions + violent tornado environment (STP > 4)
- Bridge/low-water crossing flooded on your only escape route

---

> **🟠 REPOSITION — Change location immediately**

- You are north or northwest of the updraft base
- Storm is accelerating or turning toward you
- Large hail beginning to fall on your vehicle
- New storm developing to your south or southwest (getting caught between storms)
- Power lines down on your primary road

---

> **🟡 REASSESS — Stop and re-evaluate**

- Hodograph straightening on updates (losing rotation potential)
- CAPE dropping sharply on latest model run
- Storm going outflow-dominant (anvil spreading south, mesocyclone weakening on radar)
- Multiple storm mergers (chaotic convection developing)

---

> **⚠️ HIGH-RISK ENVIRONMENTAL FLAGS**

These atmospheric signatures indicate an elevated risk even before a tornado forms:

| Flag | What It Means | What To Do |
|------|--------------|------------|
| STP > 4.0 + MLCAPE > 3000 | EF4–5 environment | Do not get close. Observe from distance only. |
| 0–1km SRH > 400 | Extreme low-level spin | Assume any supercell will produce violent tornadoes |
| Very high LCL (> 2000m) + high SRH | HP supercell environment | Tornadoes invisible in rain. Do not position close. |
| Negative CIN (< -5) + high CAPE | Explosive, uncontrolled initiation | Storms fire everywhere — impossible to position safely |
| Hodograph curving counterclockwise | Left-mover environment | Storms move NNE — unconventional tracks, very dangerous |

---

## 🧭 Safe Positioning Rules

These are non-negotiable rules for storm chasers at every experience level.

### The Golden Rule

> **Always be south or southeast of a right-moving supercell. Always have a southward or eastward escape route.**

### The 10 Commandments of Safe Storm Positioning

1. **Know your storm motion vector** before you approach any storm (from hodograph Bunkers Right vector or radar trend).

2. **Position south-southeast** of the mesocyclone — in the inflow notch where you have clear view AND escape options.

3. **Never position north or northwest** of an active supercell's updraft tower, ever, under any circumstances.

4. **Identify escape routes before you need them.** Know which road goes south, which goes east. Check they are not dead-ends.

5. **Keep moving** — a stationary chaser is a dangerous chaser. Always creep south or east to maintain position relative to a moving storm.

6. **Watch for the rear-flank downdraft (RFD)** — the "clear slot" wrapping around the wall cloud. Beautiful to watch, but it's the prelude to tornado touchdown. When the RFD clears, be ready.

7. **Respect the HP (High Precipitation) supercell.** It wraps precipitation around the mesocyclone. Rain-wrapped tornadoes are invisible. Give HP supercells significantly more distance.

8. **Fuel discipline:** Never go below 1/4 tank on a chase day. Stop when you hit 1/2 if no station is ahead on your intercept path.

9. **Night chasing requires more distance.** You cannot see what you cannot see. At night, double your minimum safe distance and rely on lightning flashes and radar.

10. **If in doubt, bail out.** No observation, video, or photo is worth your life. The atmosphere will give you another chance.

---

## 🛰️ Model Guidance Notes

Different models have different strengths. Use them together:

| Model | Update Frequency | Strengths | Weaknesses |
|-------|-----------------|-----------|------------|
| **HRRR** | Hourly | Best near-term (0–18 hr), high-resolution, handles boundaries well | Short forecast range, can over-intensify convection |
| **NAM** | 6-hourly | Good mesoscale detail, 2.5 km nest available | Can be too aggressive with moisture and CAPE |
| **GFS** | 6-hourly | Best for day 2–7 outlooks, good synoptic pattern | Low resolution, misses mesoscale details, often low on CAPE |
| **RAP** | Hourly | Similar to HRRR, slightly coarser | Less refined than HRRR for convective details |
| **ECMWF** | 12-hourly | Best synoptic forecast globally | Expensive data access, lower-resolution |

**Decision matrix for model weighting:**

```
Event timing within 6 hours?    → Weight HRRR heaviest
Event timing 6–18 hours away?   → HRRR + RAP
Event timing 18–36 hours away?  → NAM + GFS
Event timing 2–5 days away?     → GFS + ECMWF ensemble
```

### SPC Products to Monitor

| Product | URL | When to Check |
|---------|-----|--------------|
| **Day 1 Outlook** | spc.noaa.gov/products/outlook/ | Every morning and after 1 PM update |
| **Mesoscale Discussions** | spc.noaa.gov/products/md/ | Whenever storms are active or imminent |
| **Watch Status** | spc.noaa.gov/products/watch/ | Real-time during chase |
| **Mesoanalysis** | spc.noaa.gov/exper/mesoanalysis/ | Every 30–60 min on chase day |
| **Surface Analysis** | spc.noaa.gov/obswx/maps/ | Morning and afternoon |

---

## ⚡ Quick Reference Cheat Sheet

```
╔══════════════════════════════════════════════════════════════════════╗
║              STORM CHASER SOUNDING QUICK REFERENCE                   ║
╠══════════════════════════════════════════════════════════════════════╣
║  THE BIG THREE (all required for significant tornado potential):      ║
║  ├── MLCAPE    ≥ 1000 J/kg                                           ║
║  ├── 0-1km SRH ≥ 150 m²/s²                                          ║
║  └── 0-6km     ≥ 35 kt                                               ║
╠══════════════════════════════════════════════════════════════════════╣
║  TORNADO PROBABILITY QUICK SCAN:                                      ║
║  STP < 0.5  → Unlikely         STP 0.5-1.0 → Marginal               ║
║  STP 1-3    → Significant      STP > 3.0   → Outbreak level          ║
╠══════════════════════════════════════════════════════════════════════╣
║  LCL HEIGHT — TORNADO DISCRIMINATOR:                                  ║
║  < 750m  = Excellent    750-1000m = Good                             ║
║  1000-1500m = Marginal  > 1500m  = Suppressed                        ║
╠══════════════════════════════════════════════════════════════════════╣
║  CAP SWEET SPOT: CIN between -25 and -75 J/kg                        ║
║  (enough to keep storms discrete, weak enough to break)               ║
╠══════════════════════════════════════════════════════════════════════╣
║  HODOGRAPH: Clockwise curve in 0-1 km = TORNADO SIGNATURE            ║
╠══════════════════════════════════════════════════════════════════════╣
║  SAFE POSITION: Always SOUTH or SOUTHEAST of supercell               ║
║  DANGER ZONE: NEVER north or northwest of updraft base               ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

## 📖 Glossary

| Term | Definition |
|------|-----------|
| **CAPE** | Convective Available Potential Energy — the fuel for thunderstorm updrafts, measured in J/kg |
| **CIN** | Convective Inhibition — the cap that suppresses convection; must be overcome for storms to fire |
| **LCL** | Lifted Condensation Level — the altitude where a surface parcel becomes saturated; approximates cloud base |
| **LFC** | Level of Free Convection — where a lifted parcel becomes warmer than the environment and rises freely |
| **EL** | Equilibrium Level — where the rising parcel cools back to environmental temperature; the storm top |
| **SRH** | Storm Relative Helicity — the spin (helicity) available to a storm's updraft, measured relative to storm motion |
| **STP** | Significant Tornado Parameter — composite index for significant tornado potential |
| **SCP** | Supercell Composite Parameter — composite index for supercell potential |
| **SHIP** | Significant Hail Parameter — composite index for giant (≥2") hail |
| **BRN** | Bulk Richardson Number — ratio of CAPE to shear; discriminates storm type |
| **EHI** | Energy-Helicity Index — product of CAPE and SRH |
| **PW** | Precipitable Water — total column water vapor in inches |
| **EBWD** | Effective Bulk Wind Difference — shear calculated using the effective inflow layer |
| **ESRH** | Effective SRH — SRH calculated using the effective inflow layer |
| **RFD** | Rear-Flank Downdraft — the descending air behind and around the tornado, often marks the "clear slot" |
| **HP Supercell** | High Precipitation supercell — wraps rain/hail around mesocyclone, produces rain-wrapped tornadoes |
| **LP Supercell** | Low Precipitation supercell — very visible updraft and mesocyclone, less precip |
| **Classic Supercell** | The standard supercell type — well-organized with visible wall cloud and hook echo |
| **Hodograph** | Polar plot of wind speed and direction vs. altitude; spiral shape predicts storm type |
| **Streamwise Vorticity** | Horizontal spin aligned with the storm-inflow direction — tilts into updraft to produce mesocyclone |
| **Mesocyclone** | A rotating updraft within a supercell, typically 2–10 km in diameter |
| **Wall Cloud** | A lowered cloud base beneath a supercell's updraft — precursor to tornado development |
| **SARS** | Sounding Analog Retrieval System — historical sounding comparison database |
| **GFS** | Global Forecast System — NOAA's primary global weather model |
| **HRRR** | High Resolution Rapid Refresh — NOAA's 3 km hourly-updating storm-scale model |
| **RAP** | Rapid Refresh — NOAA's hourly-updating regional model |
| **SPC** | Storm Prediction Center — NOAA office responsible for severe weather outlooks and watches |
| **TVS** | Tornado Vortex Signature — tight rotation detected on Doppler radar indicative of a tornado |
| **Lapse Rate** | Rate of temperature decrease with altitude, measured in °C/km |
| **Dew Point** | Temperature to which air must be cooled to become saturated; proxy for moisture content |
| **Precipitable Water** | Total water vapor in a column of atmosphere; higher = more rain potential |
| **Anvil** | The flat, spreading top of a thunderstorm where it encounters the tropopause |
| **Overshooting Top** | A dome of cloud above the anvil — indicates extremely vigorous updraft |

---

## 📚 Further Resources

| Resource | Description | Link |
|----------|-------------|------|
| **SPC Mesoanalysis** | Real-time severe weather parameters maps | https://www.spc.noaa.gov/exper/mesoanalysis/ |
| **Pivotal Weather Soundings** | The platform shown in this guide | https://www.pivotalweather.com |
| **SHARPpy** | Open-source sounding analysis software | https://github.com/sharppy/SHARPpy |
| **RAdar Scope** | Best mobile radar app for chasers | iOS/Android |
| **SPC Outlooks** | Official severe weather outlooks | https://www.spc.noaa.gov/products/outlook/ |
| **College of DuPage Soundings** | Free sounding visualization | https://weather.cod.edu/soundings/ |
| **Univ. Wyoming Soundings** | Observed radiosonde archive | https://weather.uwyo.edu/upperair/sounding.html |

---

*Guide based on GFS sounding analysis for 41.25°N, 88.0°W — March 2026. Sounding data powered by SHARPpy / Pivotal Weather.*  
*For educational and operational reference use. Always consult official NWS and SPC products for life-safety decisions.*

---

**⭐ If this guide helped you, consider starring this repository.**
