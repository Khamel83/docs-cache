Title: HTTPX

URL Source: https://www.python-httpx.org/

Published Time: Thu, 11 Sep 2025 11:03:01 GMT

Markdown Content:
HTTPX
===============
- [x] - [x] 

[Skip to content](https://www.python-httpx.org/#features)

[](https://www.python-httpx.org/ "HTTPX")

 HTTPX 

 Introduction 

 Initializing search 

[encode/httpx](https://github.com/encode/httpx/ "Go to repository")

[](https://www.python-httpx.org/ "HTTPX") HTTPX  

[encode/httpx](https://github.com/encode/httpx/ "Go to repository")

*   - [x]  Introduction  [Introduction](https://www.python-httpx.org/) Table of contents  
    *   [Features](https://www.python-httpx.org/#features)
    *   [Documentation](https://www.python-httpx.org/#documentation)
    *   [Dependencies](https://www.python-httpx.org/#dependencies)
    *   [Installation](https://www.python-httpx.org/#installation)

*   [QuickStart](https://www.python-httpx.org/quickstart/)
*   - [x]  Advanced   Advanced  
    *   [Clients](https://www.python-httpx.org/advanced/clients/)
    *   [Authentication](https://www.python-httpx.org/advanced/authentication/)
    *   [SSL](https://www.python-httpx.org/advanced/ssl/)
    *   [Proxies](https://www.python-httpx.org/advanced/proxies/)
    *   [Timeouts](https://www.python-httpx.org/advanced/timeouts/)
    *   [Resource Limits](https://www.python-httpx.org/advanced/resource-limits/)
    *   [Event Hooks](https://www.python-httpx.org/advanced/event-hooks/)
    *   [Transports](https://www.python-httpx.org/advanced/transports/)
    *   [Text Encodings](https://www.python-httpx.org/advanced/text-encodings/)
    *   [Extensions](https://www.python-httpx.org/advanced/extensions/)

*   - [x]  Guides   Guides  
    *   [Async Support](https://www.python-httpx.org/async/)
    *   [HTTP/2 Support](https://www.python-httpx.org/http2/)
    *   [Logging](https://www.python-httpx.org/logging/)
    *   [Requests Compatibility](https://www.python-httpx.org/compatibility/)
    *   [Troubleshooting](https://www.python-httpx.org/troubleshooting/)

*   - [x]  API Reference   API Reference  
    *   [Developer Interface](https://www.python-httpx.org/api/)
    *   [Exceptions](https://www.python-httpx.org/exceptions/)
    *   [Environment Variables](https://www.python-httpx.org/environment_variables/)

*   - [x]  Community   Community  
    *   [Third Party Packages](https://www.python-httpx.org/third_party_packages/)
    *   [Contributing](https://www.python-httpx.org/contributing/)
    *   [Code of Conduct](https://www.python-httpx.org/code_of_conduct/)

[![Image 1: Speakeasy website header, showing stacked documents with the word speakeasy followed by the tagline: The fastest way to build production MCP & SDKs.](https://www.python-httpx.org/img/speakeasy.png)](https://speakeasy.com/)

 Table of contents  
*   [Features](https://www.python-httpx.org/#features)
*   [Documentation](https://www.python-httpx.org/#documentation)
*   [Dependencies](https://www.python-httpx.org/#dependencies)
*   [Installation](https://www.python-httpx.org/#installation)

![Image 2: HTTPX](https://raw.githubusercontent.com/encode/httpx/master/docs/img/butterfly.png)

HTTPX
=====

* * *

[![Image 3: Test Suite](https://github.com/encode/httpx/workflows/Test%20Suite/badge.svg)](https://github.com/encode/httpx/actions)[![Image 4: Package version](https://badge.fury.io/py/httpx.svg)](https://pypi.org/project/httpx/)

_A next-generation HTTP client for Python._

HTTPX is a fully featured HTTP client for Python 3, which provides sync and async APIs, and support for both HTTP/1.1 and HTTP/2.

* * *

Install HTTPX using pip:

```
$ pip install httpx
```

Now, let's get started:

```
>>> import httpx
>>> r = httpx.get('https://www.example.org/')
>>> r
<Response [200 OK]>
>>> r.status_code
200
>>> r.headers['content-type']
'text/html; charset=UTF-8'
>>> r.text
'<!doctype html>\n<html>\n<head>\n<title>Example Domain</title>...'
```

Or, using the command-line client.

```
# The command line client is an optional dependency.
$ pip install 'httpx[cli]'
```

Which now allows us to use HTTPX directly from the command-line...

![Image 5: httpx --help](https://www.python-httpx.org/img/httpx-help.png)

Sending a request...

![Image 6: httpx http://httpbin.org/json](https://www.python-httpx.org/img/httpx-request.png)

Features
--------

HTTPX builds on the well-established usability of `requests`, and gives you:

*   A broadly [requests-compatible API](https://www.python-httpx.org/compatibility/).
*   Standard synchronous interface, but with [async support if you need it](https://www.python-httpx.org/async/).
*   HTTP/1.1 [and HTTP/2 support](https://www.python-httpx.org/http2/).
*   Ability to make requests directly to [WSGI applications](https://www.python-httpx.org/advanced/transports/#wsgi-transport) or [ASGI applications](https://www.python-httpx.org/advanced/transports/#asgi-transport).
*   Strict timeouts everywhere.
*   Fully type annotated.
*   100% test coverage.

Plus all the standard features of `requests`...

*   International Domains and URLs
*   Keep-Alive & Connection Pooling
*   Sessions with Cookie Persistence
*   Browser-style SSL Verification
*   Basic/Digest Authentication
*   Elegant Key/Value Cookies
*   Automatic Decompression
*   Automatic Content Decoding
*   Unicode Response Bodies
*   Multipart File Uploads
*   HTTP(S) Proxy Support
*   Connection Timeouts
*   Streaming Downloads
*   .netrc Support
*   Chunked Requests

Documentation
-------------

For a run-through of all the basics, head over to the [QuickStart](https://www.python-httpx.org/quickstart/).

For more advanced topics, see the **Advanced** section, the [async support](https://www.python-httpx.org/async/) section, or the [HTTP/2](https://www.python-httpx.org/http2/) section.

The [Developer Interface](https://www.python-httpx.org/api/) provides a comprehensive API reference.

To find out about tools that integrate with HTTPX, see [Third Party Packages](https://www.python-httpx.org/third_party_packages/).

Dependencies
------------

The HTTPX project relies on these excellent libraries:

*   `httpcore` - The underlying transport implementation for `httpx`.
*   `h11` - HTTP/1.1 support.
*   `certifi` - SSL certificates.
*   `idna` - Internationalized domain name support.
*   `sniffio` - Async library autodetection.

As well as these optional installs:

*   `h2` - HTTP/2 support. _(Optional, with `httpx[http2]`)_
*   `socksio` - SOCKS proxy support. _(Optional, with `httpx[socks]`)_
*   `rich` - Rich terminal support. _(Optional, with `httpx[cli]`)_
*   `click` - Command line client support. _(Optional, with `httpx[cli]`)_
*   `brotli` or `brotlicffi` - Decoding for "brotli" compressed responses. _(Optional, with `httpx[brotli]`)_
*   `zstandard` - Decoding for "zstd" compressed responses. _(Optional, with `httpx[zstd]`)_

A huge amount of credit is due to `requests` for the API layout that much of this work follows, as well as to `urllib3` for plenty of design inspiration around the lower-level networking details.

Installation
------------

Install with pip:

```
$ pip install httpx
```

Or, to include the optional HTTP/2 support, use:

```
$ pip install httpx[http2]
```

To include the optional brotli and zstandard decoders support, use:

```
$ pip install httpx[brotli,zstd]
```

HTTPX requires Python 3.9+

 Made with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
