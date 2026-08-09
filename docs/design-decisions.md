# Engineering Design Decisions

This document records the engineering calculations and design decisions used during the development of the propulsion system.

The calculations represent theoretical design estimates used for component selection. Actual flight performance was subsequently evaluated through ground and flight testing.

---

## 1. Propulsion Design Requirements

The propulsion system was designed around an estimated Maximum Take-Off Weight (MTOW) of:

**MTOW = 1.7 kg**

A design thrust-to-weight ratio of:

**T/W = 2.15**

was selected to provide sufficient thrust margin for a multirotor platform carrying additional equipment and payload.

---

## 2. Required Total Thrust

The required total thrust was calculated as:

**T = MTOW × (T/W)**

Therefore:

**T = 1.7 × 2.15**

**T = 3.655 kgf**

For a four-motor quadcopter:

**Thrust per motor = 3.655 / 4**

**= 0.91375 kgf ≈ 1 kgf per motor**

Therefore, the propulsion system was designed around approximately **1 kgf of required thrust per motor**.

### Calculation

![Thrust-to-weight ratio calculation](calculations/01-thrust-to-weight-ratio.png)

---

## 3. Propeller Disk Area

The required propeller disk area was estimated using the thrust relationship:

**T = 1/2 × ρ × (Ve² − Vi²) × Ap**

where:

- ρ = 1.225 kg/m³
- Ve = 16 m/s
- Vi = 3 m/s
- T = 9.1375 N

Substitution gives:

**Ap = 0.060398 m²**

### Calculation

![Propeller area calculation](calculations/02-propeller-area.png)

---

## 4. Propeller Diameter

Using the calculated propeller disk area:

**A = πr²**

The required radius was calculated as:

**r = √(A/π)**

which gives:

**r = 0.1386 m**

or approximately:

**r = 5.4 inches**

Therefore:

**D = 2r = 10.8 inches**

A commercially available **10-inch propeller** was selected as the nearest practical standard size.

### Calculation

![Propeller radius and diameter calculation](calculations/03-propeller-radius-diameter.png)

---

## 5. Propeller Pitch Selection

The pitch-to-diameter ratio was selected as:

**P/D = 0.4**

Using the calculated diameter:

**D = 10.8 inches**

Therefore:

**P = 10.8 × 0.4**

**P = 4.32 inches**

A standard **4.5-inch pitch** was selected as the nearest practical option.

The resulting selected propeller specification was:

**10 × 4.5 inches**

### Calculation

![Propeller pitch calculation](calculations/05-propeller-pitch.png)

---

## 6. Lift Coefficient Estimate

The lift coefficient was estimated using:

**L = 1/2 × ρ × Ve² × Ap × Cl**

Rearranging:

**Cl = L / (1/2 × ρ × Ve² × Ap)**

Using the calculated parameters gave:

**Cl ≈ 0.96**

This calculation was used as part of the preliminary aerodynamic assessment of the selected propeller geometry.

### Calculation

![Lift coefficient calculation](calculations/04-lift-coefficient.png)

---

## 7. Hover RPM Estimate

The required propeller rotational speed was estimated using the RPM-based thrust relationship.

The resulting calculated value was:

**RPM ≈ 6069 RPM**

This represents a **theoretical hover RPM estimate** under the assumptions used in the calculation. It should not be interpreted as a directly measured flight value.

### Calculation

![Hover RPM calculation](calculations/06-hover-rpm.png)

---

## 8. Final Propulsion Selection

Based on the preceding calculations, the prototype propulsion system was configured with:

| Component | Selected Specification |
|---|---|
| Frame | S500 |
| Motor | 2212 920KV brushless motor |
| Propeller | 10 × 4.5 inch |
| ESC | Velox 50A 4-in-1 |
| Battery | 4S 6200mAh LiPo |
| Number of motors | 4 |
| Estimated MTOW | 1.7 kg |
| Design thrust-to-weight ratio | 2.15 |
| Required total thrust | 3.655 kgf |
| Required thrust per motor | 0.91375 kgf |

---

## 9. Engineering Validation

The calculations above were used for preliminary system sizing and component selection.

The actual prototype was then assembled and subjected to:

- Motor and ESC testing
- Flight-controller configuration
- Propulsion-system testing
- Ground testing
- Initial flight testing
- Troubleshooting of motor and ESC behaviour
- Flight validation

The theoretical calculations therefore served as the **design basis**, while physical testing was used to evaluate the behaviour of the completed system.

---

## 10. Design Approach

The propulsion system was not selected solely from commercially available components. The selection process began with system requirements and theoretical calculations, followed by practical component selection and physical validation.

The overall engineering sequence was:

**Requirement → Calculation → Component Selection → Integration → Ground Testing → Flight Testing → Troubleshooting**
