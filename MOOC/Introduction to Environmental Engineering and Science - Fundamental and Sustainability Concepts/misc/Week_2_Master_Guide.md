# Week 2 Master Guide.md

## 🚨 THE FINAL EXAM TRAP LIST (Review Before Exam)
* **The Temperature Trap:** **Molarity** depends on temperature (because liquid volume expands). **Molality** does *not* (because mass is constant). Also, when using the Ideal Gas Law ($PV=nRT$), $T$ MUST be in **Kelvin**, not Celsius. 
* **The Solids Sample Volume Trap:** If a question asks for TDS in mg/L and gives you TS = 250 mg/L, TSS = 190 mg/L, and a sample volume of "50 mL," **ignore the 50 mL!** It is a deliberate distractor. Just subtract: $250 - 190 = 60~mg/L$.
* **The "N as N" Trap:** Reporting nitrogen species as "mg N/L" allows scientists to directly sum different forms (Ammonia, Nitrite, Nitrate) on a common mass basis to find Total Nitrogen, completely bypassing individual molecular weight conversions.
* **The Atmospheric Abundance Trap:** **Nitrogen ($N_2$)** and **Oxygen ($O_2$)** are the most abundant gases in the atmosphere, but they are **NOT** greenhouse gases.

### 🧠 EVERY Week 2 Concept (Explained Simply + Deep Facts)

#### Part 1: Concentrations & Chemical Units

* **1. Molarity vs. Molality:** 
    * **Molarity (M):** Moles of solute per *Liter of solution*. Because liquid volume expands/contracts with heat, Molarity is **temperature-dependent**.
    * **Molality (m):** Moles of solute per *kg of solvent*. Because mass never changes with heat, Molality is **temperature-independent**.
* **2. Equivalent Weight & Normality (Formula Sheet Check):**
    * **Equivalent Weight:** The weight of a molecule divided by its "valency" or "n-factor" (how many hydrogen ions it can replace).
        * *Formula:* `Eq. Wt. = MW / n`
        * *Examples:* $H_2SO_4$ (MW=98, n=2) $\rightarrow$ 49 g/eqv. $Na_2CO_3$ (MW=106, n=2) $\rightarrow$ 53 g/eqv. HCl (MW=36.5, n=1) $\rightarrow$ 36.5 g/eqv.
    * **Normality (N):** Equivalents of solute per Liter of solution. 
        * *Formula:* `N = M × n`
        * *Example:* 1M of $H_2SO_4$ = 2N.
        * *Note:* Normality depends on both **Dilution** and **Temperature**.
* **3. The "Parts Per" Rules (ppm & ppb):**
    * **In Water (Aqueous):** $1\text{ ppm} \approx 1\text{ mg/L}$. (Valid for dilute aqueous systems where density is ~1,000 g/L).
    * **In Soil/Solids:** $1\text{ ppm} = 1\text{ mg/kg}$ (mass/mass).
    * **In Air (Gases):** $ppm_v$ is a **volume/volume** ratio.
* **4. Unit Classifications (Slide Concepts):**
    * **Fundamental Units:** Mass, length, time.
    * **Basic Units:** Fundamental units PLUS temperature, electrical current, luminous intensity, etc.
    * **Derived Units:** Area, volume, velocity (combinations of basic/fundamental).
* **5. Mass-Basis PPM Formula:** $ppm = \frac{m_i}{m_{total}} \times 10^6$. (Often tested as a conceptual or numerical question).

#### Part 2: Air, Gases & The Atmosphere
* **5. The Ideal Gas Law:** Used to convert gas concentrations between $ppm_v$ and mass-based units ($\mu g/m^3$). 
    * *Formula:* $PV = nRT$. (Temperature must be in **Kelvin**, not Celsius).
* **6. Dalton's Law of Partial Pressures:** The pressure a specific gas exerts is directly proportional to its **mole fraction** (or volume fraction) in the mixture. 
    * *Formula:* $P_i = y_i \times P_{total}$.
* **7. Atmospheric Gas Concentrations (Must-Know Trivia):**
    * **Nitrogen ($N_2$):** 780,840 ppmv (78.08%). *Most abundant, NOT a greenhouse gas.*
    * **Oxygen ($O_2$):** 209,460 ppmv (20.9%). *NOT a greenhouse gas.*
    * **Argon ($Ar$):** 9,340 ppmv (0.934%).
    * **Carbon Dioxide ($CO_2$):** 400 ppmv (0.04%). *Greenhouse gas.*
    * **Methane ($CH_4$):** 1.79 ppmv (or 1,790 ppbv). *Lowest partial pressure of this group; greenhouse gas.*
* **Ion Balance Error Acceptability:** Water must be electrically neutral. The analysis is checked via the formula: $E\% = \frac{\sum Cations - \sum Anions}{\sum Cations + \sum Anions} \times 100$. If the error is **$< 5\%$**, the analysis is chemically acceptable.

#### Part 3: The Solids Family Tree & Water Chemistry
* **8. The Solids Breakdown:**
    * **TS (Total Solids):** Everything left after evaporating an unfiltered sample at 103°C. ($TS = TSS + TDS$).
    * **TSS (Total Suspended Solids):** The physical chunks caught on a filter, dried at 103°C. (Causes turbidity).
    * **TDS (Total Dissolved Solids):** The invisible dissolved stuff (like salt) that passes through the filter, dried at 103°C. *(Note: High turbidity does NOT mean high TDS).*
* **9. Volatile vs. Fixed Solids (The 550°C Fire Test):**
    * **VSS (Volatile Suspended Solids):** The fraction of TSS that burns off in a muffle furnace at 550°C. Represents **organic matter** (living/dead biomass).
    * **FSS (Fixed Suspended Solids):** The ash/mineral fraction that remains after 550°C. Represents **inorganic** material.
* **10. Hardness vs. Alkalinity:**
    * **Alkalinity Ions:** Anions (negative) like Bicarbonate ($HCO_3^-$) and Carbonate ($CO_3^{2-}$). 
    * **Hardness Ions:** Cations (positive) like Calcium ($Ca^{2+}$) and Magnesium ($Mg^{2+}$).
* **11. Ion Balance Error:** Water must be electrically neutral. The acceptability is checked by: $E\% = \frac{\sum Cations - \sum Anions}{\sum Cations + \sum Anions} \times 100$. (Must be < 5% to be acceptable).

#### Part 4: Instruments, Statistics & Slide Secrets
* **12. Environmental Lab Instruments:**
    * **High Volume Sampler:** Sucks in huge amounts of air through a filter to measure **Particulate Matter** in the atmosphere.
    * **Chromatographs (GC / HPLC):** Sorts and separates complex gas or liquid mixtures into individual chemical components.
    * **Spectrometers (ICP / AAS):** Used to detect heavy metals and cations (like lead or arsenic) in water.
* **13. Statistical Data Handling (Audit Additions):**
    * **MDL (Method Detection Limit):** The minimum concentration a machine can measure with **99% confidence**.
    * **BDL (Below Detection Limit):** Statistically handled by assuming the value is zero, the MDL, or **1/2 the MDL**.
    * **Log-Normal Distribution:** Environmental data usually has a long tail (log-normal). We use the **Geometric Mean** as the measure of central tendency.
    * **UCL (Upper Confidence Limit):** A conservative estimate of the mean that takes into account uncertainties in the data set (e.g., 95% UCL).
* **14. Wet vs. Dry Weight:** To find the dry concentration of a pollutant, divide the wet concentration by the dry fraction (e.g., $0.6\text{ mg/kg wet} / 0.2\text{ dry fraction} = 3.0\text{ mg/kg dry}$).

***

### 📝 The Ultimate Week 2 Q&A Bank (Core + Spin-offs + Slides)

**Units, Molarity, & Chemistry**
* **Q:** The unit $\mu g/m^3$ is most appropriately used for reporting pollutant concentrations in: **A:** Air.
* **Q:** Among the following units which isn't a fundamental unit? **A:** Temperature (It is considered a 'Basic' unit, whereas Mass/Length/Time are 'Fundamental').
* **Q:** Molarity differs from molality because molarity depends on: **A:** Temperature and volume.
* **Q: Relationship between Molarity (M) and Normality (N):** `[Slides]`
    * **A:** $N = M \times n$ (where $n$ is the valency or n-factor).
* **Q: Calculate the Normality (N) of 0.05 M $H_2SO_4$.** `[Slides]`
    * **A:** 0.1 N. *(Calculation: $0.05 \text{ M} \times 2 = 0.1 \text{ N}$)*.
* **Q: Why is Molality (m) preferred over Molarity (M) for precision?** `[Slides]`
    * **A:** Molality is temperature-independent (mass doesn't change with heat), whereas Molarity changes as liquid volume expands/contracts.
* **Q:** Why is Molality temperature-independent while Molarity is not? **A:** Molality divides by the *mass* of the solvent (constant), while Molarity divides by the *volume* of the solution (expands/contracts with temperature).
* **Q:** Which statement about ppm is correct? **A:** 1 mg of solute in 1 kg of solvent = 1 ppm.
* **Q:** When is the approximation $1\text{ mg/L} \approx 1\text{ ppm}$ valid? **A:** In most dilute *aqueous* (water) systems (density ~1,000 g/L).
* **Q:** How is ppm expressed in the air? **A:** $ppm_v$ = volume/volume ratio (not mass/mass).
* **Q:** What is the equivalent weight of H₂SO₄? **A:** 49 g/eqv.
* **Q:** What is the normality (N) of 1 M Solutions of H₂SO₄? **A:** 2N.
* **Q:** What is the equivalent weight of Na₂CO₃? **A:** 53.
* **Q:** What is the normality of a 1M solution of HCl? **A:** 1 N.
* **Q:** What is the molarity of 50 grams of calcium carbonate ($CaCO_3$)? **A:** 0.5 mol/L.
* **Q:** Calculate the molality of 30.0 g of NaCl dissolved in 500.0 mL of water. **A:** 1.03 m.
* **Q:** Convert 5 ppm of TCE (MW = 131.5) in water to Molarity. **A:** $3.8 \times 10^{-5}$ M.
* **Q:** What are the two factors that Normality depends on? **A:** Dilution and Temperature.
* **Q:** Reporting nitrogen as mg N/L instead of mg/L of individual species is useful because it: **A:** Accounts for all nitrogen forms on a common basis.
* **Q:** A mineral water analysis gives total cations = $1.0 \times 10^{-3}$ eqv/L and total anions = $0.95 \times 10^{-3}$ eqv/L. Is the analysis acceptable? **A:** Yes (Ion Balance Error is ~2.56%, which is < 5%).
* **Q: What is the equivalent weight of Sodium Hydroxide (NaOH)?** `[v2 Guide Spin-off]`
    * **A: 40 g/eqv.**
    * > **Calculation:** $MW = 40$. Since it has one $OH^-$ group, $n=1$. $Eq. Wt. = 40/1 = 40$.
* **Q: Calculate the Ionic Strength (I) of 0.01 M $CaCl_2$.** `[Slides]`
    * **A:** 0.03.
    * > **Calculation:** $I = 0.5 \sum (c_i z_i^2)$. 
    * > $Ca^{2+}: 0.01 \times (2^2) = 0.04$. 
    * > $Cl^-: 0.02 \times (1^2) = 0.02$. 
    * > $I = 0.5 \times (0.04 + 0.02) = 0.03$.
* **Q: In the Ion Balance Error formula, what units must be used for the summation of Cations and Anions?** `[Slide Veto]`
    * **A: meq/L (milliequivalents per liter).**
    * > **Note:** You cannot use mg/L directly; you must convert concentrations to equivalents first.
* **Q:** The unit $\mu g/m^3$ is most appropriately used for reporting pollutant concentrations in:
    * **A:** Air. *(Mass per volume units are standard for compressible gases).*
* **Q:** When converting gaseous concentrations between $ppm_v$ and $\mu g/m^3$, which law is fundamentally required?
    * **A:** Ideal gas law.
* **Q:** In a gas mixture, the partial pressure of a component gas is proportional to its:
    * **A:** Mole (or volume) fraction.
* **Q:** A mineral water analysis gives total cations = $1.0 \times 10^{-3}$ eqv/L and total anions = $0.95 \times 10^{-3}$ eqv/L. Is the analysis acceptable?
    * **A:** Yes. *(The Ion Balance Error is approx 2.56%, which is below the 5% threshold).*

**Gases, Pressures & Atmosphere**
* **Q: Nitrogen ($N_2$) is the most abundant gas in the atmosphere. According to the slides, what is its primary role regarding atmospheric pressure?** `[Slide Veto]`
    * **A: It acts as a "diluent" for oxygen and provides the bulk of the atmospheric pressure.**
* **Q:** What is partial pressure? **A:** The pressure one of the gases in a mixture would exert if it alone occupied the whole container.
* **Q:** In a gas mixture, the partial pressure of a component gas is proportional to its: **A:** Mole (or volume) fraction.
* **Q:** What is the partial pressure of CO₂ if its concentration is 420 ppmv and atmospheric pressure is 1 atm? **A:** $4.2 \times 10^{-4}$ atm.
* **Q:** What is the formula to calculate parts per million by volume (ppmv) from partial pressure? **A:** $ppm_v = (P_i / P_{total}) \times 10^6$.
* **Q:** When converting gaseous concentrations between ppmv and $\mu g/m^3$, which law is fundamentally required? **A:** Ideal gas law.
* **Q:** The ideal gas law uses T in degrees Celsius. **A:** False (It uses absolute temperature in Kelvin).
* **Q:** Which of the following is not a greenhouse gas? **A:** Oxygen (or Nitrogen).
* **Q:** Which gas exerts the lowest partial pressure in the atmosphere out of O₂, N₂, Ar, and CH₄? **A:** Methane (CH₄).

**Water Solids & Ions**
* **Q: Alkalinity in water is primarily caused by which three ions?** `[Slides]`
    * **A:** Bicarbonates ($HCO_3^-$), Carbonates ($CO_3^{2-}$), and Hydroxides ($OH^-$).
* **Q:** Total solids of a water sample are composed of total suspended solids and total dissolved solids. **A:** True.
* **Q:** TDS Calculation: TS = 250, TSS = 190, FSS = 60, VS = 130 mg/L. Find TDS. **A:** 60 mg/L.
* **Q:** How is TDS actually measured in the lab? **A:** Place the *filtrate* (water that passed through the filter) in a crucible and dry it at 103°C for 24 hours.
* **Q: In solids analysis, what is the relationship between TSS, VSS, and FSS?** `[Slides]`
    * **A:** $TSS = VSS + FSS$. (Total Suspended Solids = Volatile + Fixed).
* **Q:** Why does a highly turbid water sample not necessarily indicate high TDS? **A:** Turbidity is caused by *suspended* particles (TSS). Dissolved solids pass right through filters and do not cause cloudiness.
* **Q:** Volatile suspended solids (VSS) are primarily an indicator of: **A:** Organic matter content.
* **Q:** What is the difference between FSS and VSS? **A:** FSS is the inorganic mineral fraction left after 550°C ignition. VSS is the organic fraction that burns off.
* **Q:** Which ions are responsible for Alkalinity in water? **A:** $CO_3^{2-}$ (Carbonate) and $HCO_3^-$ (Bicarbonate).
* **Q: Which instrument is used to measure the "True Color" of a water sample after filtration?** `[2023 Assignment]`
    * **A: Spectrophotometer (at 455 nm).**

**Instruments & Statistics**
* **Q: When environmental data are log-normally distributed, which measure of central tendency is used?** `[Slides]`
    * **A:** Geometric mean
* **Q:** Particulate matter present in atmosphere is measured by which instrument? **A:** High volume sampler.
* **Q:** Which instrument separates complex gas or liquid samples into single components? **A:** Gas Chromatograph (GC) or HPLC.
* **Q:** Which instrument analyzes heavy metals and cations? **A:** Inductively Coupled Plasma (ICP) or Atomic Absorption Spectrometer (AAS).
* **Q:** The Method Detection Limit (MDL) represents: **A:** The minimum concentration measurable with 99% confidence.
* **Q:** If you have sample results Below the Detection Limit (BDL), what are the options for handling them statistically? **A:** Assume them to be zero, assume them to be the detection limit, or assume them to be 1/2 the detection limit.
* **Q:** When environmental data are log-normally distributed, the most appropriate measure of central tendency is the: **A:** Geometric mean.
* **Q:** What does the Upper Confidence Limit (UCL) represent in environmental data? **A:** A conservative estimate of the mean that takes into account uncertainties in the data set.

## 🚀 ACTIVE RECALL & FEYNMAN CHALLENGE
*Cover the answers below and test yourself before the exam.*

**Quiz 1:** What is the difference between $1M~HCl$ and $1M~H_2SO_4$ in terms of Normality?
> **Answer:** Because $HCl$ only has one hydrogen ion ($n=1$), $1M = 1N$. Because $H_2SO_4$ has two replaceable hydrogen ions ($n=2$), its normality is doubled, meaning $1M = 2N$.

**Quiz 2:** You have a water sample that is highly turbid (cloudy). Does this automatically mean it has a high Total Dissolved Solids (TDS) concentration?
> **Answer:** No. Turbidity is caused by Total *Suspended* Solids (TSS). Dissolved solids pass through the filter and are invisible, so they do not directly cause turbidity.

**Feynman Challenge:** Explain the difference between **Molarity** and **Molality** to a 10-year-old, and tell them why a scientist in a hot desert might prefer to use Molality.
> **Example Answer:** Imagine making a glass of lemonade. Molarity is measuring how much lemon powder is in the *whole glass* of liquid. Molality is measuring how much lemon powder you mixed with an exact *weight* of plain water. If you go to a hot desert, the liquid lemonade expands and takes up more space in the glass, so the Molarity changes. But the *weight* of the water never changes no matter how hot it gets, so Molality stays exactly the same!