# Unit 6: COCOMO & Estimation Calculations

## Basic COCOMO Formula

E = a × (KLOC)^b  [Person-Months]
T = c × (E)^d     [Months]
N = E / T         [Team Size]

## Coefficient Table (MEMORIZE THIS!)

| Mode | a | b | c | d | Description |
|------|---|---|---|---|-------------|
| **Organic** | 2.4 | 1.05 | 2.5 | 0.38 | Small team, familiar problem |
| **Semi-detached** | 3.0 | 1.12 | 2.5 | 0.35 | Medium size, mixed experience |
| **Embedded** | 3.6 | 1.20 | 2.5 | 0.32 | Tight constraints, complex |

## Effort/Time Distribution (μp and τp)

| Phase | μp (Effort %) | τp (Time %) |
|-------|--------------|-------------|
| **Design** | 16-18% | 36-42% |
| **Coding** | 36-68% | 30-48% |
| **Testing** | 18-28% | 18-34% |

## Intermediate COCOMO

E = E_nominal × EAF

Where EAF = Product of 15 cost driver multipliers

**Example:** If RELY=1.15, DATA=0.94, CPLX=1.30
EAF = 1.15 × 0.94 × 1.30 = 1.41

## Example Problem

**Given:** 32 KLOC, Organic mode
**Find:** E, T, N

**Solution:**
- E = 2.4 × (32)^1.05 = 2.4 × 33.98 = 81.6 PM
- T = 2.5 × (81.6)^0.38 = 2.5 × 5.5 = 13.8 months
- N = 81.6 / 13.8 = 5.9 ≈ 6 people
