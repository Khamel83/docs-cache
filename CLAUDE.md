# Local-First Documentation Cache

This repository maintains a local cache of external service documentation. **Always check the cache before using WebSearch/WebFetch.**

## Search Order (MUST follow)

Before WebSearch, go through this order:

1. **Docs cache** → `cat docs/cache/.index.md`
2. **`/freesearch`** → Exa API (zero token cost)
3. **Training data** → Most docs/libs already known
4. **WebSearch** → Last resort only

**WebSearch only for:**
- Time-sensitive facts (current date, latest version)
- Confirmation when training data conflicts

**WebReader MCP** → Use only for caching new docs, not for research.

## Quick Check

```bash
# See what's cached
cat docs/cache/.index.md

# List cached services
ls docs/cache/*/
```

## Workflow

1. **Check local cache** — Read `docs/cache/.index.md` to see if docs exist
2. **Use cached** — If present, read from `docs/cache/{category}/{name}/README.md`
3. **Fetch if missing** — Use webReader MCP: `@mcp__web_reader__webReader{"url": "..."}`
4. **Save to cache** — Write to `docs/cache/{category}/{name}/README.md`
5. **Update index** — Add entry to `docs/cache/.index.md`
6. **Commit changes** — `git add docs/cache/ && git commit -m "Add cache: {name}" && git push`

## Cached Categories

- `tools/` — Developer tools and frameworks
- `python/` — Python libraries
- `javascript/` — JavaScript/TypeScript frameworks
- `services/` — External services (Docker, Tailscale, etc.)

## Example

```python
# Agent sees: "How do I use Convex mutations?"
# Agent checks: docs/cache/.index.md → finds "convex"
# Agent reads: docs/cache/tools/convex/README.md
# Agent answers: Uses cached content
```

## Related

- Global pattern: `~/.claude/rules/docs-cache-pattern.md`
- Research: `docs/research/llm-doc-caching/research.md`

## External Documentation

This project has links to cached external documentation:

```bash
# View linked docs
ls docs/external/

# See available cached docs
docs-link available
```

Cached docs are managed via the central cache at ~/github/docs-cache/

<!--
  ONE-SHOT Heartbeat Metadata
  oneshot:last-check: 2026-02-13
  oneshot:machine: instance-first
-->
