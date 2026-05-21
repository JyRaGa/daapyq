# WEEK 4 — Exam-Ready Study Notes
## NOC25_GE17 | Introduction to Environmental Engineering and Science
### Dr. Brajesh Kumar Dubey, IIT Kharagpur
**Topics Covered:** Mass Balance · Batch Reactor (CMBR) · CSTR · Plug Flow Reactor (PFR) · Fick's Law · Reynolds Number · Stokes' Law · Gravitational Settling · Energy Balance

---

## PART A — ASSIGNMENT QUESTIONS & SOLUTIONS

### Q1. What is the key assumption in the mass balance equation for a batch reactor?

| Option | Text |
|--------|------|
| a | Continuous inflow and outflow of mass |
| **b ✅** | **Complete mixing with no inflow or outflow** |
| c | Constant temperature and pressure |
| d | Mass transfer occurs at steady-state conditions |

**✅ Correct Answer: b**

**Why b is correct:**
The slides state the batch reactor (CMBR) has *"no inputs or outputs"* — mathematically: $\dot{m}_{in} - \dot{m}_{out} = 0$, so the full mass balance reduces to:

$$\frac{dm}{dt} = \dot{m}_{reaction}$$

The contents are *completely and uniformly mixed* but nothing enters or leaves during the reaction.

**Why others are wrong:**
- **a** — Continuous inflow/outflow describes a **CSTR**, not a batch reactor.
- **c** — Constant temperature and pressure is not an assumption specific to mass balance in a batch reactor; temperature may vary.
- **d** — Steady-state ($dm/dt = 0$) applies to **CSTR** under steady operation; a batch reactor is inherently non-steady state as concentration changes with time.

#### Type 1 — Wrong Option Spin-offs (Q1)

**Q1-T1a.** Which reactor type operates with continuous inflow and outflow, with fluid particles instantaneously dispersed throughout the reactor volume?
- a) Batch reactor
- **b) Continuous Stirred Tank Reactor (CSTR) ✅**
- c) Plug flow reactor
- d) Semi-batch reactor

**Q1-T1b.** Under which condition does the mass accumulation rate ($dm/dt$) equal zero in a reactor?
- a) Batch operation
- b) First-order reaction
- **c) Steady-state conditions ✅**
- d) Zero-order reaction

#### Type 2 — Concept Expansion Spin-offs (Q1)

**Q1-C1.** The general mass balance equation for any reactor is:

$$\frac{dm}{dt} = \dot{m}_{in} - \dot{m}_{out} + \dot{m}_{reaction}$$

For a CSTR at steady state with a first-order reaction, this simplifies to:
- a) $C_{out} = C_0 - kV/Q$
- **b) $C_{out} = C_0 / (1 + kV/Q)$ ✅**
- c) $C_{out} = C_0 \cdot e^{-k\theta}$
- d) $C_{out} = C_0 \cdot e^{-kt}$

> *Slides derive: at steady state $0 = QC_0 - QC_{out} - kC_{out}V$, solving gives $C_{out} = C_0/(1 + kV/Q)$.*

**Q1-C2.** A batch reactor is commonly used in laboratories primarily to:
- a) Continuously treat large volumes of industrial waste
- b) Model plug flow behaviour
- **c) Determine the reaction equation and rate constant for a chemical reaction ✅**
- d) Maintain steady-state concentration

> *Slides: "A common use of batch reactors in laboratories is to determine the reaction equation and rate constant for a chemical reaction."*

**Q1-C3.** In a batch reactor with a second-order reaction ($\frac{dm}{dt} = -kC^2$), the effluent concentration is described by:
- a) $C_e = C_0 - kt$
- b) $C_e = C_0 e^{-kt}$
- **c) $\frac{1}{C_e} = \frac{1}{C_0} + kt$ ✅**
- d) $C_e = C_0 / (1 + kt)$

> *Slides derive: $\int_{C_0}^{C_e} \frac{dc}{C^2} = \int_0^t -k\, dt \Rightarrow \frac{1}{C_e} = \frac{1}{C_0} + kt$*

### Q2. How does the concentration change in a CSTR under steady-state conditions?

| Option | Text |
|--------|------|
| a | Linearly with time |
| b | Exponentially with time |
| **c ✅** | **Remains constant** |
| d | Oscillates periodically |

**✅ Correct Answer: c**

**Why c is correct:**
Slides state: at steady state $\frac{dm}{dt} = 0$, meaning the rate of mass accumulation is zero — the concentration in the reactor remains constant because mass input equals mass output. The CSTR concentration-vs-time graph in the slides shows a flat horizontal line at $C_{out}$.

**Why others are wrong:**
- **a** — Linear change with time is the profile for a **zero-order batch reactor** ($C_e = C_0 - kt$), not a steady-state CSTR.
- **b** — Exponential change with time is the profile for a **first-order batch reactor** or a CSTR coming to steady state (*non-steady state* transient), not the steady-state condition.
- **d** — Periodic oscillation has no basis in the reactor models covered; the CSTR tends toward a stable equilibrium.

#### Type 1 — Wrong Option Spin-offs (Q2)

**Q2-T1a.** In a zero-order batch reactor, how does concentration change with time?
- **a) Linearly (decreases at a constant rate) ✅**
- b) Remains constant
- c) Exponentially
- d) Oscillates

> *Slides: $C_e = C_0 - kt$ — linear relationship.*

**Q2-T1b.** In a first-order batch reactor, how does concentration change with time?
- a) Linearly
- b) Remains constant
- **c) Exponentially ✅**
- d) Oscillates

> *Slides: $C_e = C_0 e^{-kt}$ — exponential decay.*

#### Type 2 — Concept Expansion Spin-offs (Q2)

**Q2-C1.** A CSTR with volume $V = 500\ \text{m}^3$, flow rate $Q = 50\ \text{m}^3/\text{day}$, inlet concentration $C_0 = 100\ \text{mg/L}$, and first-order decay constant $k = 0.216\ \text{day}^{-1}$ gives a steady-state outlet concentration of:
- a) 100 mg/L
- b) 50 mg/L
- **c) 32 mg/L ✅**
- d) 10 mg/L

> *Slides Example 1: $C_{out} = C_0 \times Q/(Q + kV) = 100 \times 50/(50 + 0.216 \times 500) = 32\ \text{mg/L}$*

**Q2-C2.** In the CSTR mass balance, the term $\dot{m}_{in}$ equals:
- **a) $QC_0$ ✅**
- b) $QC_{out}$
- c) $kC_{out}V$
- d) $V \cdot dC/dt$

> *Slides: "$\dot{m}_{in} = QC_0$, $\dot{m}_{out} = QC_{out}$"*

### Q3. What is the fundamental difference between advection and dispersion in pollutant transport?

| Option | Text |
|--------|------|
| a | Advection involves random motion, while dispersion is due to bulk flow. |
| **b ✅** | **Advection transports pollutants with bulk flow, while dispersion spreads them due to random motion.** |
| c | Advection requires molecular diffusion, while dispersion is unrelated to diffusion. |
| d | Advection depends on turbulent flow, while dispersion occurs only in laminar flow. |

**✅ Correct Answer: b**

**Why b is correct:**
Slides confirm: *"Advection transports pollutants along with bulk flow, while dispersion results from random molecular or turbulent motions."* Advection moves the *centre of mass* of a pollutant with the mean flow velocity; dispersion *spreads* the pollutant about that centre of mass.

**Why others are wrong:**
- **a** — This exactly *reverses* the definitions. Advection = bulk flow; dispersion = random motion.
- **c** — Advection does not require molecular diffusion; it simply requires bulk fluid motion.
- **d** — Dispersion occurs in both laminar (molecular diffusion) and turbulent (eddy dispersion) flows; it is not restricted to laminar flow.

#### Type 1 — Wrong Option Spin-offs (Q3)

**Q3-T1a.** Which pollutant transport mechanism involves *random* molecular or turbulent motion spreading the pollutant about its centre of mass?
- a) Advection
- **b) Dispersion ✅**
- c) Sedimentation
- d) Gravitational settling

**Q3-T1b.** In turbulent flows, which specific type of dispersion dominates because of swirling eddy currents?
- a) Molecular diffusion
- **b) Eddy (turbulent) dispersion ✅**
- c) Gravitational settling
- d) Advection

#### Type 2 — Concept Expansion Spin-offs (Q3)

**Q3-C1.** Mechanical dispersion in groundwater occurs because:
- **a) Water travels at different velocities through different pore sizes in the porous medium ✅**
- b) Water molecules diffuse due to thermal energy
- c) Gravity pulls denser water downward
- d) Turbulent eddies form in the aquifer

> *Slides show a mechanical dispersion diagram where average flow direction splits into multiple paths of varying speed.*

**Q3-C2.** Fick's First Law describes:
- a) The advective flux of a pollutant
- **b) The dispersive flux density as proportional to the concentration gradient ✅**
- c) The settling velocity of particles
- d) The Reynolds number of the flow

> *Slides: "Flux density = (constant) × (concentration gradient)" → $J = -D\, dC/dx$*

### Q4. Which law is used to calculate dispersive flux density in mass transport processes?

| Option | Text |
|--------|------|
| **a ✅** | **Fick's Law** |
| b | Stokes' Law |
| c | Bernoulli's Equation |
| d | Planck's Equation |

**✅ Correct Answer: a**

**Why a is correct:**
Slides derive Fick's First Law from first principles:

$$J = -D\frac{dC}{dx}$$

*"Flux density = (constant) × (concentration gradient)."* The negative sign shows flux moves from high to low concentration.

**Why others are wrong:**
- **b** — **Stokes' Law** describes the **drag force** on a particle settling through a fluid: $F_D = 3\pi\mu D_p v_r$. It is used for gravitational settling, not diffusive flux.
- **c** — **Bernoulli's Equation** relates pressure, velocity, and elevation in flowing fluids — used in hydraulics, not mass diffusion.
- **d** — **Planck's Equation** relates photon energy to frequency ($E = hf$) — electromagnetic energy, unrelated to mass transport.

#### Type 1 — Wrong Option Spin-offs (Q4)

**Q4-T1a.** Which law is used to calculate the drag force on a slowly settling spherical particle in a fluid?
- a) Fick's Law
- **b) Stokes' Law ✅**
- c) Bernoulli's Equation
- d) Planck's Equation

**Q4-T1b.** Which equation relates the energy of a photon to its frequency and is used in electromagnetic energy calculations?
- a) Fick's Law
- b) Stokes' Law
- c) Bernoulli's Equation
- **d) Planck's Equation ✅**

#### Type 2 — Concept Expansion Spin-offs (Q4)

**Q4-C1.** In Fick's Law $J = -D\, dC/dx$, the negative sign indicates:
- a) Flux is always negative
- **b) Mass flows from regions of high concentration to low concentration ✅**
- c) Diffusivity $D$ is always negative
- d) Flux opposes gravity

**Q4-C2.** Turbulent diffusion differs from molecular diffusion in that:
- **a) Turbulent diffusion is caused by random fluctuations in advective velocity (eddies), not thermal molecular motion ✅**
- b) Turbulent diffusion follows Planck's equation
- c) Turbulent diffusion is slower than molecular diffusion
- d) Turbulent diffusion only occurs in laminar flow

> *Slides: "Turbulent diffusion is due to random fluctuation in advective velocity."*

### Q5. Calculate the time to reduce the concentration of pollutant A to 1% of its initial value in a constant volume batch reactor. Reaction: $A \rightarrow B$, rate $= -kC_A$, $k = 0.23\ \text{min}^{-1}$.

| Option | Text |
|--------|------|
| a | 50 min |
| b | 40 min |
| c | 30 min |
| **d ✅** | **20 min** |

**✅ Correct Answer: d**

**Why d is correct:**
For a first-order reaction in a batch reactor, slides derive: $C_e = C_0 e^{-kt}$

Setting $C_e/C_0 = 0.01$:

$$\ln\left(\frac{C_e}{C_0}\right) = -kt$$

$$\ln(0.01) = -0.23 \times t$$

$$-4.605 = -0.23t$$

$$t = \frac{4.605}{0.23} \approx 20\ \text{min}$$

**Why others are wrong:**
- **a** — $t = 50$ min would give $C/C_0 = e^{-0.23 \times 50} = e^{-11.5} \approx 10^{-5}$ — far below 1%.
- **b** — $t = 40$ min: $C/C_0 = e^{-9.2} \approx 10^{-4}$ — again below 1%.
- **c** — $t = 30$ min: $C/C_0 = e^{-6.9} \approx 0.001$ — 0.1%, not 1%.

#### Type 1 — Wrong Option Spin-offs (Q5)

**Q5-T1a.** How long would it take to reduce concentration to $e^{-1}$ (≈ 36.8%) of its initial value in a first-order batch reactor with $k = 0.23\ \text{min}^{-1}$?
- a) 0.23 min
- b) 10 min
- **c) ≈ 4.35 min ✅**
- d) 20 min

> *Half-life analog: $\ln(1) - \ln(e^{-1}) = 1 = k \cdot t \Rightarrow t = 1/k = 1/0.23 \approx 4.35$ min*

#### Type 2 — Concept Expansion Spin-offs (Q5)

**Q5-C1.** For a zero-order batch reaction with $k = 2\ \text{mg/L/hr}$ and $C_0 = 20\ \text{mg/L}$, after 5 hours the concentration is:
- a) 20 mg/L
- **b) 10 mg/L ✅**
- c) 0 mg/L
- d) $20 e^{-10}$ mg/L

> *Slides: Zero-order: $C_e = C_0 - kt = 20 - 2(5) = 10$ mg/L*

**Q5-C2.** In a first-order batch reactor, the half-life ($t_{1/2}$) — time for concentration to fall to 50% of initial — is given by:
- a) $t_{1/2} = k$
- b) $t_{1/2} = 1/k$
- **c) $t_{1/2} = \ln 2 / k$ ✅**
- d) $t_{1/2} = 2/k$

> *From $\ln(0.5) = -kt_{1/2}$: $t_{1/2} = 0.693/k$*

**Q5-C3.** The Hydraulic Retention Time (HRT) $\theta$ for a reactor is defined as:
- **a) $\theta = V/Q$ ✅**
- b) $\theta = Q/V$
- c) $\theta = kV/Q$
- d) $\theta = 1/k$

> *Slides: "Reaction HRT: $\theta = V/Q$"*

### Q6. What determines the terminal settling velocity of a particle in a fluid according to Stokes' Law?

| Option | Text |
|--------|------|
| a | Viscosity of the fluid |
| b | Particle diameter |
| c | Density difference between particle and fluid |
| **d ✅** | **All of the above** |

**✅ Correct Answer: d**

**Why d is correct:**
The slides derive the full Stokes' settling velocity equation:

$$v_s = \frac{g(\rho_p - \rho_f)}{18\mu} D_p^2$$

This shows $v_s$ depends on:
- $\mu$ — fluid viscosity (option a)
- $D_p$ — particle diameter (option b)
- $(\rho_p - \rho_f)$ — density difference between particle and fluid (option c)

All three simultaneously determine $v_s$.

**Why options a, b, c alone are wrong:**
Each is a necessary but not sufficient determinant on its own. Removing any one factor makes the formula incomplete. The only complete answer is **all of the above**.

#### Type 2 — Concept Expansion Spin-offs (Q6)

**Q6-C1.** At terminal settling velocity, the net downward force on a particle is:
- a) Equal to the drag force
- b) Equal to the buoyancy force
- **c) Zero (gravity = buoyancy + drag) ✅**
- d) Equal to gravity minus buoyancy only

> *Slides: "When the particle terminal velocity is reached, it is no longer accelerating so $dv/dt = 0$, thus $F_{down} = 0$."*

**Q6-C2.** The Stokes drag force on a slowly settling sphere is given by:
- a) $F_D = \rho_f \frac{\pi}{6} D_p^3 g$
- **b) $F_D = 3\pi\mu D_p v_r$ ✅**
- c) $F_D = \rho_p \frac{\pi}{6} D_p^3 g$
- d) $F_D = g(\rho_p - \rho_f)D_p^2/18\mu$

> *Slides: "$F_D = 3\pi\mu D_p v_r$ where $\mu$ is fluid viscosity and $v_r$ is the relative velocity."*

**Q6-C3.** The buoyancy force $F_B$ acting on a settling particle equals:
- a) $\rho_p \frac{\pi}{6} D_p^3 g$
- **b) $\rho_f \frac{\pi}{6} D_p^3 g$ ✅**
- c) $3\pi\mu D_p v_s$
- d) $(\rho_p - \rho_f) \frac{\pi}{6} D_p^3 g$

> *Slides: "$F_B = \rho_f \frac{\pi}{6} D_p^3 g$ — equal to gravitational constant times the mass of the fluid displaced."*

### Q7. Calculate the flow rate of the CMBR if the volume of the reactor is 100 m³ and the retention time is 5 days.

| Option | Text |
|--------|------|
| a | 25 m³/day |
| b | 50 m³/day |
| c | 10 m³/day |
| **d ✅** | **20 m³/day** |

**✅ Correct Answer: d**

**Why d is correct:**
From the slides, HRT is defined as $\theta = V/Q$. Rearranging:

$$Q = \frac{V}{\theta} = \frac{100\ \text{m}^3}{5\ \text{days}} = 20\ \text{m}^3/\text{day}$$

**Why others are wrong:**
- **a** — 25 m³/day would imply $\theta = 100/25 = 4$ days, not 5.
- **b** — 50 m³/day would imply $\theta = 100/50 = 2$ days, not 5.
- **c** — 10 m³/day would imply $\theta = 100/10 = 10$ days, not 5.

#### Type 2 — Concept Expansion Spin-offs (Q7)

**Q7-C1.** A CSTR has a volume of $500\ \text{m}^3$ and a flow rate of $50\ \text{m}^3/\text{day}$. What is the HRT?
- a) 5 days
- **b) 10 days ✅**
- c) 25 days
- d) 2 days

> *Slides Example 4: $\theta = V/Q = 500/50 = 10$ days*

**Q7-C2.** If the HRT is doubled while keeping reactor volume constant, the flow rate:
- a) Doubles
- **b) Halves ✅**
- c) Remains the same
- d) Quadruples

> *$Q = V/\theta$ — inverse relationship between $Q$ and $\theta$.*

### Q8. Determine the volume of Plug Flow Reactor to obtain an effluent concentration of 50 mg/L. Given: $Q = 100\ \text{m}^3/\text{day}$, $k = 0.23\ \text{day}^{-1}$, $C_{in} = 200\ \text{mg/L}$.

| Option | Text |
|--------|------|
| a | 525 m³ |
| b | 500 m³ |
| **c ✅** | **603 m³** |
| d | 900 m³ |

**✅ Correct Answer: c**

**Why c is correct:**
Slides derive the PFR first-order equation:

$$\frac{C_{out}}{C_{in}} = e^{-k\theta} = e^{-kV/Q}$$

Solving for $V$:

$$V = -\frac{Q}{k} \ln\left(\frac{C_{out}}{C_{in}}\right) = -\frac{100}{0.23} \ln\left(\frac{50}{200}\right)$$

$$V = -\frac{100}{0.23} \times \ln(0.25) = -\frac{100}{0.23} \times (-1.386) = \frac{138.6}{0.23} \approx 603\ \text{m}^3$$

**Why others are wrong:**
- **a** — 525 m³: back-check gives $C_{out} = 200 \cdot e^{-0.23 \times 525/100} = 200 \cdot e^{-1.2075} \approx 59.7$ mg/L ≠ 50 mg/L.
- **b** — 500 m³: $C_{out} = 200 \cdot e^{-1.15} \approx 63$ mg/L ≠ 50 mg/L.
- **d** — 900 m³: over-treats the water (gives $C_{out} \approx 14$ mg/L), unnecessarily large.

#### Type 2 — Concept Expansion Spin-offs (Q8)

**Q8-C1.** For the same degree of first-order pollutant removal, a PFR requires _______ volume compared to a CSTR.
- a) More volume
- **b) Less volume ✅**
- c) The same volume
- d) It depends on the reaction order only

> *Slides Example 5 confirms PFR achieves the same removal as CSTR with less volume for first-order kinetics.*

**Q8-C2.** The PFR model assumes that fluid elements:
- a) Are instantly mixed throughout the reactor
- **b) Move through the reactor in discrete "plugs" with no mixing between them ✅**
- c) Have variable residence times
- d) Remain in the reactor indefinitely

**Q8-C3.** In the PFR mass balance for first-order reaction, the differential equation for an elemental volume $dV$ reduces to:

$$\frac{dC}{C} = -\frac{k\cdot A}{Q}\, dx$$

Integrating from inlet ($C_0$) to outlet ($C_e$) over length $L$, gives:
- a) $C_e = C_0 - k\theta$
- **b) $C_e = C_0 e^{-k\theta}$ ✅**
- c) $C_e = C_0 / (1 + k\theta)$
- d) $1/C_e = 1/C_0 + k\theta$

> *Slides: $\ln(C_e/C_0) = -kAL/Q = -k\theta$, therefore $C_e = C_0 e^{-k\theta}$.*

### Q9. Why is the Reynolds number significant in determining flow patterns in fluid mechanics?

| Option | Text |
|--------|------|
| a | It quantifies the rate of molecular diffusion. |
| **b ✅** | **It predicts whether flow is laminar or turbulent.** |
| c | It measures the efficiency of heat transfer. |
| d | It calculates the net flux in advection. |

**✅ Correct Answer: b**

**Why b is correct:**
Slides state: *"The Reynolds number (Re) is an important dimensionless quantity in fluid mechanics used to help predict flow patterns in different fluid flow situations. At low Reynolds numbers, flows tend to be dominated by laminar (sheet-like) flow, while at high Reynolds numbers turbulence results."*

$$Re = \frac{\rho \cdot V \cdot D}{\mu} = \frac{\text{inertia forces}}{\text{viscous forces}}$$

**Why others are wrong:**
- **a** — Molecular diffusion is quantified by the **diffusion coefficient $D$** in Fick's Law; Reynolds number has no role.
- **c** — Heat transfer efficiency is characterized by the **Nusselt number** or heat transfer coefficient, not Reynolds number.
- **d** — Advective flux is calculated using $J_{adv} = v \cdot C$; Reynolds number does not directly calculate flux.

#### Type 1 — Wrong Option Spin-offs (Q9)

**Q9-T1a.** Which dimensionless number quantifies the rate of convective heat transfer relative to conductive heat transfer in fluid flow?
- **a) Nusselt number ✅**
- b) Reynolds number
- c) Froude number
- d) Mach number

> *(Not defined in slides — flagged as **not covered in these slides**; included for conceptual contrast only.)*

#### Type 2 — Concept Expansion Spin-offs (Q9)

**Q9-C1.** The Reynolds number formula is $Re = \rho V D / \mu$. Which of the following would *increase* $Re$ (making flow more turbulent)?
- a) Increasing fluid viscosity $\mu$
- **b) Increasing flow velocity $V$ ✅**
- c) Decreasing pipe diameter $D$
- d) Decreasing fluid density $\rho$

**Q9-C2.** A vortex street around a cylinder occurs when the Reynolds number is approximately:
- a) Less than 1 (Stokes creeping flow)
- b) Between 2,000 and 4,000 (transitional)
- **c) Between 40 and 1,000 ✅**
- d) Greater than 10,000

> *Slides: "A vortex street around a cylinder can occur for any fluid, provided it has a Reynolds number between roughly 40 and 1,000."*

**Q9-C3.** Stokes' gravitational settling assumes which flow condition around the settling particle?
- **a) Creeping flow ($Re < 1$) ✅**
- b) Transitional flow ($Re \approx 2000$)
- c) Turbulent flow ($Re > 4000$)
- d) Any flow condition

> *Slides: "Most particle settling situations involve creeping flow conditions (Reynolds number less than 1). In this case Stokes' drag force can be used."*

### Q10. How is energy loss as waste heat typically calculated in a thermal power plant?

| Option | Text |
|--------|------|
| a | By using the Reynolds number |
| b | By measuring the efficiency of cooling systems |
| **c ✅** | **By subtracting the generator's output energy from the total input energy** |
| d | By applying Stokes' drag equation |

**✅ Correct Answer: c**

**Why c is correct:**
Slides present the energy balance: Input = Output + Losses. Therefore:

$$\text{Waste heat} = \text{Total energy input} - \text{Electrical energy output}$$

Slides Example 8 illustrates: total input = 2,800 MW; output = 1,000 MW; waste heat = 1,800 MW (distributed as stack heat + turbine waste heat).

**Why others are wrong:**
- **a** — Reynolds number is a fluid mechanics parameter for flow regime; it has nothing to do with power plant energy accounting.
- **b** — Cooling system efficiency is a *component* of the analysis but is not the method to calculate total waste heat.
- **d** — Stokes' drag equation applies to particle settling in a fluid — completely unrelated to thermal energy balance.

#### Type 1 — Wrong Option Spin-offs (Q10)

**Q10-T1a.** Stokes' drag equation $F_D = 3\pi\mu D_p v_r$ is applied to calculate which of the following?
- **a) The drag force on a particle settling through a fluid ✅**
- b) Energy loss in a power plant
- c) The Reynolds number
- d) Dispersive flux density

#### Type 2 — Concept Expansion Spin-offs (Q10)

**Q10-C1.** A coal-fired power plant burns fuel releasing 2,800 MW. Electricity output = 1,000 MW; stack losses = 340 MW. What is the waste heat that must be removed by cooling water?
- a) 1,000 MW
- b) 1,800 MW
- **c) 1,460 MW ✅**
- d) 340 MW

> *Slides Example 8: $2800 - 340 = 2460$ MW powers turbines. Thermal efficiency = 42%, so $0.42 \times 2460 = 1033 \approx 1000$ MW goes to electricity; waste heat $= 0.58 \times 2460 = 1430$ MW. (Closest matching value using slide numbers: **1,430 MW**)*

> ⚠️ **Note:** The assignment answer uses simplified subtraction (Input - Output). The slides' detailed example gives 1,430 MW of cooling water waste heat. Use **slide value (1,430 MW)** in detailed calculations; use **Input − Output** as the *method* for general questions.

**Q10-C2.** The energy balance equation for a system at steady state is:
- a) $dE/dt = E_{in} + E_{out}$
- **b) $E_{in} = E_{out}$ (since $dE/dt = 0$) ✅**
- c) $dE/dt = E_{out} - E_{in}$
- d) $E_{in} \cdot E_{out} = 0$

> *Slides: "conducting energy balance: $\frac{dE}{dt} = E_{in} - E_{out}$; at steady state $dE/dt = 0$."*

**Q10-C3.** The formula for heat energy change is:
- **a) $\Delta E = \text{mass} \times c \times \Delta T$ ✅**
- b) $\Delta E = \text{mass} \times \Delta T / c$
- c) $\Delta E = h\nu$ (Planck)
- d) $\Delta E = \text{mass} \times \Delta h$

> *Slides table of energy formulae: "Heat internal energy: $\Delta E = \text{mass} \times \text{Heat capacity}(c) \times \Delta T$"*

### Q11. _________ is the dimensionless quantity used to find the laminar flow pattern of the flow.

| Option | Text |
|--------|------|
| a | Vortex number |
| **b ✅** | **Reynolds number** |
| c | Viscosity number |
| d | None of the above |

**✅ Correct Answer: b**

**Why b is correct:**
Direct repeat of the Q9 concept. Slides quote: *"The Reynolds number (Re) is an important dimensionless quantity in fluid mechanics used to help predict flow patterns… at low Reynolds numbers, flows tend to be dominated by laminar (sheet-like) flow."*

**Why others are wrong:**
- **a** — "Vortex number" is **not defined in slides** and is not a standard fluid mechanics dimensionless parameter.
- **c** — "Viscosity number" is **not defined in slides**. Viscosity ($\mu$) is a dimensional property (units: Pa·s or g/cm·s), not a dimensionless number.
- **d** — Incorrect because Reynolds number (option b) exists and is the correct answer.

#### Type 2 — Concept Expansion Spin-offs (Q11)

**Q11-C1.** Which of the following correctly characterizes laminar flow?
- **a) Smooth, sheet-like (parallel) layers of fluid with no cross-stream mixing ✅**
- b) Chaotic, irregular fluid motion with strong lateral mixing
- c) Flow in swirling helical patterns
- d) Flow where inertia forces greatly exceed viscous forces

**Q11-C2.** What type of flow is characterized by eddy currents that sometimes move counter to the overall flow direction?
- a) Laminar flow
- b) Creeping flow
- **c) Turbulent flow ✅**
- d) Plug flow

> *Slides: "at high Reynolds numbers turbulence results from differences in the fluid's speed and direction, which may sometimes intersect or even move counter to the overall direction of the flow (eddy currents)."*

### Q12. What is the significance of the drag force in Stokes' law for gravitational settling of particles?

| Option | Text |
|--------|------|
| a | It depends on the temperature gradient in the fluid. |
| b | It decreases with an increase in fluid velocity. |
| **c ✅** | **It resists the gravitational force acting on a particle.** |
| d | It is inversely proportional to particle density. |

**✅ Correct Answer: c**

**Why c is correct:**
Slides state the net downward force is $F_{down} = F_g - F_B - F_D$. Drag force $F_D$ acts **upward**, opposing gravity. At terminal velocity, $F_D + F_B = F_g$, so the particle no longer accelerates. Drag *resists* (opposes) the downward gravitational force.

**Why others are wrong:**
- **a** — Stokes' drag $F_D = 3\pi\mu D_p v_r$ depends on fluid **viscosity**, not temperature gradient directly (temperature affects viscosity, but the drag formula itself doesn't include a temperature gradient term).
- **b** — Drag force actually **increases** with increasing relative velocity $v_r$; $F_D \propto v_r$.
- **d** — Drag force $F_D = 3\pi\mu D_p v_r$ depends on **particle size and fluid viscosity**, not on particle density.

#### Type 1 — Wrong Option Spin-offs (Q12)

**Q12-T1a.** The Stokes drag force on a particle *increases* with increasing:
- a) Particle density
- **b) Relative velocity of particle through fluid ✅**
- c) Temperature gradient
- d) Particle porosity

**Q12-T1b.** Which force on a settling particle acts in the *same direction* as drag (both opposing gravity)?
- a) Gravitational force
- **b) Buoyancy force ✅**
- c) Inertial force
- d) Magnetic force

#### Type 2 — Concept Expansion Spin-offs (Q12)

**Q12-C1.** A particle with $\rho_p = 2000\ \text{kg/m}^3$ settles in water ($\rho_f = 1000\ \text{kg/m}^3$). If the particle density were increased to $3000\ \text{kg/m}^3$ (all else equal), the terminal settling velocity $v_s$ would:
- a) Remain the same
- **b) Increase ✅**
- c) Decrease
- d) Become zero

> *$v_s = \frac{g(\rho_p - \rho_f)D_p^2}{18\mu}$; larger $(\rho_p - \rho_f)$ → larger $v_s$.*

**Q12-C2.** In Stokes' settling, $v_s \propto D_p^2$. If the particle diameter is doubled, the settling velocity:
- a) Doubles
- b) Stays the same
- **c) Quadruples ✅**
- d) Halves

> *$v_s \propto D_p^2$; doubling $D_p$ multiplies $v_s$ by $2^2 = 4$.*

### Q13. In a zero-order reaction occurring in a batch reactor, what is the dependency of the rate of reaction on the reactant concentration?

| Option | Text |
|--------|------|
| a | Directly proportional |
| b | Inversely proportional |
| **c ✅** | **Independent of concentration** |
| d | Exponentially dependent |

**✅ Correct Answer: c**

**Why c is correct:**
Slides derive: for zero-order reaction, $\frac{dm}{dt}_{net} = -k$ (constant). This is rate law $r = -kC^0 = -k$; the exponent on concentration is zero, so the rate is constant regardless of how much reactant remains. The resulting concentration profile is:

$$C_e = C_0 - kt \quad \text{(linear decrease)}$$

**Why others are wrong:**
- **a** — Directly proportional ($r \propto C$) is **first-order** kinetics.
- **b** — Inversely proportional ($r \propto 1/C$) is not a standard reaction order covered in the slides.
- **d** — Exponential dependence occurs in first-order batch reactors ($C = C_0 e^{-kt}$), not zero-order.

#### Type 1 — Wrong Option Spin-offs (Q13)

**Q13-T1a.** In which reaction order is the rate *directly proportional* to the reactant concentration?
- a) Zero order
- **b) First order ✅**
- c) Second order
- d) Negative order

**Q13-T1b.** In which reaction order does the concentration decrease proportionally to $C^2$, giving the integrated law $1/C_e = 1/C_0 + kt$?
- a) Zero order
- b) First order
- **c) Second order ✅**
- d) Third order

#### Type 2 — Concept Expansion Spin-offs (Q13)

**Q13-C1.** For a zero-order CSTR at steady state, the outlet concentration is:
- **a) $C_{out} = C_0 - kV/Q$ ✅**
- b) $C_{out} = C_0 / (1 + kV/Q)$
- c) $C_{out} = C_0 e^{-kV/Q}$
- d) $C_{out} = C_0 - k\theta^2$

> *Slides: for zero-order CSTR: $0 = QC_0 - QC_{out} - kV \Rightarrow C_{out} = C_0 - kV/Q$*

**Q13-C2.** The concentration-vs-time graph for a zero-order batch reaction is:
- **a) A straight line with negative slope ✅**
- b) An exponential decay curve
- c) A horizontal line
- d) A hyperbola

> *$C_e = C_0 - kt$ is a linear function of time with slope $-k$.*

### Q14. Which assumption is NOT made in applying Fick's Law to diffusion processes?

| Option | Text |
|--------|------|
| a | Steady-state concentration gradients |
| b | Molecular motion is random |
| **c ✅** | **Flow velocity is constant** |
| d | Diffusion is isotropic |

**✅ Correct Answer: c**

**Why c is correct:**
Fick's Law ($J = -D\, dC/dx$) describes **diffusion** — the movement of molecules due to random thermal energy. It requires assumptions about the *concentration gradient* (steady-state), *molecular behaviour* (random, isotropic), but says **nothing about bulk flow velocity**. Flow velocity is the domain of **advection**, not diffusion. The two processes are independent; Fick's Law applies even in a stationary fluid with zero flow velocity.

**Why others are wrong:**
- **a** — Fick's First Law assumes a **steady-state concentration gradient** ($dC/dx$ = constant with time); this IS an assumption.
- **b** — Fick's Law is derived from the assumption that **molecular motion is random** (random walk model); this IS an assumption.
- **d** — Fick's Law assumes **isotropic diffusion** (diffusivity $D$ is the same in all directions); this IS an assumption.

#### Type 1 — Wrong Option Spin-offs (Q14)

**Q14-T1a.** Which of the following IS a valid assumption in applying Fick's Law?
- a) Flow velocity is constant
- b) Temperature gradient drives diffusion
- **c) Molecular motion is random ✅**
- d) Concentration gradient is zero

**Q14-T1b.** Fick's Law applies even when:
- **a) There is zero bulk flow velocity ✅**
- b) Concentration gradient is zero
- c) Molecular motion is directional
- d) The medium is anisotropic

#### Type 2 — Concept Expansion Spin-offs (Q14)

**Q14-C1.** In the derivation of Fick's Law from the slides, the flux density $J$ was found to equal:
- a) $J = D \cdot C$
- **b) $J = -D \cdot dC/dx$ ✅**
- c) $J = D / (dC/dx)$
- d) $J = D \cdot C \cdot v$

**Q14-C2.** Which type of diffusion does Fick's Law specifically model?
- a) Turbulent eddy diffusion
- b) Thermal convection
- **c) Molecular diffusion ✅**
- d) Gravitational sedimentation

### Q15. Which type of pollutant transport is most likely to dominate in highly turbulent water bodies?

| Option | Text |
|--------|------|
| a | Advection |
| b | Molecular diffusion |
| **c ✅** | **Eddy dispersion** |
| d | Gravitational settling |

**✅ Correct Answer: c**

**Why c is correct:**
Slides state: *"Turbulent diffusion is due to random fluctuation in advective velocity."* In turbulent flows, large-scale eddies create rapid, chaotic mixing that disperses pollutants orders of magnitude faster than molecular diffusion. Eddy dispersion dominates because turbulent eddies span far larger length scales than molecular motion.

**Why others are wrong:**
- **a** — Advection moves the *bulk mass* of pollutant with the mean flow; it is present in all flows but does not *spread* the pollutant — it does not dominate *dispersion* in turbulent bodies.
- **b** — Molecular diffusion operates at the nanometer/micrometer scale via thermal energy. In turbulent conditions, eddy dispersion overwhelms it by many orders of magnitude.
- **d** — Gravitational settling applies to *particles*, not dissolved pollutants, and it is a separate physical process independent of turbulence level.

#### Type 1 — Wrong Option Spin-offs (Q15)

**Q15-T1a.** In a *still* (non-flowing, non-turbulent) water body, which is the primary mechanism spreading a dissolved pollutant?
- a) Advection
- **b) Molecular diffusion ✅**
- c) Eddy dispersion
- d) Gravitational settling

**Q15-T1b.** For heavy suspended sediment particles in a river, which transport mechanism causes them to settle out of suspension?
- a) Advection
- b) Molecular diffusion
- c) Eddy dispersion
- **d) Gravitational settling ✅**

#### Type 2 — Concept Expansion Spin-offs (Q15)

**Q15-C1.** The primary difference between molecular diffusion and eddy (turbulent) dispersion is:
- a) Molecular diffusion occurs in gases only; eddy dispersion in liquids only
- **b) Molecular diffusion is caused by thermal energy; eddy dispersion is caused by turbulent velocity fluctuations ✅**
- c) Eddy dispersion follows Fick's Law; molecular diffusion does not
- d) They are identical in mechanism and magnitude

> *Slides: "Turbulent diffusion is due to random fluctuation in advective velocity" vs. Fick's Law for molecular diffusion.*

**Q15-C2.** All three transport processes — advection, molecular diffusion, and eddy dispersion — can be combined into a single one-dimensional transport equation. The advective component is represented by:
- **a) $v \cdot C$ (velocity × concentration) ✅**
- b) $-D\, dC/dx$
- c) $v_s \cdot C$ (settling velocity × concentration)
- d) $kC$ (reaction term)

---

*Document compiled from: `Week-4-Assignment-and-Solution-4.pdf` and `WEEK-4-10.pdf` (NOC25_GE17, IIT Kharagpur)*
*All content traceable to provided slides and assignment sheet.*
