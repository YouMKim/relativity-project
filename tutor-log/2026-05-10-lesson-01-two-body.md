# Lesson 1 — The Two-Body Problem (Newtonian)

**Date:** 2026-05-10
**Phase:** 1 (Newtonian orbital mechanics) — first session
**Status:** physics covered, no code yet

---

## What we covered

### The arc we agreed on
1. Two-body problem — setup + conservation laws  ← today
2. Kepler orbits — analytical solutions to verify against
3. Numerical integration — Euler, RK4, symplectic (Verlet)
4. First build: two-body simulator + verification harness
5. N-body, perturbations, bridge to GR

### Lesson 1 content

**Setup.** Two point masses m₁, m₂ at positions r₁, r₂ in an inertial frame, interacting only via Newtonian gravity:

```
F₁ = G m₁ m₂ (r₂ - r₁) / |r₂ - r₁|³
F₂ = -F₁                                 (Newton's 3rd)
```

Two coupled second-order vector ODEs, 12 scalar ODEs total in 3D.

**Reduction to one-body.** Change coordinates to:
- Center of mass R = (m₁ r₁ + m₂ r₂) / (m₁ + m₂)
- Relative position r = r₂ - r₁

Adding the EoMs gives `(m₁+m₂) R̈ = 0` → CoM moves uniformly, drop it.
Subtracting (after dividing by mass) gives:

```
r̈ = -G(m₁+m₂) r / |r|³
```

One vector ODE. Effectively a single particle orbiting a fixed center.

**Conservation laws** (the real point of the lesson):

- **Angular momentum.** r × r̈ = 0 ⟹ L = r × ṙ is constant.
  - Direction fixed ⟹ motion is planar (2D problem, not 3D)
  - Magnitude fixed ⟹ r²θ̇ = const ⟹ Kepler's 2nd law (equal areas)
- **Energy.** ṙ · EoM integrates to:
  ```
  E = ½|ṙ|² - G(m₁+m₂)/|r|  is constant
  ```
  - E < 0: bound ellipse
  - E = 0: parabolic escape
  - E > 0: hyperbolic flyby

**Payoff before writing any code:**
- Problem is 2D
- E and |L| are correctness checks for any integrator
- Orbit shape is known qualitatively from E alone

### What we'll build first
A 2D two-body integrator with a conservation-law verification harness:

```
physics/
  src/relativity_physics/
    twobody.py
    conserved.py
  tests/
    test_conserved.py    # |ΔE/E| < 1e-6 over N orbits
    test_kepler.py       # (after Lesson 2)
```

Integrator recommendation: **velocity-Verlet** (symplectic, conserves energy over long runs) rather than RK4. Reasoning deferred to Lesson 3.

---

## Open questions / where we left off

Awaiting answers from me (the human) on:
1. Is the two-body → one-body reduction solid, or revisit?
2. Want a rigorous derivation of energy conservation or is the sketch enough?
3. Comfort level with vector calc (∇, ×, ·-with-derivatives) — for calibration

---

## Reflection prompts (for me to fill in later)

- What worked well in this session?
- What did I delegate to Claude that I should have worked out myself?
- What did I work out myself that I could have safely delegated?
- Anything surprising?
