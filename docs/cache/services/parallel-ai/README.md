# Parallel AI Search API

> Cached: 2026-04-09 — **verify against live docs**: https://docs.parallel.ai

## Balance/Usage Check

**Rate-limit headers returned on every response**:

| Header | Description |
|--------|-------------|
| `X-RateLimit-Remaining-Requests` | Remaining requests |
| `X-RateLimit-Limit-Requests` | Request limit |

HTTP 402 = insufficient credits.

## Search Endpoint

`POST https://api.parallel.ai/v1beta/search`

Headers:
```
Content-Type: application/json
x-api-key: <API_KEY>
parallel-beta: search-extract-2025-10-10
```

Body:
```json
{
  "objective": "search goal",
  "search_queries": ["query"],
  "max_results": 10
}
```

## Free Tier

4,000 one-time signup credits.

## Related

- [Tavily](../tavily/) — alternative with usage API
- [Exa](../exa/) — alternative search provider
