# Tavily API

> Cached: 2026-04-09 — **verify against live docs**: https://docs.tavily.com

## Balance/Usage Check

**Endpoint**: `GET https://api.tavily.com/usage`
**Auth**: `Authorization: Bearer <API_KEY>`

Response:
```json
{
  "key": {
    "usage": 150,
    "limit": 1000,
    "search_usage": 100,
    "extract_usage": 25,
    "crawl_usage": 15,
    "map_usage": 7,
    "research_usage": 3
  },
  "account": {
    "current_plan": "Bootstrap",
    "plan_usage": 500,
    "plan_limit": 15000,
    "paygo_usage": 25,
    "paygo_limit": 100
  }
}
```

## Search Endpoint

`POST https://api.tavily.com/search`

```json
{
  "api_key": "<KEY>",
  "query": "search terms",
  "max_results": 10
}
```

## Free Tier

1,000 queries/month on free plan. Usage resets monthly.

## Related

- [Brave Search](../brave-search/) — alternative search provider
- [Serper](../serper/) — Google search API
