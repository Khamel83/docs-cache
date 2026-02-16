# Documentation Cache

Offline cache of external documentation for popular libraries, frameworks, and services. Designed to give LLMs and developers fast, local access to reference documentation without requiring internet lookups.

## Purpose

This repository stores markdown-converted copies of official documentation. It is useful when:

- An LLM needs to reference library docs during code generation or review
- You want offline access to documentation
- You need a stable snapshot of docs at a known point in time

## How to Find Documentation

### Directory structure

All cached documentation lives under `cache/` organized by category:

```
cache/
  python/          # Python packages (fastapi, httpx, pandas, etc.)
  javascript/      # JavaScript/Node frameworks (nextjs, etc.)
  services/        # Infrastructure and hosted services (docker, tailscale, etc.)
  tools/           # Platform tools and SaaS products (convex, supabase, vercel, etc.)
```

Each tool has its own subdirectory containing a single `README.md`:

```
cache/<category>/<tool-name>/README.md
```

### Index

The [.index.md](.index.md) file lists every cached source with its:

- Tool name and file path
- Original source URL
- Cache timestamp
- Category
- Content status (ok or degraded)

### Search strategy for LLMs

1. **Check `.index.md`** first to see if the tool/library is cached and find its file path.
2. **Read the file** at `cache/<category>/<tool-name>/README.md`.
3. **If the tool is not listed**, it is not cached here. Fall back to other sources.

## Cached File Format

Every `README.md` in the cache follows this format:

```
Title: <display name>

URL Source: <original documentation URL>

Published Time: <ISO 8601 timestamp>        # optional, included when available

Markdown Content:
<full documentation body converted to markdown>
```

| Field            | Required | Description                                      |
|------------------|----------|--------------------------------------------------|
| Title            | yes      | Human-readable name of the tool or library       |
| URL Source        | yes      | URL the documentation was fetched from           |
| Published Time    | no       | Publication or last-modified timestamp if available |
| Markdown Content  | yes      | The documentation body in GitHub-flavored Markdown |

## Category Guidelines

| Category      | Use for                                                  | Examples                          |
|---------------|----------------------------------------------------------|-----------------------------------|
| `python`      | Python packages installable via pip/poetry               | fastapi, httpx, pandas, aiohttp   |
| `javascript`  | JavaScript/TypeScript packages installable via npm/yarn  | nextjs                            |
| `services`    | Infrastructure, hosting, and managed services            | docker, tailscale                 |
| `tools`       | Multi-language platforms, SaaS products, workflow tools  | convex, supabase, vercel, n8n     |

When a library exists primarily in one language ecosystem (e.g., pandas is a Python package even though it has broad use), place it under that language category.

## Content Quality

Some cached entries may contain degraded content (e.g., cookie consent pages instead of actual documentation) due to scraping limitations. These are flagged in `.index.md` with a `degraded` status. Degraded entries should not be relied upon and need re-caching.

## Adding or Updating Documentation

To add a new cached source:

1. Create the directory: `cache/<category>/<tool-name>/`
2. Add a `README.md` following the format above
3. Add an entry to `.index.md`

To update an existing entry, replace the `README.md` content and update the timestamp in `.index.md`.
