# Brave Search API

> Cached: 2026-04-09 — **verify against live docs**: https://api.search.brave.com/app/documentation

## Balance/Usage Check

No dedicated usage endpoint. **Rate-limit headers are returned on every response**:

| Header | Description |
|--------|-------------|
| `X-RateLimit-Limit` | Monthly query limit |
| `X-RateLimit-Remaining` | Queries remaining this month |
| `X-RateLimit-Used` | Queries used this month |

## Search Endpoint

`GET https://api.search.brave.com/res/v1/web/search`

Headers:
```
Accept: application/json
X-Subscription-Token: <API_KEY>
```

Params: `q`, `count` (max 20), `offset`, `country`, `search_lang`, `freshness`

## Free Tier

2,000 queries/month on free plan.

## Related

- [Tavily](../tavily/) — alternative search provider
- [SearXNG](../../tools/searxng/) — self-hosted alternative
