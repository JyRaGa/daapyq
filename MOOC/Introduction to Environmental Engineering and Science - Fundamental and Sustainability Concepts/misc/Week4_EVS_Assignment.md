# Week 4: Mass Balances, Reactors & Transport Processes
**Course:** Introduction to Environmental Engineering and Science – Fundamentals and Sustainability Concepts
**Institute:** IIT Kharagpur (NPTEL) | **Lectures:** 16–19

---

## PART A — SLIDE CONTENT (Lecture-wise)

---

### Lecture 16: Mass Balances & Batch Reactor (CMBR)

#### Law of Conservation of Mass
"Mass can neither be produced nor destroyed."

Mass at time (t + Δt) = Mass at time t
+ (mass entering from t to t + Δt)
− (mass exiting from t to t + Δt)
+ (net mass of chemical produced by reactions between t and t + Δt)

#### Mass Flux & Accumulation Rate
**Mass flux** = the rate at which mass enters and leaves the system.

Dividing the conservation equation by Δt and taking the limit as Δt → 0:

$$\boxed{\frac{dm}{dt} = \dot{m}_{in} - \dot{m}_{out} + \dot{m}_{reaction}}$$

- $\dot{m}$ = mass flux (units: mass/time)
- $\dot{m}_{reaction}$ = net rate of chemical production (positive = produced, negative = consumed)
- If accumulation = 0 → **steady state**

#### Control Volume
A **control volume** is a specific region of space with defined boundaries across which $\dot{m}_{in}$ and $\dot{m}_{out}$ are calculated.
- Theoretically, a volume of **any shape and location** can be used as a control volume.
- Its most important attribute: it has boundaries over which mass fluxes can be calculated.
- Examples: a reactor, a lake, a river reach, an atmospheric cell.

---

#### Reactor Design Overview

| Mode of Operation | Reactor Kinetics |
|---|---|
| 1. Batch reactor / Completely Mixed Batch Reactor (CMBR) | Reaction order zero |
| 2. Continuous reactor / Continuous Stirred Tank Reactor (CSTR) | First order reaction |
| 3. Plug Flow Reactor (PFR) | Second order reaction |

---

#### Completely Mixed Batch Reactor (CMBR)
- The simplest reactor type.
- **No flow** enters or leaves during reaction.
- Contents are mixed **completely and uniformly** (stir bar symbol indicates complete mixing).
- Used in: cell cultivation, polymer synthesis, crystallization, laboratory kinetic studies.

**Fundamental mass balance in CMBR** (no in/out):

$$\dot{m}_{in} - \dot{m}_{out} = 0 \quad \Rightarrow \quad \frac{dm}{dt}_{net} = \frac{dm}{dt}_{reaction}$$

##### CMBR — Zero Order Reaction

$$\frac{dm}{dt}_{net} = -k$$
$$\int_{C_0}^{C_e} dc = \int_{0}^{t} -k \, dt$$
$$\boxed{C_e = C_0 - kt}$$

##### CMBR — First Order Reaction

$$\frac{dm}{dt}_{net} = -kC$$
$$\int_{C_0}^{C_e} \frac{dc}{C} = \int_{0}^{t} -k \, dt$$
$$\ln(C_e/C_0) = -kt$$
$$\boxed{C_e = C_0 \, e^{-kt}}$$

##### CMBR — Second Order Reaction

$$\frac{dm}{dt}_{net} = -kC^2$$
$$\int_{C_0}^{C_e} \frac{dc}{C^2} = \int_{0}^{t} -k \, dt$$
$$\boxed{\frac{1}{C_e} = \frac{1}{C_0} + kt}$$

---

### Lecture 17: Mass Balance in CSTR and PFR

#### Continuous Stirred Tank Reactor (CSTR)
- Stir bar indicates the reactor is **completely mixed**.
- Fluid particles that enter are **instantaneously dispersed** throughout the reactor.
- At steady state: concentration inside reactor = concentration at outlet ($C_{out}$).

**CSTR Mass Balance (steady state, $dm/dt = 0$):**

$$0 = \dot{m}_{in} - \dot{m}_{out} + \dot{m}_{reaction}$$
$$\dot{m}_{in} = QC_0, \quad \dot{m}_{out} = QC_{out}$$

##### CSTR — Zero Order Reaction

$$0 = QC_0 - QC_{out} - kV$$
$$\boxed{C_{out} = C_0 - \frac{kV}{Q}}$$

##### CSTR — First Order Reaction

$$0 = QC_0 - QC_{out} - kC_{out}V$$
$$\boxed{C_{out} = \frac{C_0}{1 + k\theta}} \quad \text{where } \theta = V/Q \text{ (HRT)}$$

##### CSTR — Second Order Reaction

$$0 = QC_0 - QC_{out} - kC_{out}^2 V$$
Solve quadratic for $C_{out}$ (homework).

---

#### Hydraulic Retention Time (HRT)
$$\boxed{\theta = \frac{V}{Q}}$$
- $\theta$ = average time a fluid element spends in the reactor.
- Longer HRT → more treatment time → higher removal for given k.

---

#### CSTR Examples from Slides

**Example 1:** CMBR with first-order kinetics: k = 0.216/day, V = 500 m³, Q = 50 m³/day, $C_{in}$ = 100 mg/L.

$$C_{out} = C_{in} \times \frac{Q}{Q + kV} = 100 \times \frac{50}{50 + (0.216)(500)} = \mathbf{32 \text{ mg/L}}$$

**Example 2:** After $C_{in}$ is set to 0 (non-steady state):

$$\frac{C_t}{C_0} = e^{-(Q/V + k)t} = e^{-0.316t}$$

Time to reach 10% of initial: $t = \ln(10)/0.316 = \mathbf{7.3 \text{ days}}$

**Example 3:** Conservative pollutant, tank starts with clean water, $C_0 = 0$:

$$C = C_{in}\left(1 - e^{-(Q/V)t}\right) \quad \rightarrow \quad C \rightarrow C_{in} \text{ as } t \rightarrow \infty$$

---

#### Plug Flow Reactor (PFR)
- Length >> Width (tube/pipe shaped).
- Fluid flows as a **"plug"** — **no intermixing (backmixing)** between fluid elements.
- Concentration decreases from inlet to outlet along reactor length.

**PFR Mass Balance (first order, steady state) on elemental section dV:**

$$0 = QC - Q(C + dC) - kC \cdot dV$$
$$\int_{C_0}^{C_e} \frac{dC}{C} = \int_0^V -\frac{k}{Q} dV$$
$$\ln(C_e/C_0) = -k\theta = -\frac{kV}{Q}$$
$$\boxed{C_e = C_0 \, e^{-k\theta} = C_0 \, e^{-kV/Q}}$$

**PFR Example 5:** Same conditions as Example 1 (Q = 50 m³/day, k = 0.216/day, $C_{out}/C_{in}$ = 0.32):

$$V_{PFR} = -\ln(0.32) \times \frac{Q}{k} = 1.139 \times \frac{50}{0.216} \approx \mathbf{264 \text{ m}^3}$$

→ PFR requires only 264 m³ vs 500 m³ for CSTR for same removal efficiency. **PFR is more efficient.**

---

### Lecture 18: Energy Balance

#### First Law of Thermodynamics
$$\Delta U = Q - W$$
- $\Delta U$ = change in internal energy of system
- $Q$ = heat supplied to the system
- $W$ = work done by the system on surroundings

#### Common Forms of Energy

| Form | Formula |
|---|---|
| Heat / Internal energy | $\Delta E = \text{mass} \times c \times \Delta T$ |
| Gravitational potential energy | $\Delta E = \text{mass} \times g \times \Delta h$ |
| Kinetic energy | $KE = \frac{1}{2}mv^2$ |
| Electromagnetic (photon) | $E = h \times \nu$ (Planck's const × frequency) |

Heat capacity of water: c = 4,184 J/(kg·°C) = 4.184 kJ/(kg·°C)

#### Energy Balance Equation
$$\frac{dE}{dt} = E_{in} - E_{out}$$
- At steady state: $dE/dt = 0$

#### Energy Balance Examples

**Example 6 (Water Heater, steady state):**
- Heater: 5 kW, flow = 2 gal/min, $T_{in}$ = 10°C
- $T_{out} = T_{in} + 9.5°C = \mathbf{19.5°C}$ (cold shower!)

**Example 7 (Tank reheat, non-steady state):**
- Heat 40-gallon tank from 20°C to 54°C with 5 kW heater
- $\Delta t = \frac{m \times c \times \Delta T}{5000 \text{ J/s}} = \mathbf{4.3 \times 10^3 \text{ s} \approx 1.2 \text{ hours}}$

**Example 8 (Coal Power Plant cooling):**
- 1,430 MW waste heat removed by river (Q = 100 m³/s)
- $\Delta T = \frac{1.43 \times 10^9 \text{ W}}{(10^5 \text{ kg/s})(4184)} = \mathbf{3.4°C}$
- ⚠️ Temperature rise reduces dissolved oxygen in river → harmful to aquatic life.

---

### Lecture 19: Energy Balance of Earth, Transport Processes

#### Earth's Energy Balance & Greenhouse Gases

- **Without atmosphere:** Earth's surface would be **cooler than today** (~−18°C vs +15°C), unable to support life.
- **With atmosphere:** Greenhouse gases absorb and re-emit infrared radiation → natural greenhouse effect (+33°C warming).
- **Water vapour** is the most abundant and potent natural greenhouse gas.

**Greenhouse gases (GHGs):**
- Water vapour (H₂O) — most abundant (~50% of effect)
- Carbon dioxide (CO₂)
- Methane (CH₄)
- Nitrous oxide (N₂O)

GHGs warm the Earth similar to how blankets warm us at night.

#### Earth Overshoot Day
- The day humanity has used more ecological resources than Earth can regenerate in a year.
- 2019: **July 29** — earliest ever recorded.
- Humanity uses **1.75 Earths worth** of resources per year (as of 2019).
- The date has moved up by ~2 months over the past 20 years (1993: Oct 21 → 2019: Jul 29).
- Causes: deforestation, soil erosion, biodiversity loss, CO₂ buildup.

---

#### Mass Transport Processes

Three fundamental mechanisms of pollutant transport:

| Process | Mechanism | Formula |
|---|---|---|
| **Advection** | Transport by bulk fluid motion (flow velocity) | J = v × C |
| **Diffusion (Fickian)** | Random molecular motion (Brownian) from high → low concentration | J = −D (dC/dx) |
| **Dispersion** | Spreading due to velocity variations (mechanical mixing + turbulence) | Combined term |

**Combined transport:** J = Advection + Diffusion + Dispersion

---

#### Fick's Law of Diffusion

Derivation (from random molecular motion in a box):

$$J = -D \frac{dC}{dx}$$

- J = diffusive flux density (mass/area/time)
- D = diffusion coefficient (m²/s)
- dC/dx = concentration gradient
- Negative sign: flux moves from high → low concentration (down the gradient)

> *"The rate of diffusion across unit area is proportional to the concentration gradient."*

Fick's law is used to calculate the **dispersive-flux density** in pollutant transport models.

---

#### Turbulent Diffusion & Dispersion

- **Turbulent diffusion:** caused by **random fluctuations in advective velocity** (eddies, swirls in turbulent flow).
  - In turbulent flows: turbulent diffusivity >> molecular diffusivity.
- **Mechanical dispersion:** caused by velocity gradients (faster in center, slower at edges of flow).
- **Molecular diffusion:** caused by random thermal (Brownian) motion of molecules, independent of flow.
- **Dispersion:** broader term encompassing turbulent diffusion + mechanical mixing.

---

#### Reynolds Number

$$\boxed{Re = \frac{\text{inertia forces}}{\text{viscous forces}} = \frac{\rho \cdot V \cdot D}{\mu}}$$

- $\rho$ = fluid density (kg/m³)
- V = flow velocity (m/s)
- D = pipe/particle diameter (m)
- $\mu$ = dynamic viscosity (Pa·s or g/cm·s)

| Re Range | Flow Regime |
|---|---|
| Re < 2,000 | **Laminar** (smooth, sheet-like) |
| 2,000 – 4,000 | **Transitional** |
| Re > 4,000 | **Turbulent** (chaotic, eddy currents) |

A vortex street forms around cylinders for Re between ~40 and 1,000.

---

#### Gravitational Settling (Stokes' Law)

Forces acting on a settling particle:
- $F_g$ = gravitational force (downward) = $\rho_p \frac{\pi}{6} D_p^3 g$
- $F_B$ = buoyancy force (upward) = $\rho_f \frac{\pi}{6} D_p^3 g$
- $F_D$ = Stokes drag force (upward, for creeping flow Re < 1) = $3\pi\mu D_p v_r$

At **terminal settling velocity** ($dv/dt = 0$, $F_{down} = 0$):

$$(\rho_p - \rho_f)\frac{\pi}{6}D_p^3 g = 3\pi\mu D_p v_s$$

$$\boxed{v_s = \frac{g(\rho_p - \rho_f)}{18\mu} D_p^2}$$

- $v_s$ = settling velocity (m/s)
- $D_p$ = particle diameter (m)
- $\rho_p$ = particle density, $\rho_f$ = fluid density (kg/m³)
- $\mu$ = fluid dynamic viscosity

**Applications:** Primary settling basins, dust collection hoppers, air pollution control.

---

## PART B — ASSIGNMENT QUESTIONS & SOLUTIONS

---

### Q1. Mass Accumulation Rate
**Q:** Calculate the mass accumulation rate: 50 mg/L/s entering, 10 mg/L/s leaving.
**Options:** a. 20 | b. 30 | **c. 40** | d. 10 mg/L/s
**✅ Answer: (c) 40 mg/L/s**

**Core Formula:**
$$\text{Mass Accumulation Rate} = \dot{m}_{in} - \dot{m}_{out} + \dot{m}_{reaction}$$
Assuming no reaction:
$$= 50 - 10 = \mathbf{40 \text{ mg/L/s}}$$

**Why others are wrong:**
- (b) 30 = 50 − 20 (wrong subtraction)
- (a) 20 = 50 − 30 (wrong)
- (d) 10 = just the outflow value

> **Key concept:** If accumulation = 0 → steady state. This equation applies to CMBR, CSTR, and PFR alike.

---

### Q2. Gravitational Potential Energy Change
**Q:** Change in gravitational energy of 50 kg object, h changes from 10 m to 2.5 m; g = 9.81 m/s².
**Options:** a. 5200 J | b. 4500 J | **c. 3679 J** | d. 3500 J
**✅ Answer: (c) 3679 J**

**Formula:** $\Delta PE = m \times g \times \Delta h$

$$\Delta h = 10 - 2.5 = 7.5 \text{ m}$$
$$\Delta PE = 50 \times 9.81 \times 7.5 = \mathbf{3678.75 \approx 3679 \text{ J}}$$

**Why others are wrong:**
- (a) 5200 → uses wrong Δh ≈ 10.6 m
- (b) 4500 → uses g ≈ 10, Δh = 9 m
- (d) 3500 → uses g ≈ 9.33 (wrong)

> **Key rule:** Always use Δh = h₁ − h₂ (not the final height alone), and use standard g = 9.81 m/s².

---

### Q3. Control Volume
**Q:** What is control volume?
**Options:** a. Imaginary boundary to separate two systems | b. Reactor of 1L capacity | **c. Volume of any shape with boundaries** | d. None
**✅ Answer: (c)**

> **Definition:** A control volume is a specific region of space with boundaries across which $\dot{m}_{in}$ and $\dot{m}_{out}$ are calculated. It can be **any shape and location** — a reactor, lake, river reach, or atmospheric cell. The key attribute: defined boundaries for mass flux calculation.

**Why (a) is incomplete:** A control volume isn't just imaginary — it has defined flux boundaries with real physical meaning.

---

### Q4. Stirring in CMBR
**Q:** Purpose of stirring in a Completely Mixed Batch Reactor?
**Options:** a. Maintain heterogeneous mixture | **b. Maintain homogeneous mixing** | c. Indicate batch reactor | d. Indicate plug flow reactor
**✅ Answer: (b)**

> **Key concept:** The stirrer ensures **uniform (homogeneous) concentration** throughout — no concentration gradients exist anywhere in the CMBR. This is the defining assumption of complete mixing.

- (a) "Heterogeneous" is the exact opposite — stirring eliminates heterogeneity.
- (c), (d) — the stir bar symbol indicates **complete mixing**, not the reactor type.

---

### Q5. Time to Reduce to 1% in CMBR (First Order)
**Q:** Reduce pollutant A to 1% of C₀ in CMBR; A→B, rate = −kCₐ, k = 0.23 min⁻¹.
**Options:** **a. 20 min** | b. 30 min | c. 40 min | d. 50 min
**✅ Answer: (a) 20 min**

**Using first-order CMBR equation:**
$$C_e = C_0 \, e^{-kt}$$
$$0.01 = e^{-0.23t}$$
$$\ln(0.01) = -0.23t$$
$$-4.605 = -0.23t$$
$$t = \frac{4.605}{0.23} = \mathbf{20 \text{ min}}$$

**Verification:** At t = 20: $e^{-0.23 \times 20} = e^{-4.6} \approx 0.01$ ✓
- (b) 30 min → $C_e/C_0 = e^{-6.9} \approx 0.001$ (0.1%, not 1%)

---

### Q6. Highest Removal Efficiency per Reactor Volume
**Q:** Which reactor gives highest removal efficiency for a given reactor volume?
**Options:** a. Batch reactor | **b. Plug flow reactor** | c. CMBR | d. CSTR
**✅ Answer: (b) Plug Flow Reactor (PFR)**

> **Why PFR wins:** In a PFR, fluid moves as a plug with no backmixing — concentration decreases progressively along length, maintaining a high driving force throughout. In a CSTR, incoming high-concentration feed is instantly diluted to the low effluent concentration, drastically reducing the reaction driving force.

At high fractional conversions, CSTR requires **significantly larger volume** than PFR for the same removal.

**PFR vs CSTR comparison (from Example 5 in slides):**
- CSTR needed 500 m³ for 68% removal
- PFR needed only ~264 m³ for the same removal

---

### Q7. Flow Rate of CMBR
**Q:** Volume = 100 m³, retention time = 5 days. Find flow rate.
**Options:** **a. 20 m³/day** | b. 50 | c. 25 | d. 10 m³/day
**✅ Answer: (a) 20 m³/day**

$$\theta = \frac{V}{Q} \quad \Rightarrow \quad Q = \frac{V}{\theta} = \frac{100}{5} = \mathbf{20 \text{ m}^3/\text{day}}$$

- (b) 50 → V/θ = 100/2 (wrong θ)
- (c) 25 → V/θ = 100/4 (wrong)
- (d) 10 → V/θ = 100/10 (wrong)

---

### Q8. Volume of Plug Flow Reactor
**Q:** PFR volume for C_out = 50 mg/L; Q = 100 m³/day, k = 0.23/day, C_in = 200 mg/L.
**Options:** **a. 603 m³** | b. 500 | c. 850 | d. 900 m³
**✅ Answer: (a) 603 m³**

**PFR design equation (first-order):**
$$\frac{C_{out}}{C_{in}} = e^{-kV/Q}$$
$$V = -\ln\left(\frac{C_{out}}{C_{in}}\right) \times \frac{Q}{k}$$
$$V = -\ln\left(\frac{50}{200}\right) \times \frac{100}{0.23}$$
$$V = -\ln(0.25) \times \frac{100}{0.23}$$
$$V = 1.386 \times \frac{100}{0.23} = \mathbf{602.6 \approx 603 \text{ m}^3}$$

**Bonus comparison — CSTR for same conditions:**
$$V_{CSTR} = \frac{C_{in} - C_{out}}{k \cdot C_{out}} \times Q = \frac{150}{0.23 \times 50} \times 100 \approx 1304 \text{ m}^3$$
→ CSTR needs **>2× the volume** of PFR for same removal. ✓

---

### Q9. NOT True About PFR
**Q:** Which is NOT true about a Plug Flow Reactor?
**Options:** **a. Inter mixing of particles will happen in PFR** | b. Inter mixing will not happen | c. Length >> Width | d. Concentration less at effluent end
**✅ Answer: (a) — this statement is FALSE (i.e., the NOT true one)**

> In an ideal PFR, **NO intermixing (backmixing)** occurs. Each fluid parcel moves independently as a plug.

**What IS true (b, c, d are all correct):**
- (b) No intermixing — correct ✓
- (c) Length >> Width — enables unidirectional plug flow ✓
- (d) Concentration decreases from inlet to outlet ✓

---

### Q10. Instantaneous Dispersion Throughout Reactor
**Q:** In which reactor are fluid particles instantly dispersed throughout the reactor volume?
**Options:** a. Batch reactor | b. Plug flow reactor | **c. Continuous stirred tank reactor** | d. Sequential batch reactor
**✅ Answer: (c) CSTR**

> The defining characteristic of a CSTR: incoming fluid is **instantaneously and completely mixed** throughout the entire reactor → effluent concentration = concentration everywhere inside.

- (a) Batch: no continuous flow
- (b) PFR: plugs move independently, NO mixing
- (d) Sequential batch: cycled (fill → react → settle → discharge)

---

### Q11. Reynolds Number
**Q:** ___ is the dimensionless quantity to find laminar flow pattern.
**Options:** a. Vortex number | **b. Reynolds number** | c. Viscosity number | d. None
**✅ Answer: (b) Reynolds Number**

$$Re = \frac{\rho \cdot V \cdot D}{\mu}$$

| Re | Flow Type |
|---|---|
| < 2,000 | Laminar (smooth, sheet-like) |
| 2,000–4,000 | Transitional |
| > 4,000 | Turbulent (chaotic, eddy currents) |

- (a) "Vortex number" — not a standard term
- (c) "Viscosity number" — not a standard term

---

### Q12. Mass Transport Processes
**Q:** Different mass transport processes are?
**Options:** a. Diffusion | b. Dispersion | c. Advection | **d. All the above**
**✅ Answer: (d) All of the above**

Three fundamental transport mechanisms:
1. **Advection** — transport by bulk fluid motion
2. **Diffusion** — transport by random molecular motion (Fickian)
3. **Dispersion** — spreading due to velocity variations

Combined: $J = J_{advection} + J_{diffusion} + J_{dispersion}$

---

### Q13. Turbulent Diffusion
**Q:** ___ is due to random fluctuation in advective velocity.
**Options:** **a. Turbulent diffusion** | b. Diffusion | c. Dispersion | d. Laminar dispersion
**✅ Answer: (a) Turbulent diffusion**

> **Turbulent diffusion** arises from random fluctuations in the advective (bulk) velocity field — eddies and swirls in turbulent flow cause mixing far beyond molecular diffusion alone.

- (b) **Molecular diffusion:** random thermal motion of molecules (Brownian) — independent of flow
- (c) **Dispersion:** broader term including both turbulent diffusion AND mechanical mixing
- (d) "Laminar dispersion" — non-standard term

---

### Q14. Fick's Law
**Q:** "Rate of diffusion across unit area is proportional to concentration gradient" — which law?
**Options:** a. Stokes law | b. Gravitational law | **c. Fick's law** | d. First law of thermodynamics
**✅ Answer: (c) Fick's Law**

$$\boxed{J = -D \frac{dC}{dx}}$$

- J = diffusive flux (mass/area/time)
- D = diffusion coefficient (m²/s)
- dC/dx = concentration gradient
- Negative sign: flux from high → low concentration

**Why others are wrong:**
- (a) **Stokes' Law:** drag force on a sphere in viscous fluid — used for settling velocity
- (b) **Gravitational law:** describes gravitational attraction force
- (d) **First law of thermodynamics:** energy conservation (ΔU = Q − W)

---

### Q15. Greenhouse Gas Statements
**Q:** Which is/are correct? (a) Without atmosphere Earth's surface would be cooler | (b) Water vapour is a greenhouse gas
**Options:** a. (a) only | b. (b) only | **c. Both (a) and (b)** | d. Neither
**✅ Answer: (c) Both are correct**

**Statement (a):** Without GHGs, Earth's average temperature ≈ −18°C instead of current +15°C — a difference of ~33°C due to the natural greenhouse effect. ✓

**Statement (b):** Water vapour (H₂O) is the **most abundant and potent natural greenhouse gas**, responsible for ~50% of the greenhouse effect. ✓

**Other GHGs:** CO₂, CH₄, N₂O, O₃.

> The "enhanced greenhouse effect" = additional warming from anthropogenic emissions (CO₂, CH₄, etc.).

---

## PART C — KEY FORMULAS QUICK REFERENCE

| Formula | Description |
|---|---|
| $\frac{dm}{dt} = \dot{m}_{in} - \dot{m}_{out} + \dot{m}_{reaction}$ | Mass balance (fundamental) |
| $C_e = C_0 - kt$ | CMBR zero-order |
| $C_e = C_0 e^{-kt}$ | CMBR first-order |
| $\frac{1}{C_e} = \frac{1}{C_0} + kt$ | CMBR second-order |
| $C_{out} = C_0 - kV/Q$ | CSTR zero-order (steady state) |
| $C_{out} = C_0 / (1 + k\theta)$ | CSTR first-order (steady state) |
| $C_e = C_0 e^{-kV/Q}$ | PFR first-order |
| $\theta = V/Q$ | Hydraulic Retention Time (HRT) |
| $\Delta PE = m \cdot g \cdot \Delta h$ | Gravitational potential energy |
| $\Delta E = m \cdot c \cdot \Delta T$ | Thermal energy |
| $J = -D \frac{dC}{dx}$ | Fick's First Law |
| $Re = \rho V D / \mu$ | Reynolds Number |
| $v_s = \frac{g(\rho_p - \rho_f)}{18\mu} D_p^2$ | Stokes settling velocity |

---

*Source: NPTEL Lectures 16–19 (Week 4) — Dr. Brajesh Kumar Dubey, IIT Kharagpur*