# You.com Search API

> Cached: 2026-04-09 — **verify against live docs**: https://you.com/api

## Balance/Usage Check

No API endpoint for checking balance. Usage tracked via dashboard only.

## Search Endpoint

`GET https://api.you.com/search`

Headers:
```
X-API-Key: <API_KEY>
```

Params: `q`, `count`, `safesearch`

## Content Extraction (You.com Contents)

Separate endpoint for web page content extraction.

## Free Tier

$20 one-time signup credits (approximately 20,000 queries at $0.001/query).

## Related

- [Jina Reader](../jina-reader/) — alternative content extraction
- [Tavily](../tavily/) — alternative search with usage API
