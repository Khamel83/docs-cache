# Docs Cache — Shared Documentation Cache for AI Agents

A centralized cache of external service documentation. Use this **before** reaching for WebSearch.

## How to Use

Add this line to any project's `CLAUDE.md`:

```markdown
~/.claude/rules/docs-cache-pattern.md
```

That's it. Agents will now:
1. Check the cache first
2. Use `/freesearch` for research (saves WebSearch quota)
3. Only WebSearch for time-sensitive facts

## What's Cached

| Category | Examples |
|----------|----------|
| `tools/` | Convex, Supabase, Vercel, Traefik, n8n |
| `python/` | FastAPI, HTTPX, Poetry, Typer |
| `javascript/` | Next.js |
| `services/` | Docker, Tailscale |

See `docs/cache/.index.md` for full catalog.

## Adding New Docs

When you fetch new documentation:

1. Save to `docs/cache/{category}/{name}/README.md`
2. Add entry to `docs/cache/.index.md`
3. Commit and push

```bash
git add docs/cache/
git commit -m "Add cache: {name}"
git push
```

## Why

- **Speed** — Local files are instant
- **Cost** — Saves WebSearch API quota
- **Accuracy** — Cached docs don't drift
- **Reliability** — Works offline

## Structure

```
docs-cache/
├── CLAUDE.md                 # Project instructions
├── docs/
│   ├── cache/
│   │   ├── .index.md         # Catalog of cached docs
│   │   ├── tools/            # Frameworks & libraries
│   │   ├── python/           # Python packages
│   │   ├── javascript/       # JS/TS frameworks
│   │   └── services/         # External services
│   └── research/             # Research findings
└── README.md                 # This file
```

## Setup

```bash
# Copy env template and add your keys
cp .env.example .env
# Edit .env with your EXA_API_KEY and JINA_API_KEY
```

The `.env` file is gitignored and contains:
- `EXA_API_KEY` — For `/freesearch` (Exa API, zero-token research)
- `JINA_API_KEY` — For web reading/summarization

## Global Rule

The full pattern lives at `~/.claude/rules/docs-cache-pattern.md` and includes:

- WebSearch gate (check cache, files, training data first)
- Freesearch for research
- Cache-first workflow

Update that file to change behavior across all projects.
