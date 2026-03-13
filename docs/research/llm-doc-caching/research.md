# LLM Agent Documentation Caching Research

*Generated: 2026-02-08*

## Executive Summary

Several patterns and tools exist for self-upcreasing local documentation caches for AI agents. The main approaches are:

1. **Behavior caching** - Agent learns from its own tool-calling patterns
2. **RAG with caching** - Local vector DB with semantic search + cache layer
3. **Self-updating docs** - Agents that monitor codebases and update docs automatically
4. **Tool result caching** - Cache API/tool responses for reuse

## Current Approaches

### 1. Muscle-Mem (Behavior Cache)
- **Project**: [pig-dot-dev/muscle-mem](https://github.com/pig-dot-dev/muscle-mem)
- **Pattern**: Records agent's tool-calling patterns as it solves tasks
- **Mechanism**: Deterministically replays learned trajectories when encountering similar tasks
- **Use case**: When your agent repeatedly solves similar types of problems

### 2. RAG with Local Vector DB
- **Pattern**: Ingest docs → vector embeddings → local search → LLM retrieval
- **Benefits**: Privacy, low latency, no API costs for retrieval
- **Tools**: Elasticsearch, LocalAI, LangChain
- **Reference**: [Local RAG Personal Knowledge Assistant](https://www.elastic.co/search-labs/blog/local-rag-personal-knowlege-assistant-localai-elasticsearch)

### 3. Self-Updating Documentation
- **Project**: [Mintlify Autopilot](https://www.mintlify.com/blog/autopilot)
- **Pattern**: Agent monitors codebase → identifies drift → suggests doc updates
- **Solves**: Documentation drift (code changes, docs don't)

### 4. Tool Result Caching
- **Paper**: [TOOL CACHE AGENT](https://openreview.net/pdf/05f7fe080121ee4044c4899cf9b69ac21b7738ba.pdf)
- **Pattern**: Cache tool call results, reuse for similar queries
- **Benefit**: Faster responses, reduced API calls

## Tools & Projects

| Project | Type | Link |
|---------|------|------|
| Muscle-Mem | Behavior cache | https://github.com/pig-dot-dev/muscle-mem |
| Mintlify Autopilot | Self-updating docs | https://www.mintlify.com/blog/autopilot |
| Firecrawl | Doc scraping | https://www.firecrawl.dev/blog/build-documentation-agent-langgraph-firecrawl |
| Elastic Local RAG | Local RAG stack | https://www.elastic.co/search-labs/blog/local-rag-personal-knowlege-assistant-localai-elasticsearch |
| LangGraph RAG Agent | Doc agent framework | https://ai-sdk.dev/cookbook/guides/rag-chatbot |

## Implementation Pattern for Your Use Case

Based on your requirements (local-first, slow cadence updates, external service docs):

```
┌─────────────────────────────────────────────────────────────┐
│                     Agent Request                           │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │ Check Local Cache    │
              │ docs/cache/<name>/   │
              └──────────┬───────────┘
                         │
            ┌────────────┴────────────┐
            │                         │
         FOUND                    NOT FOUND
            │                         │
            ▼                         ▼
    ┌──────────────┐      ┌─────────────────────┐
    │ Return Cached │      │ Fetch from URL      │
    │ Content      │      │ (webReader MCP)     │
    └──────────────┘      └──────────┬──────────┘
                                     │
                                     ▼
                          ┌─────────────────────┐
                          │ Save to Cache       │
                          │ docs/cache/<name>/  │
                          └─────────────────────┘
```

### Update Cadence Strategies

1. **Time-based** - Check docs URL if cache > N days old
2. **Hash-based** - Store content hash, refetch if changed
3. **Manual trigger** - Update only when explicitly requested
4. **Staleness metadata** - Store `last_updated` timestamp in `.index.md`

### File Structure

```
docs/cache/
├── .index.md              # Catalog of cached docs with timestamps
├── convex/
│   └── README.md          # Cached Convex docs
├── nextjs/
│   └── README.md          # Cached Next.js docs
└── tailscale/
    └── README.md          # Cached Tailscale docs
```

### .index.md Format

```markdown
# Documentation Cache Index

| Name | URL | Last Updated | Size |
|------|-----|--------------|------|
| convex | https://docs.convex.dev | 2026-02-01 | 245KB |
| nextjs | https://nextjs.org/docs | 2026-01-28 | 512KB |
| tailscale | https://tailscale.com/kb | 2026-02-05 | 128KB |
```

## Code Examples

### Simple Python Pattern

```python
import os
import time
from datetime import datetime, timedelta
from pathlib import Path

CACHE_DIR = Path("docs/cache")
STALE_DAYS = 30  # Update monthly

def get_docs(name: str, url: str) -> str:
    """Get docs from cache or fetch if stale/missing."""
    cache_path = CACHE_DIR / name / "README.md"
    index_path = CACHE_DIR / ".index.md"

    # Check cache exists and is fresh
    if cache_path.exists():
        cache_age = datetime.now() - datetime.fromtimestamp(cache_path.stat().st_mtime)
        if cache_age < timedelta(days=STALE_DAYS):
            return cache_path.read_text()

    # Fetch and cache
    content = fetch_from_url(url)  # Use webReader MCP here
    cache_path.parent.mkdir(parents=True, exist_ok=True)
    cache_path.write_text(content)
    update_index(name, url)
    return content

def update_index(name: str, url: str):
    """Update the cache index with new entry."""
    # Append to .index.md
    ...
```

### MCP Tool Integration

Use the existing `webReader` MCP:
- `@mcp__web_reader__webReader` with URL parameter
- Already supports markdown conversion
- Returns formatted content ready to cache

## Recommendations

1. **Start simple**: File-based cache with time-based staleness
2. **Use existing tools**: webReader MCP for fetching, git for versioning
3. **Index file**: Maintain `.index.md` for quick lookup
4. **Slow cadence**: 30-day staleness is reasonable for most docs
5. **Version control**: Git tracks changes, easy to rollback

## Resources

- [Building RAG Locally: From Ingestion to Caching](https://www.linkedin.com/pulse/building-rag-locally-from-ingestion-caching-before-agents-rajawat-kc04c)
- [Local RAG Personal Knowledge Assistant](https://www.elastic.co/search-labs/blog/local-rag-personal-knowlege-assistant-localai-elasticsearch)
- [Muscle-Mem GitHub](https://github.com/pig-dot-dev/muscle-mem)
- [Mintlify Autopilot - Self-Updating Docs](https://www.mintlify.com/blog/autopilot)
- [Turn Any Documentation Site Into an AI Agent](https://www.firecrawl.dev/blog/build-documentation-agent-langgraph-firecrawl)
- [Advanced RAG Techniques](https://neo4j.com/blog/genai/advanced-rag-techniques/)
