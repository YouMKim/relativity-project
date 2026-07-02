# Project Plan

Re-scoped 2026-07-02.
Priorities: (1) genuine learning, (2) resume/portfolio value.
The relativistic physics engine is the core.
Everything else is a satellite whose job is to showcase the engine.

## Milestones

Every milestone must end with something demoable and verified, so there is always a "current best artifact" to show.

### M1 - Two-body engine + verification harness

Newtonian two-body simulator using velocity-Verlet (symplectic integrator).
Verification harness first-class from day one: energy and angular-momentum conservation tests (target |dE/E| < 1e-6 over many orbits), then checks against analytical Kepler orbits.
Project tooling lands here too: uv-managed package, pytest, CI.
Tutor Lessons 2 (Kepler orbits) and 3 (integrators: Euler vs RK4 vs symplectic) happen alongside the build, and each lesson ends with code written the same week.

### M2 - Deployed orbit visualizer

One interactive web page running the M1 engine (FastAPI backend; start with a simple 2D canvas, upgrade to Three.js later).
This is the first shareable portfolio link.

### M3 - The relativity payoff

Post-Newtonian corrections to the engine.
Reproduce Mercury's perihelion precession (~43 arcsec/century) and show Newtonian vs corrected side by side.
Verify against the analytic formula, an independent numerical oracle (e.g. REBOUND + REBOUNDx's GR force), and published values; EinsteinPy serves as a qualitative strong-field cross-check.
This is the portfolio headline: a physics result a reviewer can check.

### M4 - MCP server

Expose the engine to LLMs via an MCP server.
Small scope once the library exists, and directly demonstrates modern AI-tooling skills.

### Parked

Godot roguelite game: the long-term dream, intentionally parked.
Revisit only after M1-M4 are done; it builds on top of the engine.

## Where the detail lives

This file is the short source of truth.
The detailed curriculum, background-knowledge modules, and per-milestone implementation notes live in the Obsidian vault at `~/Documents/Obsidian Vault/Relativity Project/` (start at `00 Home.md`).

## Working agreements

Tutor mode for physics: derive step by step, build intuition, then code it.
Lessons never float free of code; "learn it, build it, verify it" within the same week.
The devlog and tutor-log stay human-written.
