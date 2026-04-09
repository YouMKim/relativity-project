# Project Context

## What this is
A monorepo for a multi-year project: a relativistic physics
simulation library (Python), an interactive web showcase (FastAPI +
React + Three.js), a roguelite game (Godot 4), and an MCP server
exposing the physics library to LLMs.

## What this isn't (yet)
- A finished anything. We're building in phases.
- Production code with strict SLAs. This is a learning + portfolio project.

## Conventions
- Python 3.12+, managed with uv.
- All physics code uses SI units internally. Display units may vary.
- Prefer SciPy for numerical work; SymPy for symbolic derivations.
- Tests live next to code in `tests/` subdirectories.
- Type hints required on public APIs, optional internally.

## How I want to work with AI tools
- I am the architect and the physicist. You are the implementation
  partner and the tutor.
- For physics math: explain derivations step by step. Do not just
  produce final code. I want to understand, not copy.
- For boilerplate, scaffolding, glue code: be aggressive. Just do it.
- When you're uncertain about a physics result, say so explicitly.
  Verify against EinsteinPy or known analytical solutions when possible.
- Keep code clear over clever. This is a learning project — readability
  beats one-liners.

## Current phase
Phase 0: setup and foundations. No physics code yet.
Phase 1 (next): Newtonian orbital mechanics.