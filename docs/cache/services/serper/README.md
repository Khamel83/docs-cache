# Serper (Google Search API)

> Cached: 2026-04-09 — **verify against live docs**: https://serper.dev

## Balance/Usage Check

No dedicated usage endpoint. **Credits returned in every search response**:

```json
{
  "organic": [...],
  "credits": 4975
}
```

Also check for header `X-Credits-Remaining`.

## Search Endpoint

`POST https://google.serper.dev/search`

Headers:
```
X-API-KEY: <API_KEY>
Content-Type: application/json
```

Body:
```json
{
  "q": "search terms",
  "num": 10
}
```

## Free Tier

2,500 one-time credits on signup. Credits are deducted per successful search response (~1 credit each).

## Related

- [Brave Search](../brave-search/) — alternative search provider
- [Tavily](../tavily/) — alternative with usage API
