# WEEK 7 — Exam-Ready Study Notes
## NOC25_GE17 | Introduction to Environmental Engineering and Science
### Dr. Brajesh Kumar Dubey, IIT Kharagpur
**Topics Covered:** Hydrologic Cycle · Surface Runoff (Rational Method) · Water Demand & Per Capita Demand · Population Forecasting · Conveyance (Darcy-Weisbach & Hazen-Williams) · Water Quality (Hardness, Fluoride, Nitrates, pH)

---

## PART A — ASSIGNMENT QUESTIONS & SOLUTIONS

### Q1. Which type of land cover has the highest runoff coefficient?

| Option | Text |
|--------|------|
| a | Lawns and gardens |
| b | Open ground |
| **c ✅** | **Pavements and yards** |
| d | Single-family dwellings |

**✅ Correct Answer: c**

**Why c is correct:**
The slides provide the following runoff coefficient table:

| Type of Cover | Coefficient of Runoff |
|---|---|
| Roofs | 0.90 |
| Pavements and yards | 0.80 |
| Single family dwelling | 0.50 |
| Roads | 0.40 |
| Lawns and gardens | 0.15 |
| Open ground | 0.10 |

Among the four given options, **Pavements and yards (0.80)** is the highest. Impervious surfaces like pavement allow almost no infiltration, so nearly all rainfall becomes runoff.

**Why others are wrong:**
- **a** — Lawns and gardens (0.15) are vegetated, allowing significant infiltration and absorption.
- **b** — Open ground (0.10) has the lowest runoff coefficient of the options listed — it absorbs almost all rainfall.
- **d** — Single-family dwellings (0.50) are mixed surfaces (roof + lawn + driveway) and have a lower composite coefficient than pure pavement.

#### Type 1 — Wrong Option Spin-offs (Q1)

**Q1-T1a.** Which type of land cover has the *lowest* runoff coefficient among those listed in the slides?
- a) Lawns and gardens
- **b) Open ground (0.10) ✅**
- c) Pavements and yards
- d) Single-family dwellings

**Q1-T1b.** Which land cover type has a runoff coefficient of approximately 0.50 in the slides?
- a) Pavements and yards
- b) Open ground
- **c) Single-family dwellings ✅**
- d) Lawns and gardens

**Q1-T1c.** Roofs have the highest runoff coefficient overall (0.90). Why?
- a) Roofs absorb large amounts of rainfall
- **b) Roofs are completely impervious, preventing any infiltration ✅**
- c) Roofs have high evapotranspiration
- d) Roofs channel rainfall into groundwater

#### Type 2 — Concept Expansion Spin-offs (Q1)

**Q1-C1.** The rational method formula for estimating storm water runoff quantity is:

$$Q = \frac{C \cdot I \cdot A}{360}$$

where $Q$ is in m³/sec, $I$ is in mm/hour, and $A$ is in hectares. The coefficient 360 in the denominator accounts for unit conversion. If $C = 0.80$, $I = 45\ \text{mm/hr}$, $A = 100\ \text{ha}$, then $Q$ equals:
- a) 8 m³/sec
- **b) 10 m³/sec ✅**
- c) 3.6 m³/sec
- d) 36 m³/sec

> *$Q = (0.80 \times 45 \times 100)/360 = 3600/360 = 10\ \text{m}^3/\text{sec}$*

**Q1-C2.** The overall runoff coefficient for a catchment with mixed land cover is calculated as:

$$C = \frac{A_1C_1 + A_2C_2 + \cdots + A_nC_n}{A_1 + A_2 + \cdots + A_n}$$

For a 300 ha catchment with 15% roofs ($C=0.90$), 15% pavements ($C=0.80$), 25% lawns ($C=0.15$), 20% roads ($C=0.40$), 15% open ground ($C=0.10$), 10% single family ($C=0.50$), the overall $C$ is approximately:
- a) 0.80
- b) 0.55
- **c) 0.44 ✅**
- d) 0.30

> *Slides worked example: $C = (0.15 \times 0.90 + 0.15 \times 0.80 + 0.25 \times 0.15 + 0.20 \times 0.40 + 0.15 \times 0.10 + 0.10 \times 0.50) = 0.44$*

### Q2. Which of the following factors does NOT affect per capita water demand?

| Option | Text |
|--------|------|
| a | Cost of water |
| **b ✅** | **Type of soil in the area** |
| c | Size of the city |
| d | Climate conditions |

**✅ Correct Answer: b**

**Why b is correct:**
The slides list 10 specific factors affecting per capita demand: size of the city, climate conditions, types of gentry and habits of people, industrial and commercial activities, quality of water supplies, pressure in distribution systems, development of sewerage facilities, system of supply, cost of water, and policy of metering and method of charging. **Type of soil** is not listed among these factors. Soil type affects *runoff and infiltration* in hydrology, not the quantity of water people demand for domestic/industrial use.

**Why others are wrong:**
- **a** — Cost of water **is** listed as a factor: higher water cost reduces demand.
- **c** — Size of the city **is** listed as a factor: larger cities have higher industrial and commercial demand.
- **d** — Climate conditions **are** listed as a factor: hotter/drier climates increase domestic and irrigation demand.

#### Type 2 — Concept Expansion Spin-offs (Q2)

**Q2-C1.** Per Capita Demand (PCD) is calculated as:

$$PCD = \frac{\text{Total yearly water requirement of the city (litres)}}{365 \times \text{Design population}}$$

If a city of 500,000 people uses $1.825 \times 10^{10}$ litres per year, the PCD is:
- a) 50 lpcd
- **b) 100 lpcd ✅**
- c) 200 lpcd
- d) 365 lpcd

> *$PCD = 1.825 \times 10^{10} / (365 \times 500000) = 100$ litres/capita/day*

**Q2-C2.** The maximum *hourly* demand is _______ times the average daily demand.
- a) 1.8
- b) 2.0
- **c) 2.7 ✅**
- d) 3.0

> *Slides: Maximum hourly demand $= 1.5 \times 1.8 \times$ Average daily demand $= 2.7 \times$ Average daily demand.*

**Q2-C3.** The maximum *daily* demand is _______ times the average daily demand.
- **a) 1.8 ✅**
- b) 1.5
- c) 2.7
- d) 2.0

> *Slides: "Maximum daily demand = 1.8 × Average daily demand."*

### Q3. What is the permissible limit of fluoride in drinking water to prevent fluorosis?

| Option | Text |
|--------|------|
| a | 0.5 ppm |
| b | 1.0 ppm |
| **c ✅** | **1.5 ppm** |
| d | 2.0 ppm |

**✅ Correct Answer: c**

**Why c is correct:**
Slides state: *"Fluoride – 1.5 ppm; excess of this effects human lungs and other respiratory organs. If fluoride concentration is greater than 1.5 ppm, causing spotting and discolouration of teeth (a disease called fluorosis)."*

**Why others are wrong:**
- **a** — 0.5 ppm is **below** even the dental cavity threshold (0.8–1.0 ppm); this concentration is too low and would not prevent cavities.
- **b** — 1.0 ppm is within the range that *prevents* dental cavity (0.8–1.0 ppm is the beneficial range) but the permissible *upper limit* is 1.5 ppm.
- **d** — 2.0 ppm exceeds the 1.5 ppm limit and would cause fluorosis (spotting/discolouration of teeth).

#### Type 1 — Wrong Option Spin-offs (Q3)

**Q3-T1a.** Below what fluoride concentration (ppm) does dental cavity (tooth decay) occur?
- a) 0.5 ppm
- **b) 0.8–1.0 ppm ✅**
- c) 1.5 ppm
- d) 2.0 ppm

> *Slides: "Fluoride concentration of less than 0.8–1.0 ppm cause dental cavity (tooth decay)."*

#### Type 2 — Concept Expansion Spin-offs (Q3)

**Q3-C1.** Match the permissible limits from the slides:

| Parameter | Limit |
|---|---|
| Iron (Fe) | 0.3 ppm |
| Manganese (Mn) | 0.05 ppm |
| Copper (Cu) | 1.3 ppm |
| Fluoride (F⁻) | 1.5 ppm |
| Sulphate (SO₄) | 250 ppm |

Which metal, if exceeded, causes **discolouration of clothes**?
- **a) Iron (Fe > 0.3 ppm) ✅**
- b) Manganese
- c) Copper
- d) Fluoride

> *Slides: "Iron – 0.3 ppm, excess of these cause discoloration of clothes."*

**Q3-C2.** High concentrations of sulphate in drinking water can cause what health effect when combined with calcium and magnesium?
- a) Fluorosis
- b) Methemoglobinemia
- **c) Laxative effect ✅**
- d) Dental cavity

> *Slides: "High concentrations of sulphate in the water we drink can have a laxative effect when combined with calcium and magnesium."*

### Q4. Maximum daily demand is typically how many times the average daily demand?

| Option | Text |
|--------|------|
| a | 1.5 |
| **b ✅** | **1.8** |
| c | 2.0 |
| d | 2.7 |

**✅ Correct Answer: b**

**Why b is correct:**
Slides explicitly state: *"Maximum daily demand = 1.8 × Average daily demand."*

**Why others are wrong:**
- **a** — 1.5 is the factor applied to maximum *daily* demand to get maximum *hourly* demand ($1.5 \times$ max daily $= 2.7 \times$ average daily). It is not the max daily multiplier.
- **c** — 2.0 is a common misconception but not the slide-stated value.
- **d** — 2.7 is the maximum *hourly* demand factor ($1.5 \times 1.8 = 2.7 \times$ average daily), not the maximum daily factor.

#### Type 1 — Wrong Option Spin-offs (Q4)

**Q4-T1a.** The maximum hourly demand is _______ times the maximum daily demand (and _______ times the average daily demand).
- a) 1.8 times max daily; 2.0 times average
- **b) 1.5 times max daily; 2.7 times average ✅**
- c) 2.7 times max daily; 1.5 times average
- d) 1.0 times max daily; 1.8 times average

#### Type 2 — Concept Expansion Spin-offs (Q4)

**Q4-C1.** Total draft/demand for water supply design must account for:
- a) Average daily demand only
- b) Maximum hourly demand only
- **c) The greater of (maximum daily demand + fire demand) OR (maximum hourly demand) ✅**
- d) Minimum daily demand + average demand

> *Slides: "Total draft/demand: i. Maximum daily demand + Fire demand; ii. Maximum hourly demand."*

**Q4-C2.** Fire demand formulas such as Kuichling's, Buston's, and Freeman's all express fire demand in:
- a) m³/sec
- **b) litres/min ✅**
- c) litres/day
- d) m³/day

> *Slides: "Q obtained is in liters/min; P is the population of a city."*

### Q5. A catchment area of 200 hectares has: Roofs (20%, C=0.9), Pavements (30%, C=0.8), Lawns (50%, C=0.15). Calculate the overall runoff coefficient.

| Option | Text |
|--------|------|
| **a ✅** | **0.50** |
| b | 0.63 |
| c | 0.70 |
| d | 0.45 |

**✅ Correct Answer: a**

**Why a is correct:**

$$C = \frac{A_1C_1 + A_2C_2 + A_3C_3}{A_1 + A_2 + A_3}$$

Since proportions sum to 1 (20% + 30% + 50% = 100%):

$$C = (0.20 \times 0.9) + (0.30 \times 0.8) + (0.50 \times 0.15)$$

$$C = 0.18 + 0.24 + 0.075 = 0.495 \approx 0.50$$

**Why others are wrong:**
- **b** — 0.63 would result from a higher proportion of impervious surfaces.
- **c** — 0.70 would imply nearly all impervious cover.
- **d** — 0.45 is close but slightly low; the calculation gives 0.495 which rounds to 0.50.

#### Type 2 — Concept Expansion Spin-offs (Q5)

**Q5-C1.** Using the catchment from Q5 (C = 0.495 ≈ 0.50) with a rainfall intensity of 40 mm/hr and area of 200 ha, the storm water runoff Q is:
- a) 5.6 m³/sec
- **b) Approximately 11 m³/sec ✅**
- c) 14 m³/sec
- d) 1.4 m³/sec

> *$Q = C \cdot I \cdot A / 360 = 0.495 \times 40 \times 200/360 \approx 11\ \text{m}^3/\text{sec}$*

> ⚠️ **Note:** Q6 uses $C = 0.63$, not the Q5 result. Both Q5 and Q6 are independent problems with different given values.

### Q6. If the intensity of rainfall is 40 mm/hour and the runoff coefficient is 0.63 for a catchment area of 200 hectares, what is the storm water runoff Q in m³/sec?

| Option | Text |
|--------|------|
| a | 5.6 m³/sec |
| b | 5 m³/sec |
| **c ✅** | **14 m³/sec** |
| d | 1.4 m³/sec |

**✅ Correct Answer: c**

**Why c is correct:**

$$Q = \frac{C \cdot I \cdot A}{360} = \frac{0.63 \times 40 \times 200}{360} = \frac{5040}{360} = 14\ \text{m}^3/\text{sec}$$

**Why others are wrong:**
- **a** — 5.6 m³/sec: back-check gives $5.6 = C \times 40 \times 200/360 \Rightarrow C = 0.252$ — inconsistent with given $C = 0.63$.
- **b** — 5 m³/sec: corresponds to $C \approx 0.225$ — wrong.
- **d** — 1.4 m³/sec: corresponds to $C \approx 0.063$ — an order of magnitude too low.

#### Type 2 — Concept Expansion Spin-offs (Q6)

**Q6-C1.** In the rational method $Q = CIA/360$, the intensity $I$ used must be for a duration equal to:
- a) 24 hours
- b) 1 hour
- **c) The time of concentration of the catchment ✅**
- d) The recurrence interval

> *Slides: "$I$ = Intensity of rainfall (mm/hour) for the duration equal to time of concentration."*

### Q7. Using the Hazen-Williams equation, estimate the head loss in a pipe with diameter 0.3 m, length 5 m, flow rate 1.2 m³/s, Hazen-Williams coefficient $C_h = 130$.

| Option | Text |
|--------|------|
| a | 4.5 m |
| **b ✅** | **3.2 m** |
| c | 6.1 m |
| d | 7.0 m |

**✅ Correct Answer: b**

**Why b is correct:**
The Hazen-Williams equation in the slides is:

$$V = 0.85\, C_h\, R^{0.63}\, S^{0.54}$$

where $R = D/4$ (hydraulic radius for full circular pipe) and $S = h_f/L$.

For head loss, using the derived form:

$$h_f = \frac{10.67 \times L \times Q^{1.852}}{C_h^{1.852} \times D^{4.87}}$$

Substituting: $L=5$, $Q=1.2$, $C_h=130$, $D=0.3$:

$$h_f = \frac{10.67 \times 5 \times (1.2)^{1.852}}{(130)^{1.852} \times (0.3)^{4.87}} \approx 3.2\ \text{m}$$

**Why others are wrong:**
All other options (4.5, 6.1, 7.0 m) result from incorrect substitution of values or use of wrong formula terms.

#### Type 1 — Wrong Option Spin-offs (Q7)

**Q7-T1a.** Which equation is an alternative to the Hazen-Williams equation for designing pressure conduits?
- a) Stokes' Law
- **b) Darcy-Weisbach equation ✅**
- c) Fick's Law
- d) Bernoulli's equation

> *Slides: "To design pressure conduits: Darcy's Weisbach equation OR Hazen Williams equation."*

#### Type 2 — Concept Expansion Spin-offs (Q7)

**Q7-C1.** The Darcy-Weisbach equation for head loss in a pipe is:

$$h_f = \frac{fLV^2}{2gd} = \frac{fLQ^2}{12.1\, d^5}$$

A pipeline of length $L = 8000\ \text{m}$, diameter $d = 0.4\ \text{m}$, and friction factor $f = 0.003$ carries a flow of $Q = 0.231\ \text{m}^3/\text{s}$. The head loss is approximately:
- a) 5 m
- **b) 10 m ✅**
- c) 20 m
- d) 50 m

> *Slides Example: $h_f = 0.003 \times 8000 \times (0.231)^2 / (12.1 \times (0.4)^5) = 10\ \text{m}$*

**Q7-C2.** The hydraulic radius $R$ for a full circular pipe of diameter $D$ is:
- a) $D$
- b) $D/2$
- **c) $D/4$ ✅**
- d) $\pi D/4$

> *Slides: $R = \text{wetted area}/\text{wetted perimeter} = \frac{\pi D^2/4}{\pi D} = D/4$*

### Q8. If the population of a city in 2021 is 2,000,000 and it grows at 1.5% annually, predict its population in 2031 using the Geometrical Increase Method.

| Option | Text |
|--------|------|
| **a ✅** | **2,030,000** |
| b | 2,548,008 |
| c | 2,817,048 |
| d | 3,125,620 |

**✅ Correct Answer: a**

**Why a is correct:**
The Geometrical Increase Method formula is:

$$P_n = P\left(1 + \frac{I_G}{100}\right)^n$$

where $n$ is in **decades**. Since 2021 to 2031 = 1 decade, $n = 1$:

$$P_{2031} = 2{,}000{,}000 \times \left(1 + \frac{1.5}{100}\right)^1 = 2{,}000{,}000 \times 1.015 = 2{,}030{,}000$$

**Why others are wrong:**
- **b** — 2,548,008 would result from applying the rate annually for 10 years: $2{,}000{,}000 \times (1.015)^{10} \approx 2{,}320{,}000$ — still not matching; likely a different rate was assumed.
- **c & d** — Much larger values imply higher growth rates or longer periods.

> ⚠️ **Important:** The Geometrical Increase Method uses $n$ in *decades* as per the slides (census data is per-decade). When the problem states "1.5% annually," $n = 1$ decade means **1 decade of growth**, and $I_G = 1.5\%$ is the rate per decade here.

#### Type 1 — Wrong Option Spin-offs (Q8)

**Q8-T1a.** Which population forecasting method is suitable for *new industrial towns* at the beginning of development (tends to give higher estimates)?
- a) Arithmetical Increase Method
- **b) Geometrical Increase Method ✅**
- c) Incremental Increase Method
- d) Logistic Curve Method

> *Slides: "This method gives higher values and hence should be applied for a new industrial town at the beginning of development for only few decades."*

#### Type 2 — Concept Expansion Spin-offs (Q8)

**Q8-C1.** In the Geometrical Increase Method, the geometric mean $I_G$ is calculated from the individual decade growth rates $r_1, r_2, \ldots, r_n$ as:
- a) Arithmetic mean of $r_1, r_2, \ldots$
- **b) $(r_1 \times r_2 \times \cdots \times r_n)^{1/n}$ ✅**
- c) $(r_1 + r_2 + \cdots + r_n)/n$
- d) Maximum of $r_1, r_2, \ldots, r_n$

**Q8-C2.** The Logistic Curve method is most appropriate when:
- a) The city is newly established with rapid growth
- **b) The city approaches a saturation population and growth is S-shaped ✅**
- c) Only one census record is available
- d) Population is declining

> *Slides give the logistic equation: $P = P_s / (1 + m \cdot e^{-nt})$ which approaches saturation population $P_s$.*

### Q9. If the average increment is 8,000 and the incremental increase is 1,000, what is the population in 2021 using the Incremental Increase Method, given the 2011 population was 28,000?

| Option | Text |
|--------|------|
| a | 35,000 |
| b | 36,000 |
| **c ✅** | **37,000** |
| d | 38,000 |

**✅ Correct Answer: c**

**Why c is correct:**
The Incremental Increase Method formula from the slides:

$$P_n = P + n \cdot X + \frac{n(n+1)}{2} \cdot Y$$

Given: $P = 28{,}000$, $X = 8{,}000$ (average increment), $Y = 1{,}000$ (incremental increase), $n = 1$ decade (2011→2021):

$$P_{2021} = 28{,}000 + (1 \times 8{,}000) + \frac{1 \times 2}{2} \times 1{,}000$$

$$= 28{,}000 + 8{,}000 + 1{,}000 = 37{,}000$$

**Why others are wrong:**
- **a** — 35,000 = $28,000 + 7,000$; missing both $X$ and $Y$ components correctly.
- **b** — 36,000 = $28,000 + 8,000$; ignores the $Y$ incremental correction.
- **d** — 38,000 = $28,000 + 10,000$; overestimates the incremental correction.

#### Type 1 — Wrong Option Spin-offs (Q9)

**Q9-T1a.** Which population method formula is $P_n = P + n \cdot C$ (constant increment per decade)?
- **a) Arithmetical Increase Method ✅**
- b) Geometrical Increase Method
- c) Incremental Increase Method
- d) Logistic Curve Method

> *Slides: "Population after $n$th decade: $P_n = P + n \cdot C$ where $C$ = average increase per decade."*

#### Type 2 — Concept Expansion Spin-offs (Q9)

**Q9-C1.** The Incremental Increase Method is a modification of the Arithmetical Increase Method and is most suitable for:
- a) A new rapidly industrializing city
- **b) An average-sized town under normal conditions where growth rate is in increasing order ✅**
- c) A large old city with considerable existing development
- d) A declining population

> *Slides: "This method is suitable for an average size town under normal condition where the growth rate is found to be in increasing order."*

**Q9-C2.** In the Incremental Increase Method for $n = 2$ decades from a base population of 28,000, with $X = 8,000$ and $Y = 1,000$, the projected population is:
- a) 44,000
- b) 45,000
- **c) 47,000 ✅**
- d) 50,000

> *$P_2 = 28000 + (2 \times 8000) + \frac{2 \times 3}{2} \times 1000 = 28000 + 16000 + 3000 = 47000$*

### Q10. A water sample has 100 mg/L of Ca²⁺ and 120 mg/L of Mg²⁺. Calculate the total hardness in mg/L as CaCO₃.

| Option | Text |
|--------|------|
| a | 500 mg/L |
| b | 520 mg/L |
| **c ✅** | **750 mg/L** |
| d | 560 mg/L |

**✅ Correct Answer: c**

**Why c is correct:**
The slides give the formula (equivalent weights: CaCO₃ = 50, Ca = 20, Mg = 12):

$$TH = \left[Ca^{2+} \times \frac{EW_{CaCO_3}}{EW_{Ca}}\right] + \left[Mg^{2+} \times \frac{EW_{CaCO_3}}{EW_{Mg}}\right]$$

$$TH = \left[100 \times \frac{50}{20}\right] + \left[120 \times \frac{50}{12}\right]$$

$$= 250 + 500 = 750\ \text{mg/L as CaCO}_3$$

**Why others are wrong:**
- **a** — 500 mg/L would result from computing only the Mg component ($120 \times 50/12 = 500$) and ignoring Ca.
- **b** — 520 mg/L uses wrong equivalent weight ratios.
- **d** — 560 mg/L similarly results from incorrect equivalent weight conversion.

#### Type 2 — Concept Expansion Spin-offs (Q10)

**Q10-C1.** Hard water is undesirable because (select all that apply from slides):
- **a) It leads to greater soap consumption, scaling of boilers, and corrosion of pipes ✅**
- b) It causes dental fluorosis
- c) It depletes dissolved oxygen
- d) It increases turbidity

> *Slides: "Hard waters are undesirable because they may lead to greater soap consumption, scaling of boilers, causing corrosion and incrustation of pipes, making food tasteless."*

**Q10-C2.** Which type of hardness can be removed by simple boiling?
- **a) Temporary (carbonate) hardness ✅**
- b) Permanent (non-carbonate) hardness
- c) Both types
- d) Neither type

> *Slides: "Temporary Hardness: this hardness can be removed to some extent by simple boiling or to full extent by adding lime to water."*

**Q10-C3.** If the total alkalinity of a sample (as CaCO₃) is 200 mg/L and total hardness is 300 mg/L, then carbonate hardness and non-carbonate hardness are:
- a) CH = 300, NCH = 0
- **b) CH = 200, NCH = 100 ✅**
- c) CH = 0, NCH = 300
- d) CH = 150, NCH = 150

> *Slides: "If TH > Alkalinity, then CH = Alkalinity; NCH = TH − CH = 300 − 200 = 100 mg/L."*

### Q11. The main cause of methemoglobinemia (Blue Baby Syndrome) is excess of:

| Option | Text |
|--------|------|
| a | Fluoride |
| **b ✅** | **Nitrates > 45 mg/L** |
| c | Nitrites > 45 mg/L |
| d | Hardness |

**✅ Correct Answer: b**

**Why b is correct:**
Slides state: *"Nitrates in water is not harmful [to adults]. However the presence of too much of nitrates in water may adversely affect the health of infants causing a disease called methemoglobinemia commonly called blue baby disease. The nitrate concentration in domestic water supplies is limited to 45 mg/L."*

**Why others are wrong:**
- **a** — Fluoride causes **fluorosis** (spotting/discolouration of teeth) at > 1.5 ppm, not methemoglobinemia.
- **c** — Nitrites are *intermediates* in the nitrogen cycle. The slides state nitrites are highly dangerous and permissible amount should be nil, but the *named* cause of Blue Baby Syndrome specifically is **nitrates** exceeding 45 mg/L.
- **d** — Hardness causes scaling, soap inefficiency, and pipe corrosion — not methemoglobinemia.

#### Type 1 — Wrong Option Spin-offs (Q11)

**Q11-T1a.** Excess fluoride (> 1.5 ppm) in drinking water causes:
- a) Methemoglobinemia
- b) Cholera
- **c) Fluorosis (spotting and discolouration of teeth) ✅**
- d) Typhoid

**Q11-T1b.** Which nitrogen form in water indicates that organic matter is *fully* oxidized (representing old/historical pollution)?
- a) Free ammonia
- b) Organic nitrogen
- c) Nitrites
- **d) Nitrates ✅**

> *Slides: "Nitrates: It indicates fully oxidized organic matter in water (representing old pollution)."*

#### Type 2 — Concept Expansion Spin-offs (Q11)

**Q11-C1.** Free ammonia in water (should not exceed 0.15 mg/L) indicates:
- **a) The very first stage of decomposition of organic matter ✅**
- b) Fully oxidized, old pollution
- c) Absence of any biological activity
- d) Industrial chemical contamination only

**Q11-C2.** Nitrite (NO₂⁻) in water is considered:
- a) Safe in any concentration
- b) Harmless below 45 mg/L
- **c) Highly dangerous; permissible limit is nil ✅**
- d) A sign of fully treated water

> *Slides: "Nitrites is highly dangerous and therefore the permissible amount of nitrites in water should be nil."*

### Q12. Which of the following is NOT a component of the hydrologic cycle?

| Option | Text |
|--------|------|
| a | Evaporation |
| b | Condensation |
| c | Precipitation |
| **d ✅** | **Sedimentation** |

**✅ Correct Answer: d**

**Why d is correct:**
The slides illustrate the hydrologic cycle components as: Transpiration, Evaporation, Condensation, Precipitation, Snowmelt Runoff, and Surface Runoff. **Sedimentation** is a geological/physical process (particles settling in water bodies) — it is part of geomorphology, not the hydrologic cycle.

**Why others are wrong:**
- **a** — Evaporation is explicitly shown in the hydrologic cycle diagram in the slides.
- **b** — Condensation is explicitly shown (water vapour condenses to form clouds).
- **c** — Precipitation (rain, snow, hail) is explicitly shown.

#### Type 2 — Concept Expansion Spin-offs (Q12)

**Q12-C1.** In the hydrologic cycle, units of water transfer are typically expressed as:
- a) m³/sec
- **b) 10¹² m³/year ✅**
- c) mm/day
- d) litres/capita/day

> *Slides: "The Hydrologic Cycle. Units of water transfer are $10^{12}\ \text{m}^3/\text{year}$."*

**Q12-C2.** A watershed is defined as:
- **a) An area of land where all water drains into the same collection point ✅**
- b) The zone below the water table
- c) A reservoir built for water storage
- d) The boundary between surface and groundwater

> *Slides: "A Watershed is an area of land where all of the water that is under it, or drains off of it collects into the same place."*

### Q13. Which population forecasting method assumes a constant rate of increase?

| Option | Text |
|--------|------|
| **a ✅** | **Arithmetical Increase Method** |

> ⚠️ **Assignment answer says b (Arithmetic Increase Method). The option labelling in the assignment is: (a) Geometric, (b) Arithmetic, (c) Incremental, (d) Logistic. Correct answer is the Arithmetic Increase Method — option b in the assignment, reproduced below with the assignment's original option labels.**

| Option | Text |
|--------|------|
| a | Geometric Increase Method |
| **b ✅** | **Arithmetic Increase Method** |
| c | Incremental Increase Method |
| d | Logistic Curve Method |

**✅ Correct Answer: b (Arithmetic Increase Method)**

**Why b is correct:**
Slides state: *"In this method… it is assumed that the population is increasing at constant rate."* The formula $P_n = P + n \cdot C$ adds a fixed constant $C$ each decade — constant rate of increase.

**Why others are wrong:**
- **a** — **Geometric method** assumes a constant *percentage* increase (growth rate), not a constant absolute increment.
- **c** — **Incremental method** accounts for *changing* rates of increase (the rate itself increases decade by decade).
- **d** — **Logistic curve** follows an S-shaped growth curve, with rate initially increasing then decreasing toward a saturated population.

#### Type 1 — Wrong Option Spin-offs (Q13)

**Q13-T1a.** Which population forecasting method assumes a *constant percentage* increase per decade?
- a) Arithmetic Increase Method
- **b) Geometric Increase Method ✅**
- c) Incremental Increase Method
- d) Master Plan Method

**Q13-T1b.** Which method is most appropriate for *large, old cities with considerable development* (slides text)?
- **a) Arithmetic Increase Method ✅**
- b) Geometric Increase Method
- c) Logistic Curve Method
- d) Comparative Graphical Method

> *Slides: "Arithmetic Increase Method: suitable for large and old city with considerable development."*

#### Type 2 — Concept Expansion Spin-offs (Q13)

**Q13-C1.** Which population forecasting method divides the city into zones with fixed population densities as per a 25–30 year city plan?
- a) Geometric Increase Method
- b) Incremental Increase Method
- **c) Master Plan Method ✅**
- d) Logistic Curve Method

> *Slides: "The master plan is prepared for next 25 to 30 years for the city… population densities are fixed for various zones."*

### Q14. A pipeline delivers water 5 km away. Pipe diameter = 0.4 m, friction factor $f$ = 0.002, $v$ = 3 m/sec. Determine head loss using Darcy-Weisbach.

| Option | Text |
|--------|------|
| a | 5.2 m |
| b | 6.8 m |
| **c ✅** | **11.5 m** |
| d | 8.4 m |

**✅ Correct Answer: c**

**Why c is correct:**
Darcy-Weisbach equation from slides: $h_f = fLV^2 / (2gd)$

$$h_f = \frac{0.002 \times 5000 \times (3)^2}{2 \times 9.81 \times 0.4} = \frac{0.002 \times 5000 \times 9}{7.848} = \frac{90}{7.848} \approx 11.5\ \text{m}$$

**Why others are wrong:**
All other values result from incorrect substitution (e.g., using $L = 5$ instead of $L = 5000$, or wrong $g$ value).

#### Type 2 — Concept Expansion Spin-offs (Q14)

**Q14-C1.** A town of 100,000 people uses 200 lpcd. Source is 8 km away with elevation difference of 10 m, friction factor $f = 0.003$. The required pipe diameter (using $h_f = fLQ^2/12.1d^5$) is approximately:
- a) 0.2 m
- b) 0.3 m
- **c) 0.4 m ✅**
- d) 0.6 m

> *Slides worked example: $Q = 100000 \times 200\ \text{l/day} = 0.231\ \text{m}^3/\text{s}$; solving gives $d = 0.4$ m.*

### Q15. If a water sample has a pH of 8, what is its hydroxide ion concentration [OH⁻] in mol/L?

| Option | Text |
|--------|------|
| a | $1 \times 10^{-9}$ |
| b | $1 \times 10^{-5}$ |
| **c ✅** | **$1 \times 10^{-6}$** |
| d | $1 \times 10^{-1}$ |

**✅ Correct Answer: c**

**Why c is correct:**
Using the relationship from the slides:

$$pH + pOH = 14$$

$$pOH = 14 - 8 = 6$$

$$[OH^-] = 10^{-pOH} = 10^{-6}\ \text{mol/L}$$

**Why others are wrong:**
- **a** — $10^{-9}$ corresponds to $pOH = 9$, which would require $pH = 5$ (acidic), not 8.
- **b** — $10^{-5}$ corresponds to $pOH = 5$, which would require $pH = 9$.
- **d** — $10^{-1}$ corresponds to $pOH = 1$ ($pH = 13$, strongly alkaline).

#### Type 1 — Wrong Option Spin-offs (Q15)

**Q15-T1a.** A water sample has $[H^+] = 10^{-9}\ \text{mol/L}$. What is its pH?
- a) 6
- b) 7
- **c) 9 ✅**
- d) 14

> *$pH = -\log[H^+] = -\log(10^{-9}) = 9$*

**Q15-T1b.** A water sample has pH = 5. What is its $[OH^-]$?
- **a) $10^{-9}$ mol/L ✅**
- b) $10^{-5}$ mol/L
- c) $10^{-6}$ mol/L
- d) $10^{-14}$ mol/L

> *$pOH = 14 - 5 = 9$; $[OH^-] = 10^{-9}$*

#### Type 2 — Concept Expansion Spin-offs (Q15)

**Q15-C1.** If $[H^+]$ concentration is $10^{-6}$ mol/L, then pOH equals:
- a) 6
- **b) 8 ✅**
- c) 14
- d) 20

> *Slides example: $pH = 6$; $pOH = 14 - 6 = 8$*

**Q15-C2.** Which pH indicator changes from yellow to red in the range 6.8–8.4?
- a) Methyl orange
- b) Methyl red
- **c) Phenol red ✅**
- d) Phenolphthalein

> *Slides pH indicator table: "Phenol red: pH range 6.8–8.4, Original color: Yellow, Final color: Red."*

**Q15-C3.** Alkalinity in water is caused by the presence of:
- a) Sulphates and chlorides of calcium
- **b) Bicarbonates and carbonates of calcium/magnesium, or hydroxides of sodium/potassium ✅**
- c) Fluoride and nitrates
- d) Iron and manganese

> *Slides: "The alkalinity is caused by the presence of bicarbonate of calcium and magnesium or by the carbonates of hydroxides of sodium, potassium, calcium and magnesium."*

---

*Document compiled from: `Week-7-Assignment-and-Solution.pdf` and `Week-7-mooc-9.pdf` (NOC25_GE17, IIT Kharagpur)*
*All content traceable to provided slides and assignment sheet.*
