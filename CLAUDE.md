# Project Context

## What this is
A monorepo for a long-term learning + portfolio project.
The core artifact is a relativistic physics simulation library (Python) - everything else exists to showcase it.
Satellites, in priority order: an interactive web showcase (FastAPI + React + Three.js), an MCP server exposing the physics library to LLMs, and (parked for now) a roguelite game (Godot 4).
See PLAN.md for milestones.
Detailed curriculum and implementation notes live in the Obsidian vault: `~/Documents/Obsidian Vault/Relativity Project/` (start at `00 Home.md`).

## What this isn't (yet)
- A finished anything. We're building in phases.
- Production code with strict SLAs. This is a learning + portfolio project.

## Repo map
- `physics/` - the core engine package; see `physics/CLAUDE.md`. Built during M1.
- `web/` - M2 orbit visualizer; see `web/CLAUDE.md`. Empty until M1 is tagged.
- `mcp/` - M4 MCP server; see `mcp/CLAUDE.md`. Empty until M3 ships.
- `devlog/` - human-written reflections. AI must never write or edit anything here.
- `tutor-log/` - lesson records. Human-curated; AI may draft a lesson summary only when asked at the end of a lesson.
- `PLAN.md` - the milestone plan (short source of truth; detail lives in the Obsidian vault).

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
- Exception during M1 only: I hand-write the scaffolding, tests, and CI to learn Python project construction; review my work instead of generating it (see "M1 Implementation Plan" in the Obsidian vault).
- When you're uncertain about a physics result, say so explicitly.
  Verify against EinsteinPy or known analytical solutions when possible.
- Keep code clear over clever. This is a learning project - readability
  beats one-liners.

# General Guidelines

- Never use the em dash "—". Use plain dash "-" instead.
- When writing commit messages, NEVER auto-add your agent name as co-author.
- Never manually modify CHANGELOG.md files or any files that are marked as auto-generated.
- When writing or substantially editing long Markdown files, put each full sentence on its own line.
  Preserve normal Markdown structure, but avoid wrapping multiple sentences onto one physical line.
- When making technical decisions, do not give much weight to development cost.
  Instead, prefer quality, simplicity, robustness, scalability, and long term maintainability.
- When doing bug fixes, always start with reproducing the bug in an E2E setting as closely aligned with how an end user would experience it.
  This makes sure you find the real problem so your fix will actually solve it.
- When end-to-end testing a product, be picky about the UI you see and be obsessed with pixel perfection.
  If something clearly looks off, even if it is not directly related to what you are doing, try to get it fixed along the way.
- Apply that same high standard to engineering excellence: lint, test failures, and test flakiness.
  If you see one, even if it is not caused by what you are working on right now, still get it fixed.


## Current phase
Phase 1: Newtonian orbital mechanics (Lesson 1 done 2026-05-10; plan re-scoped 2026-07-02).
Current milestone M1: two-body integrator + conservation-law verification harness (see PLAN.md).
Next action: tutor Lesson 2 (Kepler orbits), then start building M1.