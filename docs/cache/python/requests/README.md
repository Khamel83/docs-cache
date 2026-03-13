# Requests Documentation

> Source: https://requests.readthedocs.io/
> Cached: 2026-02-13

## HTTP for Humans™

Release v2.32.3

**Requests** is an elegant and simple HTTP library for Python, built for human beings.

## Quick Example

```python
>>> r = requests.get('https://api.github.com/user', auth=('user', 'pass'))
>>> r.status_code
200
>>> r.headers['content-type']
'application/json; charset=utf8'
>>> r.encoding
'utf-8'
>>> r.text
'{"type":"User"...'
>>> r.json()
{'private_gists': 419, 'total_private_repos': 77, ...}
```

**Requests** allows you to send HTTP/1.1 requests extremely easily. There's no need to manually add query strings to your URLs, or to form-encode your POST data. Keep-alive and HTTP connection pooling are 100% automatic, thanks to urllib3.

## Features

- Keep-Alive & Connection Pooling
- International Domains and URLs
- Sessions with Cookie Persistence
- Browser-style SSL Verification
- Automatic Content Decoding
- Basic/Digest Authentication
- Elegant Key/Value Cookies
- Automatic Decompression
- Unicode Response Bodies
- HTTP(S) Proxy Support
- Multipart File Uploads
- Streaming Downloads
- Connection Timeouts
- Chunked Requests
- `.netrc` Support

## Requirements

Requests officially supports Python 3.8+, and runs great on PyPy.

## Installation

```bash
python -m pip install requests
```

## User Guide Sections

- **Quickstart** - Make a Request, Passing Parameters, Response Content, JSON, Headers, Cookies
- **Advanced Usage** - Sessions, SSL, Streaming, Proxies, Authentication
- **Authentication** - Basic, Digest, OAuth 1, OAuth 2
