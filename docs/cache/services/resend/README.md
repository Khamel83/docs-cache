# Resend — Email API (Python SDK)

> Cached: 2026-03-15
> Source: https://resend.com/docs/send-with-python + https://resend.com/docs/api-reference/introduction

---

## Installation

```bash
pip install resend
```

---

## Sending Emails

```python
import os
import resend

resend.api_key = os.environ["RESEND_API_KEY"]

params: resend.Emails.SendParams = {
    "from": "Acme <onboarding@resend.dev>",
    "to": ["delivered@resend.dev"],
    "subject": "hello world",
    "html": "<strong>it works!</strong>",
}

email = resend.Emails.send(params)
# Returns dict with 'id' key: {"id": "49a3999c-0ce1-4ea6-ab68-afcd6dc2e794"}
print(email["id"])
```

### Required Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `from` | str | Sender address, e.g. `"Name <email@domain.com>"` |
| `to` | list[str] | Recipient email addresses |
| `subject` | str | Email subject line |
| `html` | str | HTML body content |

### Optional Parameters

- `text` — Plain text fallback
- `cc`, `bcc`, `reply_to` — Additional recipients
- `attachments` — File attachments
- `scheduled_at` — Delayed delivery (ISO 8601)
- `headers` — Custom headers
- `tags` — Key/value metadata tags

### Response

`resend.Emails.send()` returns a dict with at minimum:
```python
{"id": "49a3999c-0ce1-4ea6-ab68-afcd6dc2e794"}
```

---

## Read-Only Connectivity Check

Use `resend.ApiKeys.list()` to verify the API key is valid without sending an email:

```python
import resend

resend.api_key = os.environ["RESEND_API_KEY"]
keys = resend.ApiKeys.list()
# Returns list of API key objects — empty list is still a success (key is valid)
```

This is useful for health checks and preflight validation.

---

## Rate Limits

- **Default**: 2 requests per second per team (across all API keys)
- Exceeding the limit returns HTTP `429`
- Teams can request increases via the Resend dashboard (Settings → Usage)

---

## Exception Classes

All exceptions are in `resend.exceptions`.

### RateLimitError

Raised on HTTP 429 responses.

```python
from resend.exceptions import RateLimitError

# Constructor signature:
# RateLimitError(message: str, error_type: str, code: Union[str, int], headers=None)

try:
    resend.Emails.send(params)
except RateLimitError as e:
    print(e.message)      # Human-readable message
    print(e.error_type)   # Error type string
    print(e.code)         # HTTP status code or error code
    # e.headers is optional (response headers)
```

### AuthenticationError

Raised on HTTP 401/403 responses (missing or invalid API key).

```python
from resend.exceptions import AuthenticationError

try:
    resend.Emails.send(params)
except AuthenticationError as e:
    print("Auth failed:", e)
```

### General Error Handling Pattern

```python
import resend
from resend.exceptions import RateLimitError, AuthenticationError

resend.api_key = os.environ["RESEND_API_KEY"]

try:
    result = resend.Emails.send(params)
    email_id = result["id"]
except RateLimitError as e:
    # Retry after delay
    import time
    time.sleep(1)
    result = resend.Emails.send(params)
except AuthenticationError as e:
    # API key problem — fail loudly
    raise RuntimeError("Resend API key invalid") from e
except Exception as e:
    # Catch-all for network errors, 5xx, etc.
    raise
```

---

## HTTP Status Codes & Error Codes

| Status | Error Code | Meaning |
|--------|-----------|---------|
| 200 | — | Success |
| 400 | `validation_error` | Invalid parameters |
| 400 | `invalid_idempotency_key` | Key must be 1-256 chars |
| 401 | `missing_api_key` | No API key in Authorization header |
| 401 | `restricted_api_key` | Key lacks permissions |
| 403 | `invalid_api_key` | Incorrect or expired API key |
| 403 | `1010` | Missing User-Agent header (not an auth issue) |
| 404 | `not_found` | Invalid endpoint URL |
| 405 | `method_not_allowed` | Wrong HTTP method |
| 409 | `invalid_idempotent_request` | Idempotency key reused with different payload |
| 422 | `invalid_from_address` | Malformed sender address |
| 422 | `invalid_attachment` | Missing content or path |
| 422 | `missing_required_field` | Required body field absent |
| 429 | `rate_limit_exceeded` | Too many requests (>2/sec) |
| 429 | `daily_quota_exceeded` | Daily sending limit hit |
| 429 | `monthly_quota_exceeded` | Plan limit reached |
| 500 | `application_error` | Resend server error |

---

## Free Tier Limits

- 3,000 emails/month
- 2 requests/second
- Verified domain required for production sending

---

## Prerequisites

- Create an API key at https://resend.com/api-keys
- Verify your domain at https://resend.com/domains
- Set `RESEND_API_KEY` environment variable

---

## Related Docs

- [Supabase](../../tools/supabase/) — Database backend used with Resend in Net Worth Tennis
- [Vercel](../../tools/vercel/) — Deployment platform where API functions call Resend
