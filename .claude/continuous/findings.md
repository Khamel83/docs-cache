# Findings: Local-First Documentation Cache Pattern

**Created:** 2026-02-08

## Research Summary

Completed web search on LLM agent documentation caching patterns. Key findings:

- **Muscle-Mem**: Behavior cache for agents ([GitHub](https://github.com/pig-dot-dev/muscle-mem))
- **Local RAG**: Vector DB + embeddings for local retrieval ([Elastic](https://www.elastic.co/search-labs/blog/local-rag-personal-knowlege-assistant-localai-elasticsearch))
- **Mintlify Autopilot**: Self-updating docs that monitor codebase ([Blog](https://www.mintlify.com/blog/autopilot))

Full research: `docs/research/llm-doc-caching/research.md`

## Existing Structure Discovery

### docs-cache Repo
- Has `docs/cache/` with existing content
- Structure: `docs/cache/{category}/{name}/README.md`
- Categories: `go`, `javascript`, `python`, `rust`, `services`, `tools`
- No `.index.md` exists yet

### Global Rules Conflict
- `~/.claude/rules/docs-first.md` references `docs/external/`
- This repo uses `docs/cache/`
- Need to harmonize or make pattern flexible

### oneshot Repo
- Has `CLAUDE.md` at root
- Has `.claude/rules/`, `.claude/skills/`
- Has continuous planning already

## Discovered Issues

1. **Path mismatch**: Global rule says `docs/external/`, this repo uses `docs/cache/`
2. **Missing metadata**: Cached files have `Title:` and `URL Source:` in content but no index
3. **No staleness check**: No mechanism to determine if cache is old

## Solutions Identified

1. **Flexible pattern**: Check both `docs/cache/` and `docs/external/`
2. **Parse existing files**: Extract metadata from README.md headers
3. **Date-based staleness**: Use file mtime or embedded date

## Code Snippets

### Extract metadata from existing cached files
```bash
for file in docs/cache/*/*/README.md; do
    echo "File: $file"
    head -10 "$file" | grep -E "Title:|URL Source:"
done
```

### Check staleness
```python
import os
from datetime import datetime, timedelta
cache_path = "docs/cache/nextjs/README.md"
mtime = datetime.fromtimestamp(os.path.getmtime(cache_path))
stale = (datetime.now() - mtime) > timedelta(days=30)
```

## Open Questions

- Should we update global `docs-first.md` to check both paths?
- Should oneshot have its own docs cache or reference this one?

## References

- Research output: `docs/research/llm-doc-caching/research.md`
- Global docs-first rule: `~/.claude/rules/docs-first.md`
- oneshot CLAUDE.md: `~/github/oneshot/CLAUDE.md`
