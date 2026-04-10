# Jina Reader API

> Cached: 2026-04-09 — **verify against live docs**: https://jina.ai/reader

## Balance/Usage Check

No API endpoint for checking balance. Usage tracked via dashboard only.

Token-based pricing. Balance tracked manually via `argus set-balance -s jina -b <count>`.

## Reader Endpoint

`GET https://r.jina.ai/<URL>`

Or with API key:
```
Authorization: Bearer <API_KEY>
```

Returns extracted markdown content from any URL.

## Free Tier

Free tier has rate limits (no API key required). Paid tier uses tokens.

## Related

- [You.com API](../you-api/) — alternative content extraction
- [Trafilatura](../../python/trafilatura/) — local extraction alternative
