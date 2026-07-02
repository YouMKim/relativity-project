# web/ - the orbit visualizer (M2)

Status: do not start until M1 (`physics/` v0.1.0) is tagged.
If asked to work here while M1 is unfinished, point that out first.

## Scope fences (v1)

- One page: orbit animation driven by the real `relativity_physics` engine.
- No physics in JavaScript. The engine computes, the browser draws: the API returns a full sampled trajectory, the frontend only animates it (no websockets, no streaming).
- 2D canvas first. Three.js is allowed only after the page is deployed and public.
- No accounts, no persistence.
- Design the parameter panel so the M3 "Newtonian vs GR" toggle can be added without a redesign.

## Stack

- `web/api`: FastAPI; Pydantic request/response models; one `/simulate` endpoint; CORS for the frontend origin.
- `web/frontend`: React; canvas + requestAnimationFrame; parameter sliders (masses, semi-major axis, eccentricity); live energy-drift readout.
- Deploy: API on a small host (Fly.io/Render), frontend static. Pyodide fallback exists if hosting friction stalls momentum; see the vault note before switching.

## Working mode

Normal rules apply here: be aggressive with boilerplate and glue.
The M1 hand-writing exception does NOT extend to `web/`.
Hold the UI to the pixel-perfection standard from the root guidelines; show units in the UI everywhere.

Detail: "M2 - Orbit Visualizer" in the Obsidian vault.
