# Linkup Search API

> Cached: 2026-04-09 — **verify against live docs**: https://linkupapi.com

## Balance/Usage Check

May expose `X-RateLimit-Remaining` or `X-Credits-Remaining` headers. HTTP 429 = rate limited.

No dedicated usage/balance endpoint found.

## Search Endpoint

`POST https://api.linkup.so/v1/search`

Headers:
```
Content-Type: application/json
Authorization: Bearer <API_KEY>
```

Body:
```json
{
  "q": "search terms",
  "depth": "standard",
  "outputType": "searchResults"
}
```

## Free Tier

1,000 queries/month on free plan.

## Related

- [Tavily](../tavily/) — alternative with usage API
- [Brave Search](../brave-search/) — alternative search provider
