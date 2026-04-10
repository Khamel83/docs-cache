# Exa Search API

> Cached: 2026-04-09 — **verify against live docs**: https://docs.exa.ai

## Balance/Usage Check

Team management API (requires service key):
`GET https://admin-api.exa.ai/team-management/api-keys/{id}/usage`

Headers:
```
x-api-key: <SERVICE_KEY>
```

Returns cost breakdown in USD.

## Search Endpoint

`POST https://api.exa.ai/search`

Headers:
```
Content-Type: application/json
x-api-key: <API_KEY>
```

Body:
```json
{
  "query": "search terms",
  "numResults": 10,
  "type": "auto"
}
```

## Free Tier

1,000 queries/month (likely recurring). Exact limits vary by plan.

## Related

- [Tavily](../tavily/) — alternative with usage API
- [Parallel AI](../parallel-ai/) — alternative search provider
