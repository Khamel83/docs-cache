# Docs Cache — Shared Documentation Cache for AI Agents

A centralized cache of external service documentation. Use this **before** reaching for WebSearch.

## Quick Start

```bash
# Add cache to your PATH
export PATH="$PATH:$HOME/github/docs-cache/bin"

# From any project, link cached docs
cd /your/project
docs-link add polymarket convex tailscale

# View what's linked
docs-link list

# See all available cached docs
docs-link available
```

## How to Use

### Option 1: Using docs-link (Recommended)

```bash
# Add docs to your current project
docs-link add <name>...

# List linked docs
docs-link list

# Remove a link
docs-link remove <name>

# Show available cached docs
docs-link available
```

Links are created in `docs/external/<name>` pointing to the central cache.

### Option 2: Direct Reference

Add this line to any project's `CLAUDE.md`:

```markdown
~/.claude/rules/docs-cache-pattern.md
```

Agents will now:
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

## docs-link CLI

The `docs-link` command manages symlinks between the central cache and your projects.

**Commands:**

| Command | Description |
|---------|-------------|
| `add <name>...` | Add symlinks to current project |
| `list` | Show what's linked in this project |
| `remove <name>` | Remove a symlink |
| `available` | Show all cached docs available to link |
| `sync` | Update all symlinks (if cache moved) |

**Setup:**

```bash
# Add to PATH (put in ~/.bashrc or ~/.zshrc)
export PATH="$PATH:$HOME/github/docs-cache/bin"
```

**Manifest File:**

Each project gets `.docs-links.json` tracking linked docs:

```json
{
  "cache_path": "/home/ubuntu/github/docs-cache/docs/cache",
  "links": {
    "polymarket": "services/polymarket",
    "convex": "tools/convex"
  },
  "updated": "2026-02-08T12:00:00Z"
}
```

## Structure

```
docs-cache/
├── bin/
│   └── docs-link             # CLI tool for linking docs to projects
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
