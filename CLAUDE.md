# Local-First Documentation Cache

This repository maintains a local cache of external service documentation. **Always check the cache before using WebSearch/WebFetch.**

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
