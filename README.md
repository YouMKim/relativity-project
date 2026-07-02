# relativity-project

A relativistic physics engine in Python, built from first principles and verified against analytical solutions - with a web visualizer, an MCP server, and (someday) a roguelite game on top.

**Status: early.**
Phase 1 (Newtonian orbital mechanics) is in progress; no physics code is committed yet.
The plan lives in [PLAN.md](PLAN.md).

## The headline goal

Reproduce Mercury's perihelion precession (~43 arcseconds/century, the classic test of general relativity) in an engine built and verified from scratch - then let you play with it in the browser, and let LLMs use it over MCP.

## Roadmap

| Milestone | What ships | Status |
|---|---|---|
| M1 | Two-body engine + conservation-law verification harness | in progress |
| M2 | Deployed interactive orbit visualizer | not started |
| M3 | Mercury perihelion precession + time dilation, verified three ways | not started |
| M4 | MCP server exposing the engine to LLMs | not started |

Parked dream: a roguelite space game built on the engine.

## Layout

- `physics/` - the core engine (`relativity_physics`), the heart of the project
- `web/` - the visualizer (M2)
- `mcp/` - the MCP server (M4)
- `devlog/` - human-written reflections on the process
- `tutor-log/` - records of the physics lessons behind the code

## The learning experiment

This is also an experiment in learning *with* AI without letting it learn *instead of* me.
The physics is derived by hand in tutored lessons before any code is written; during M1 even the scaffolding, tests, and CI are hand-written, with AI reviewing rather than generating.
`devlog/` and `tutor-log/` document that honestly, unpolished.
