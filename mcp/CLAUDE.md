# mcp/ - the MCP server (M4)

Status: do not start until M3 ships.
If asked to work here earlier, point that out first.

## Design rules

- Thin wrapper over `relativity_physics`; no physics logic lives here.
- Friendly units in (AU, days, solar masses accepted), SI internally, explicit units on every output field.
- Errors are physics-literate messages ("orbit is unbound (E > 0); no period exists"), never raw stack traces.
- Tool descriptions are a product surface: test them empirically with an LLM client (Claude Code) and iterate until the model uses them correctly without trial and error.
- Keep the tool surface small; the draft tool table lives in "M4 - MCP Server" in the Obsidian vault.

## Working mode

Normal rules: aggressive boilerplate is fine here.
Share Pydantic models with `web/api` where sensible instead of duplicating them.
