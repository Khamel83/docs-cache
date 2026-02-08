# Task Plan: Local-First Documentation Cache Pattern

**Created:** 2026-02-08
**Status:** In Progress
**Epic:** Docs Cache Self-Updating Pattern

## Objective

Establish a reusable pattern for AI agents to check local documentation caches before fetching external docs, with automatic cache updates on a slow cadence.

## Success Criteria

1. [ ] `CLAUDE.md` exists in `docs-cache/` repo with local-first rule
2. [ ] `docs/cache/.index.md` exists with catalog of cached docs
3. [ ] Pattern added to `oneshot` CLAUDE.md or rules
4. [ ] Both repos committed and pushed
5. [ ] Pattern is discoverable by future agents

## Phases

### Phase 1: Create Files in docs-cache Repo

**Target:** `/home/ubuntu/github/docs-cache`

| File | Content | Purpose |
|------|---------|---------|
| `CLAUDE.md` | Local-first docs rule | Project-specific instruction for agents |
| `docs/cache/.index.md` | Catalog table | Quick reference for what's cached |

**CLAUDE.md Template:**
```markdown
# Local-First Documentation

Before using WebSearch/WebFetch for external service documentation:

1. Check local cache: `ls docs/cache/` or read `docs/cache/.index.md`
2. If cached content exists, use it
3. If missing or stale (30+ days), fetch with webReader MCP
4. Save new cache to `docs/cache/<category>/<name>/README.md`
5. Update `docs/cache/.index.md` with entry
```

**docs/cache/.index.md Template:**
```markdown
# Cached Documentation Catalog

| Name | Category | URL | Cached | Source |
|------|----------|-----|--------|--------|
| nextjs | javascript | https://nextjs.org/docs | 2026-02-07 | webReader |
| convex | tools | https://docs.convex.dev | 2026-02-01 | webReader |
```

### Phase 2: Scan and Populate .index.md

**Action:** Scan existing `docs/cache/` and populate the index

```bash
find docs/cache -name "README.md" -exec head -5 {} \; | grep -E "(Title:|URL Source:)"
```

Extract: name, URL source, date from existing files.

### Phase 3: Add Pattern to oneshot Repo

**Target:** `/home/ubuntu/github/oneshot`

**Option A:** Add to existing `CLAUDE.md`
**Option B:** Add to `~/.claude/rules/docs-cache-pattern.md` (global rule)

Decision: **Option B** - Add as global rule so all projects benefit, with oneshot as reference implementation.

**File:** `~/.claude/rules/docs-cache-pattern.md`
```markdown
# Local-First Documentation Cache Pattern

When working with external service documentation:

1. Check for project-level cache: `ls docs/cache/` or `docs/external/`
2. Check global cache: `ls ~/.claude/docs/cache/`
3. Use webReader MCP to fetch if missing
4. Save with clear naming: `<category>/<name>/README.md`
5. Update index file

Reference: `~/github/docs-cache`
```

### Phase 4: Commit and Push

**docs-cache repo:**
```bash
git add CLAUDE.md docs/cache/.index.md
git commit -m "Add local-first docs cache pattern"
git push
```

**oneshot repo:**
```bash
# If modifying oneshot CLAUDE.md
cd ~/github/oneshot
git add CLAUDE.md
git commit -m "Reference docs-cache pattern"
git push
```

**Global rules (no git):**
```bash
# Rules are in ~/.claude/rules/, already tracked separately
```

## Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Index location | `docs/cache/.index.md` | Colocated with cache, easy to find |
| Update cadence | 30 days | Docs don't change often, slow refresh |
| Fetch method | webReader MCP | Already available, handles markdown conversion |
| Pattern scope | Global rule + project CLAUDE.md | Reusable across all projects |

## Dependencies

- [x] Research completed (`docs/research/llm-doc-caching/research.md`)
- [ ] Existing docs scanned for .index.md population
- [ ] oneshot repo structure reviewed

## Open Questions

None currently.

## Related

- Research: `docs/research/llm-doc-caching/research.md`
- Global rules: `~/.claude/rules/docs-first.md` (conflicting path `docs/external/` vs `docs/cache/`)
