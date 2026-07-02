# physics/ - the core engine

The `relativity_physics` package.
This is the heart of the whole project; everything else in the monorepo exists to showcase this library.

## Working mode (IMPORTANT, until M1 is tagged)

The user is hand-writing all scaffolding, config, tests, and CI in this package to learn Python project construction.
Review their work, point at docs, explain errors and tradeoffs - do NOT generate these files unless explicitly asked.
This deliberately overrides the root "be aggressive with boilerplate" rule; it expires when M1 (v0.1.0) is tagged.
Physics code follows tutor mode: derive with the user on paper first, then they write the code.

## Design rules

- SI units internally, always. Unit conversion happens in `web/` and `mcp/`, never here. Docstrings state units for every physical quantity.
- Pure functions over plain data: dataclass states in, NumPy arrays through, no hidden state, I/O stays out of this package.
- The acceleration seam is velocity-aware: `accel(r, v)` even where `v` is unused (Newtonian), because the M3 relativistic correction needs it.
- Name things for what they are now: `twobody`, not `nbody`.
- Type hints required on the public API.

## Testing rules

- Every numerical claim needs an oracle: analytical solution, hand computation, or independent implementation. Test the oracle itself before trusting it.
- Tolerances are derived (integrator order + timestep + float floor) and justified in a comment. No magic numbers.
- hypothesis property tests for invariants; example tests for known values; expected-failure tests for documented failure modes (e.g. Euler's energy growth).
- Never leave the suite red.

## Where the detail lives

Session-by-session build plan: "M1 Implementation Plan" in the Obsidian vault (`~/Documents/Obsidian Vault/Relativity Project/Project/`).
Design rationale: the "Architecture" note in the same folder.
