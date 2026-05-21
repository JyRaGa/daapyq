# Week 5: Environmental Biological Aspects – Oxygen Demand, Water Quality & Nutrient Cycles
**Course:** Introduction to Environmental Engineering and Science – Fundamentals and Sustainability Concepts
**Institute:** IIT Kharagpur (NPTEL) | **Lectures:** 21–25

---

## PART A — SLIDE CONTENT (Lecture-wise)

---

### Lecture 21: Oxygen Demand in Environmental Systems

#### Major Organism Groups (Environmental Importance)
- Viruses, Bacteria, Fungi, Algae, Protozoa, Macrophytes, Fish, Rotifers, Micro-crustaceans, Macro-invertebrates
- Algae are particularly significant — used for **biodiesel production**.

---

#### Oxygen Demand — Definition
**BOD** = a chemical procedure for determining the amount of dissolved oxygen needed by aerobic biological organisms in a body of water to break down organic material at a certain temperature over a specific time period.

#### Decomposition Pathways

**Aerobic decomposition:**
$$\text{Organic matter} + O_2 \xrightarrow{\text{Microbes}} CO_2 + H_2O + \text{New cells} + \text{Stable products (NO}_3^-, PO_4^{3-}, SO_4^{2-}\text{)}$$

**Anaerobic decomposition:**
$$\text{Organic matter} \xrightarrow{\text{Microbes}} CO_2 + H_2O + \text{New cells} + \text{Unstable products (H}_2S, NH_3, CH_4\text{)}$$

> Key distinction: Aerobic products are "stable" (fully oxidized); anaerobic products are "unstable" (reduced, odorous — H₂S, NH₃, CH₄).

---

#### Oxygen Demand — Definitions & Notation Table

| Notation | Definition |
|---|---|
| **BOD** | Biochemical oxygen demand — amount of oxygen utilized by **microorganisms** in oxidizing carbonaceous and nitrogenous organic matter. |
| **CBOD** | Carbonaceous BOD — electron donor is carbonaceous organic matter. |
| **NBOD** | Nitrogenous BOD — electron donor is nitrogenous organic matter. |
| **ThOD** | Theoretical oxygen demand — oxygen utilized assuming all organic matter is biodegradable. |
| **BOD₅** | 5-day BOD — oxygen consumed over 5-day incubation at 20°C; standard lab estimate. Notation: y₅. |
| **BODᵤ** | Ultimate BOD — oxygen consumed when all biodegradable matter is oxidized. Notation: L₀. |
| **COD** | Chemical oxygen demand — amount of **chemical oxidant** (expressed as O₂ equivalent) required to **completely oxidize** organic matter; COD ≈ ThOD. |

---

#### BOD of Selected Waste Streams

| Origin | BOD₅ (mg O₂/L) |
|---|---|
| River | 2 |
| Domestic Wastewater | 200 |
| Pulp and Paper mill | 400 |
| Commercial laundry | 2,000 |
| Sugar beet factory | 10,000 |
| Tannery | 15,000 |
| Brewery | 25,000 |
| Cherry-canning factory | 55,000 |

---

#### Steps to Calculate Carbonaceous ThOD

| Step | Description | Example (Benzene C₆H₆) |
|---|---|---|
| **Step 1** | Write the oxidation reaction (C → CO₂, H → H₂O) | C₆H₆ + O₂ → CO₂ + H₂O |
| **Step 2** | Balance: (a) Carbon, (b) Hydrogen, (c) Oxygen | C₆H₆ + **7.5O₂** → 6CO₂ + 3H₂O |
| **Step 3** | Apply stoichiometry with unit conversions | 156 mg benzene/L × (1 mol/78 g) × (7.5 mol O₂/mol) × (32 g/mol) = **480 mg O₂/L** |

**Glucose worked example (from Q3):**
$$C_6H_{12}O_6 + 6O_2 \rightarrow 6CO_2 + 6H_2O$$
MW glucose = 180 g/mol; MW 6O₂ = 192 g/mol → ThOD = **192/180 = 1.07 mg O₂/mg glucose**

---

#### Worked Example: Combined Carbonaceous + Nitrogenous ThOD
A waste contains 300 mg/L of C(H₂O) and 50 mg/L of NH₃-N. Calculate total ThOD.

**Carbonaceous:**
$$C(H_2O) + O_2 \rightarrow CO_2 + H_2O$$
300 mg/L × (1 mol/30 g) × (1 mol O₂/mol) × (32 g/mol) = **320 mg/L**

**Nitrogenous:**
$$NH_3 + 2O_2 \rightarrow NO_3^- + H^+ + H_2O$$
50 mg NH₃-N/L × (1 mol/14 g N) × (2 mol O₂/mol) × (32 g/mol) = **229 mg/L**

**Total ThOD = 320 + 229 = 549 mg/L**

---

#### BOD Test Procedure
1. Prepare dilution water (add CaCl₂, MgSO₄, FeCl₃, Phosphate buffer)
2. Add field sample to BOD bottles + dilution water
3. Titrate initial sample for DO (blank + sample)
4. Incubate at **20°C for 5 days**
5. Titrate final DO

**BOD₅ Formula:**
$$\boxed{BOD_5 = \frac{DO_i - DO_f}{P}}$$

- DOᵢ = Initial dissolved oxygen (mg/L)
- DO_f = Final dissolved oxygen after 5 days (mg/L)
- P = Dilution factor = Volume of wastewater / Total volume

---

### Lecture 22: BOD Examples, Oxygen in Surface Waters, COD

#### BOD Calculation Examples

**Example (Slide):** 10 mL sewage + dilution water = 300 mL; initial DO = 9.0 mg/L.
Required: ≥2.0 mg/L DO drop; ≥2.0 mg/L DO remaining.

P = 10/300:
- Minimum BOD₅ = 2.0 / (10/300) = **60 mg/L**
- Maximum BOD₅ = (9.0 − 2.0) / (10/300) = **210 mg/L**
→ This dilution works for BOD₅ between **60–210 mg/L**

**Example (Slide):** 2.5 mL sewage diluted to 250 mL; DO₀ = 8 mg/L; DO₅ = 5 mg/L.
- Dilution ratio = 250/2.5 = 100; ΔDO = 3 mg/L
- BOD = 3 × 100 = **300 mg/L**

**Homework (appears as Q7 in assignment):** 2% solution, DO depletion = 4 ppm → P = 0.02
- BOD = 4 / 0.02 = **200 mg/L**

---

#### Ganga River BOD Data (CPCB)

| Location | BOD 2013 (mg/L) | BOD 2017 (mg/L) |
|---|---|---|
| Haridwar | 7.8 | 6.6 |
| Varanasi | 5.1 | 6.1 |
| Patna | 2.7 | 2.8 |

**Interpretation key (CPCB):**
- BOD < 2 mg/L → Safe for drinking after disinfection
- BOD 2–3 mg/L → Fit for bathing only
- BOD > 3 mg/L → Requires full treatment; not safe for bathing

---

#### COD Procedure

1. Take 2.5 mL water sample in a tube
2. Add 1.5 mL Potassium dichromate (K₂Cr₂O₇)
3. **Keep in COD digestor at 150°C for 2 hours** (tightly closed)
4. Carefully add 3.5 mL sulphuric acid reagent
5. After cooling, transfer to conical flask
6. Titrate against Ferrous Ammonium Sulphate (FAS) with **Ferroin indicator**
7. Endpoint: colour changes to **reddish brown**

> Why COD ≥ BOD: K₂Cr₂O₇ in concentrated H₂SO₄ at 150°C oxidizes both biodegradable AND non-biodegradable organic matter.

#### Discharge Limits (India — CPCB)
| Parameter | Limit in Surface Water |
|---|---|
| BOD | **30 mg/L** |
| COD | **250 mg/L** |

---

### Lecture 23: Environmental Health Basics & SDGs

#### Environmental Health Science
The study of those factors in the environment that affect human health:
- Pollutants in air, water, and soil transferred to humans by **inhalation, ingestion, or absorption**.
- Results in adverse health effects.

#### Basic Requirements for a Healthy Environment (Slide)
- **Clean air, water and soil**
- **Safe and adequate food**
- **Stable global peaceful environment**

#### Target Areas (Environmental Health)
- Water supplies; Wastewater treatment; Waste management
- Prevention and control of land pollution and vector control
- Food hygiene and safety; Air quality management
- Environmental radiation hazards; Occupational health; Noise management

---

#### Types of Pathogens in Wastewater

| Type | Details |
|---|---|
| **Bacteria** | Faeces of healthy person: >10¹⁰ bacteria/g; mostly non-pathogenic; infection causes diarrhoea, cholera |
| **Viruses** | Faeces: >10⁹/g; adenoviruses, enteroviruses, Hepatitis A, reoviruses, rotavirus |
| **Protozoa** | Cause diarrhoea, dysentery via ingested cysts; *Giardia lamblia*, *Balantidium coli*, *Entamoeba histolytica* |
| **Helminths** | Parasitic worms; eggs/larvae in excreta; *Ascaris*, *Trichuris* |

#### Waterborne Disease Classification (Slide)

| Category | Diseases |
|---|---|
| **Viral** | Hepatitis A, Hepatitis E, Rotavirus diarrhoea |
| **Bacterial** | Typhoid & Paratyphoid, Bacillary dysentery, Cholera, *E. coli* diarrhoea |
| **Protozoal** | Amoebiasis, Giardiasis |
| **Helminthic** | Round worm, Thread worm, Hydatid disease |

> **E. coli** is used as a fecal indicator because it is abundant (>10¹⁰/g in faeces) and signals potential presence of all other pathogens.

#### SDG 6 — Clean Water and Sanitation
- 1.5 billion people have no sanitation service at health facilities
- Cholera can kill within hours but is easily treated
- 1 in 4 health facilities lacks basic water services
- Jakarta: 1.3M m³/day sewage generated; only **3%** treated
- Sydney: 1.2M m³/day generated; **~100%** treated

---

### Lecture 24: Field Applications — Composting, Anaerobic Digestion, MFC

#### Biological Methods of Waste Treatment
- Composting, Anaerobic digestion, Microbial fuel cell, Bioremediation

#### Composting (Solid Waste)
- Transformation of organic material through decomposition into a **soil-like material**.
- Invertebrates (insects, earthworms) + microorganisms (bacteria, fungi) facilitate transformation.
- Benefits: reduces waste volume + produces **soil improver** (reduces need for chemical fertilizers; improves drought resistance).
- Can be done at household, community, or commercial scale.

**Compost inputs/outputs:**
- Inputs: Organic matter + Minerals + Water + Micro-organisms + Oxygen
- Outputs: Heat + Water + CO₂ + **Finished compost** (organic matter, minerals, microbes)

---

#### Anaerobic Digestion

**4-Stage Biochemical Pathway:**

| Stage | Products |
|---|---|
| **1. Hydrolysis** | Soluble organic molecules (sugars, amino acids, fatty acids) |
| **2. Acidogenesis** | Alcohols, carbonic acids, volatile fatty acids |
| **3. Acetogenesis** | **Acetic acid (CH₃COOH), H₂, CO₂** |
| **4. Methanogenesis** | **CH₄ + CO₂** (biogas) |

Simplified: Organic matter → sugars/amino acids/fatty acids → H₂, CO₂, organic acids → **Biogas (CH₄, CO₂, H₂S)**

**Applications of anaerobic digestion:**
- Waste and wastewater treatment
- Reduces landfill gas emissions
- **Power generation**
- Fertilizer and soil conditioner
- **Cooking gas**
- **Vehicle fuel**

---

#### Microbial Electrolysis Cell (MFC)
A bio-electrochemical system that drives an electric current using bacteria mimicking bacterial interactions in nature.

Process: Plant waste → fermentation → **acetic acid** → bacteria consume it (releasing electrons, protons, CO₂) → >0.2V added externally → electrons + protons form **hydrogen gas** → clean fuel.

Benefits: Direct electricity generation, no aeration needed, low sludge yield, decentralized treatment, low carbon footprint.

---

### Lecture 25: Nutrient Cycles

#### Water Cycle
Processes: Evaporation → Condensation → Infiltration → Surface runoff

---

#### Carbon Cycle
The biogeochemical cycle by which carbon is exchanged among biosphere, pedosphere, geosphere, hydrosphere, and atmosphere.

**Carbon Sinks (largest to smallest active sink):**
- **Lithosphere** — limestone (**largest reservoir** overall)
- **Hydrosphere** — ocean (**largest active sink**, 2nd largest reservoir)
- **Atmosphere** — in form of CO₂
- **Biosphere** — wood, plants, dead animals

> The ocean is the dominant **active** carbon sink, absorbing ~25–30% of anthropogenic CO₂.

---

#### Oxygen Cycle
- Essential for animals during respiration; released by plants during photosynthesis.
- Cycles similarly to the carbon cycle.
- **Threats:** Forest deforestation, ocean pollution.

---

#### Nitrogen Cycle
- Makes up **78%** of the troposphere by volume.
- Most complex biogeochemical cycle.
- N₂ gas **cannot be used directly** by most organisms — must be "fixed" first.
- The **triple bond** in N₂ makes it relatively inert (like a noble gas).

**Forms of Nitrogen:**
- Urea: CO(NH₂)₂ | Ammonia: NH₃ (gas) | Ammonium: NH₄⁺
- Nitrate: NO₃⁻ | Nitrite: NO₂⁻ | Atmospheric dinitrogen: N₂ | Organic N

**Steps of the Nitrogen Cycle:**
1. **N₂ Fixation** → N₂ → NH₃/NH₄⁺ (conversion to usable form)
2. **Ammonification** (Mineralization) → Organic N → NH₄⁺ (decomposers: bacteria, fungi)
3. **Nitrification** → NH₄⁺ → NO₂⁻ → NO₃⁻ (nitrifying bacteria)
4. **Assimilation** → NO₃⁻/NH₄⁺ → Organic N (plants/animals incorporate into proteins, DNA, RNA)
5. **Denitrification** → NO₃⁻ → N₂ gas (returned to atmosphere)

**Types of Nitrogen Fixation:**

| Type | Examples |
|---|---|
| **Biological** | Bacteria in legume root nodules (*Rhizobium*), free-living bacteria |
| **Environmental (Atmospheric)** | **Lightning, forest fires, hot lava flows** (high-energy events break N₂ triple bond) |
| **Anthropogenic** | Burning fossil fuels, synthetic N fertilizers, cultivation of legumes |

**Nitrogen: Essential for life** — component of DNA, RNA, and proteins.

**Human Impact of excess nitrogen:**
- In drinking water: excess NO₃⁻ → cancer risk, infant respiratory distress
- In surface water: nutrient over-enrichment → fish-kills, **harmful algal blooms**, species shifts
- In atmosphere: smog (NO), greenhouse gas (**N₂O**), acid rain (nitrogen oxides)
- N₂O GWP = **265–298× that of CO₂** over 100-year timescale; atmospheric lifetime = 110 years
- N₂O also depletes ozone.

---

#### Phosphorus Cycle
- Unlike other cycles, the **atmosphere plays no significant role** (phosphorus compounds are solids at typical Earth temperatures/pressures).
- Movement: lithosphere → hydrosphere → biosphere and back.
- Key concern: phosphate fertilizer overuse → runoff → eutrophication.

---

#### Sulfur Cycle
- Sulfur released as rocks erode; plants assimilate it.
- H₂S released by decomposers and during volcanic eruptions.
- **99% of sulfur in the atmosphere is due to human activity** (industrial SO₂ emissions).
- SO₂ + H₂O → **H₂SO₄** → **Acid Rain**.

---

#### Eutrophication
Triggered by **N & P** enrichment:

N & P excess → phytoplankton increase → **Algal Bloom** → Algae die → **Bacterial decomposition (consumes O₂)** → **O₂ depletion** → Loss of food, habitat, oxygen production

**7 Measures to Reduce Eutrophication:**
1. Reduce phosphates in detergents
2. Reduce nitrate-containing fertilizers
3. Use tertiary sewage treatment to remove phosphate and nitrate
4. Direct wastewater away from lakes to treatment sites
5. Aerate lakes/reservoirs to prevent O₂ depletion during algal blooms
6. Remove phosphate-rich plant material from affected lakes
7. Remove phosphate-rich sediments by dredging

---

#### Phytoremediation — Constructed Wetland
A constructed wetland uses natural processes (sedimentation, precipitation, adsorption) to remove pollutants from water. Key mechanisms: S = Sedimentation; P = Precipitation; A = Adsorption.

---

## PART B — ASSIGNMENT QUESTIONS & SOLUTIONS

---

### Q1. BOD vs COD Definition (True/False)
**Q:** "The amount of chemical oxidant, expressed in oxygen equivalent, required to completely oxidize a source of organic matter is expressed as biochemical oxygen demand." True or False?
**Options:** a. True | b. False
**✅ Answer: (b) False**

> **Key distinction from slides:**
> - **BOD:** oxygen utilized by **microorganisms** (biological oxidation)
> - **COD:** amount of **chemical oxidant** (expressed as O₂ equivalent) to **completely oxidize** organic matter
>
> The statement perfectly matches the slide definition of **COD**, not BOD. BOD is slower (biological), while COD is faster (chemical, complete). Neither CBOD, NBOD, ThOD, BOD₅, nor BODᵤ involves a chemical oxidant — all are biologically based.

---

### Q2. NOT a Product of Aerobic Decomposition
**Q:** Which is NOT the outcome of aerobic decomposition?
**Options:** a. CO₂ | **b. CH₄** | c. NO₃ | d. PO₄
**✅ Answer: (b) CH₄ (Methane)**

> **Aerobic products (stable):** CO₂ ✓, H₂O ✓, NO₃⁻ ✓, PO₄³⁻ ✓, SO₄²⁻ ✓
>
> **Anaerobic products (unstable):** H₂S, NH₃, **CH₄** — CH₄ is the final product of **methanogenesis** (Stage 4 of anaerobic digestion). Aerobic products are "stable" because they are fully oxidized end states.

---

### Q3. Theoretical Oxygen Demand of Glucose
**Q:** Compute ThOD of water containing glucose (C₆H₁₂O₆) in mg O₂/mg glucose.
**Options:** **a. 1.07** | b. 2.07 | c. 0.94 | d. 1.5
**✅ Answer: (a) 1.07**

**Step 1:** Write the reaction: C₆H₁₂O₆ + O₂ → CO₂ + H₂O
**Step 2:** Balance: C₆H₁₂O₆ + **6O₂** → 6CO₂ + 6H₂O
**Step 3:** Apply stoichiometry:

$$\text{MW glucose} = 6(12) + 12(1) + 6(16) = 180 \text{ g/mol}$$
$$\text{MW } 6O_2 = 6 \times 32 = 192 \text{ g/mol}$$
$$\text{ThOD} = \frac{192}{180} = \mathbf{1.07 \text{ mg O}_2/\text{mg glucose}}$$

> ⚠️ Common error: option (c) 0.94 = 180/192 (inverted ratio). Always divide O₂ mass by compound mass.

---

### Q4. BOD Discharge Limit in Surface Water
**Q:** What is the discharge limit of BOD (mg/L) in surface water?
**Options:** a. 10 | b. 20 | c. 50 | **d. 30 mg/L**
**✅ Answer: (d) 30 mg/L**

> **Direct slide quote (Lecture 22):** *"Discharge limit of BOD and COD in surface water is 30 mg/L and 250 mg/L respectively."*
>
> This is the regulatory cap on effluent entering surface water. Note the difference from drinking water quality standards (BOD < 2 mg/L). The Ganga River CPCB data shows most sites have BOD 3–8 mg/L, already above drinking water threshold but below the 30 mg/L discharge limit.

---

### Q5. Fecal Contamination Indicator
**Q:** Which is generally used as a fecal contamination indicator?
**Options:** **a. E. coli** | b. Amoebiasis | c. Round worm | d. Rotavirus
**✅ Answer: (a) E. coli**

> From Lecture 23 slides: Faeces of a healthy person contains **>10¹⁰ bacteria/g**. E. coli is used as a fecal indicator because of its abundance in faeces and because its presence signals potential co-presence of all other waterborne pathogens.
>
> - (b) Amoebiasis is a **disease** (caused by *Entamoeba histolytica*), not an indicator organism
> - (c) Round worm → Helminthic disease
> - (d) Rotavirus → Viral diarrhoea, not used as an indicator

---

### Q6. Biggest Sink of Carbon Dioxide
**Q:** Which is the biggest sink of CO₂?
**Options:** a. Plants | **b. Ocean** | c. Soil | d. Rocks
**✅ Answer: (b) Ocean**

> **From Lecture 25 slide — Carbon Sinks:**
> - Lithosphere (limestone) = largest **reservoir** overall
> - **Hydrosphere (ocean)** = 2nd largest reservoir, but **largest active sink** (absorbs anthropogenic CO₂)
> - Biosphere (plants) = active but smaller capacity
>
> Rocks/limestone store carbon over **geological timescales** — they don't actively absorb current CO₂ emissions. The ocean absorbs ~25–30% of annual anthropogenic CO₂.

---

### Q7. BOD of Sewage Sample
**Q:** 2% solution incubated 5 days at 20°C. DO depletion = 4 ppm. Find BOD.
**Options:** **a. 200 mg/L** | b. 250 | c. 300 | d. 150 mg/L
**✅ Answer: (a) 200 mg/L**

$$BOD_5 = \frac{DO_i - DO_f}{P} = \frac{4}{0.02} = \mathbf{200 \text{ mg/L}}$$

> This exact problem appears as a **homework problem** in the Lecture 22 slides. P = 0.02 (2% = 0.02 dilution fraction).
>
> Compare with slide example: 2.5 mL in 250 mL (ratio = 100), DO loss = 3 mg/L → BOD = 300 mg/L. Same method, different numbers.

---

### Q8. Environmental Events that Fix Nitrogen
**Q:** Which environmental event fixes nitrogen present in air?
**Options:** a. Lightning | b. Forest fires | c. Animals | **d. Both a and b**
**✅ Answer: (d) Both a and b — Lightning AND Forest fires**

> **Direct from Lecture 25 slide — "Nitrogen Fixation (ENVIRONMENTAL)":**
> *"High-energy natural events which break the bond N₂. Examples: **lightning, forest fires, hot lava flows**"*
>
> - Lightning and forest fires both provide the energy to break N₂'s **triple bond**.
> - Animals (c) **cannot** fix nitrogen — they obtain nitrogen through diet (organic N from food).
> - Both abiotic fixation methods produce nitrogen oxides, which rain down to earth as bioavailable forms.

---

### Q9. Minimum Detectable BOD₅
**Q:** 10 mL wastewater + dilution water = 300 mL total. Desired ≥1.5 mg/L DO drop. Minimum detectable BOD₅?
**Options:** **a. 45 mg/L** | b. 24 | c. 30 | d. 12 mg/L
**✅ Answer: (a) 45 mg/L**

$$P = \frac{10}{300}; \quad \text{Min BOD}_5 = \frac{\text{Min }\Delta DO}{P} = \frac{1.5}{10/300} = 1.5 \times 30 = \mathbf{45 \text{ mg/L}}$$

> The **slides work a near-identical example** (same 10 mL/300 mL setup, but require 2.0 mg/L drop):
> - Minimum BOD₅ = 2.0 / (10/300) = 60 mg/L
> - Maximum BOD₅ = (9.0 − 2.0) / (10/300) = 210 mg/L → acceptable range: 60–210 mg/L
>
> This question uses 1.5 mg/L minimum drop instead of 2.0, giving 45 mg/L.

---

### Q10. Eutrophication
**Q:** Excessive algal growth when water is overly enriched with minerals and nutrients is called _____.
**Options:** **a. Eutrophication** | b. Biodegradation | c. Pollution | d. None
**✅ Answer: (a) Eutrophication**

> **Full mechanism from Lecture 25 slide:**
> N & P excess → phytoplankton increase → **Algal bloom** → Algae die → Bacterial decay (uses O₂) → O₂ depletion → Loss of food, habitat & oxygen production.
>
> **7 measures to reduce eutrophication** listed in slides (see Part A above).

---

### Q11. Nitrogen Assimilation (True/False)
**Q:** "Nitrogen assimilation is the process of formation of organic nitrogen compounds from inorganic nitrogen compounds." True or False?
**Options:** a. True | b. False
**✅ Answer: (a) True**

> **From Lecture 25 — Nitrogen Cycle steps:**
> N Fixation → Ammonification → Nitrification → **Assimilation** → Denitrification
>
> During assimilation, plants/animals take up inorganic forms (NO₃⁻, NH₄⁺) and convert them into **organic nitrogen** (amino acids, proteins, DNA, RNA). Nitrogen is "an essential component of DNA, RNA, and proteins." The reverse process is **ammonification** (decomposers convert organic N back to NH₄⁺).

---

### Q12. COD Digestion Temperature
**Q:** What is the digestion temperature of COD?
**Options:** a. 100°C | **b. 150°C** | c. 100°C | d. 110°C
**✅ Answer: (b) 150°C**

> **Direct from Lecture 22 slide — COD procedure:**
> Step 3: *"Tightly close the tubes kept in COD digestor at **150°C for 2 hours**"*
>
> The oxidant K₂Cr₂O₇ in concentrated H₂SO₄ at 150°C ensures **complete** chemical oxidation of all oxidizable organic matter. This is why COD ≥ BOD — it oxidizes both biodegradable and non-biodegradable organic fractions.

---

### Q13. End Products of Acetogenesis
**Q:** End products of acetogenesis in anaerobic digestion?
**Options:** a. Hydrolysed products | **b. Acetic acid** | c. Acidic compounds | d. Glucose
**✅ Answer: (b) Acetic acid**

> **Direct from Lecture 24 anaerobic digestion pathway:**
> Stage 3 (Acetogenesis) → **Acetic acid (CH₃COOH), H₂, CO₂**
>
> - (a) Hydrolysed products = **Stage 1** (Hydrolysis) outputs
> - (c) Acidic compounds = **Stage 2** (Acidogenesis) outputs — volatile fatty acids, alcohols
> - (d) Glucose = a hydrolysis product from Stage 1
>
> Acetic acid from Stage 3 is then consumed in **Stage 4 (Methanogenesis)** to produce CH₄ + CO₂.

---

### Q14. Basic Requirements for a Healthy Environment
**Q:** What are basic requirements for a healthy environment?
**Options:** a. Clean air | b. Polluted air | c. Safe and adequate food | **d. Both a and c**
**✅ Answer: (d) Both a and c**

> **Direct from Lecture 23 slide:**
> *"What are the Basic requirements for a healthy environment?"*
> - **Clean air, water and soil**
> - **Safe and adequate food**
> - **Stable global peaceful environment**
>
> (b) Polluted air is itself a target area requiring "air quality management" under environmental health.

---

### Q15. Typhoid Causative Organism
**Q:** Typhoid is caused by which microorganism?
**Options:** a. Viral | b. Protozoa | c. Fungi | **d. Bacteria**
**✅ Answer: (d) Bacteria**

> **From Lecture 23 — Waterborne Disease Classification slide:**
> - **Bacterial:** *Typhoid & Paratyphoid fever*, Bacillary dysentery, Cholera, *E. coli* diarrhoea
> - Caused specifically by *Salmonella Typhi*
>
> - (a) Viral → Hepatitis A/E, Rotavirus
> - (b) Protozoa → Amoebiasis (*Entamoeba histolytica*), Giardiasis
> - (c) Fungi → Not listed in the slides' waterborne disease classification

---

## PART C — KEY FORMULAS QUICK REFERENCE

| Formula | Description |
|---|---|
| $BOD_5 = (DO_i - DO_f) / P$ | BOD from dilution test |
| $P = V_{sample} / V_{total}$ | Dilution factor |
| $\text{ThOD} = \frac{MW_{O_2 \text{ required}}}{MW_{\text{compound}}}$ | Theoretical oxygen demand ratio |
| $C_6H_{12}O_6 + 6O_2 \rightarrow 6CO_2 + 6H_2O$ | Glucose oxidation |
| $NH_3 + 2O_2 \rightarrow NO_3^- + H^+ + H_2O$ | Nitrification (NBOD) |
| BOD discharge limit | 30 mg/L |
| COD discharge limit | 250 mg/L |
| COD test temperature | 150°C for 2 hours |
| COD oxidant | K₂Cr₂O₇ (Potassium dichromate) |

---

## PART D — ANAEROBIC DIGESTION PATHWAY SUMMARY

```
Organic matter (manure, food waste, crops)
        ↓ HYDROLYSIS
Soluble monomers (sugars, amino acids, fatty acids)
        ↓ ACIDOGENESIS
Alcohols, carbonic acids, volatile fatty acids
        ↓ ACETOGENESIS
Acetic acid (CH₃COOH) + H₂ + CO₂
        ↓ METHANOGENESIS
CH₄ + CO₂ (BIOGAS)
```

Applications: Power generation, cooking gas, vehicle fuel, fertilizer (digestate)

---

*Source: NPTEL Lectures 21–25 (Week 5) — Dr. Brajesh Kumar Dubey, IIT Kharagpur*
