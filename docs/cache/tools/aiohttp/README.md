Title: Welcome to AIOHTTP — aiohttp 3.13.3 documentation

URL Source: https://docs.aiohttp.org/

Published Time: Sat, 03 Jan 2026 16:27:38 GMT

Markdown Content:
Welcome to AIOHTTP — aiohttp 3.13.3 documentation
===============

Welcome to AIOHTTP[¶](https://docs.aiohttp.org/#welcome-to-aiohttp "Link to this heading")
==========================================================================================

Asynchronous HTTP Client/Server for [asyncio](https://docs.aiohttp.org/glossary.html#term-asyncio) and Python.

Current version is 3.13.3.

Key Features[¶](https://docs.aiohttp.org/#key-features "Link to this heading")
------------------------------------------------------------------------------

*   Supports both [Client](https://docs.aiohttp.org/client.html#aiohttp-client) and [HTTP Server](https://docs.aiohttp.org/web.html#aiohttp-web).

*   Supports both [Server WebSockets](https://docs.aiohttp.org/web_quickstart.html#aiohttp-web-websockets) and [Client WebSockets](https://docs.aiohttp.org/client_quickstart.html#aiohttp-client-websockets) out-of-the-box without the Callback Hell.

*   Web-server has [Middlewares](https://docs.aiohttp.org/web_advanced.html#aiohttp-web-middlewares), [Signals](https://docs.aiohttp.org/web_advanced.html#aiohttp-web-signals) and pluggable routing.

*   Client supports [middleware](https://docs.aiohttp.org/client_advanced.html#aiohttp-client-middleware) for customizing request/response processing.

Library Installation[¶](https://docs.aiohttp.org/#library-installation "Link to this heading")
----------------------------------------------------------------------------------------------

$ pip install aiohttp

For speeding up DNS resolving by client API you may install [aiodns](https://docs.aiohttp.org/glossary.html#term-aiodns) as well. This option is highly recommended:

$ pip install aiodns

### Installing all speedups in one command[¶](https://docs.aiohttp.org/#installing-all-speedups-in-one-command "Link to this heading")

The following will get you `aiohttp` along with [aiodns](https://docs.aiohttp.org/glossary.html#term-aiodns) and `Brotli` in one bundle. No need to type separate commands anymore!

$ pip install aiohttp[speedups]

Getting Started[¶](https://docs.aiohttp.org/#getting-started "Link to this heading")
------------------------------------------------------------------------------------

### Client example[¶](https://docs.aiohttp.org/#client-example "Link to this heading")

import aiohttp
import asyncio

async def main():

    async with aiohttp.ClientSession() as session:
        async with session.get('http://python.org') as response:

            print("Status:", response.status)
            print("Content-type:", response.headers['content-type'])

            html = await response.text()
            print("Body:", html[:15], "...")

asyncio.run(main())

This prints:

Status: 200
Content-type: text/html; charset=utf-8
Body: <!doctype html> ...

Coming from [requests](https://docs.aiohttp.org/glossary.html#term-requests) ? Read [why we need so many lines](https://docs.aiohttp.org/http_request_lifecycle.html#aiohttp-request-lifecycle).

### Server example:[¶](https://docs.aiohttp.org/#server-example "Link to this heading")

from aiohttp import web

async def handle(request):
    name = request.match_info.get('name', "Anonymous")
    text = "Hello, " + name
    return web.Response(text=text)

app = web.Application()
app.add_routes([web.get('/', handle),
                web.get('/{name}', handle)])

if  __name__  == '__main__':
    web.run_app(app)

For more information please visit [Client](https://docs.aiohttp.org/client.html#aiohttp-client) and [Server](https://docs.aiohttp.org/web.html#aiohttp-web) pages.

Development mode[¶](https://docs.aiohttp.org/#development-mode "Link to this heading")
--------------------------------------------------------------------------------------

When writing your code, we recommend enabling Python’s [development mode](https://docs.python.org/3/library/devmode.html) (`python -X dev`). In addition to the extra features enabled for asyncio, aiohttp will:

*   Use a strict parser in the client code (which can help detect malformed responses from a server).

*   Enable some additional checks (resulting in warnings in certain situations).

What’s new in aiohttp 3?[¶](https://docs.aiohttp.org/#what-s-new-in-aiohttp-3 "Link to this heading")
-----------------------------------------------------------------------------------------------------

Go to [What’s new in aiohttp 3.0](https://docs.aiohttp.org/whats_new_3_0.html#aiohttp-whats-new-3-0) page for aiohttp 3.0 major release changes.

Tutorial[¶](https://docs.aiohttp.org/#tutorial "Link to this heading")
----------------------------------------------------------------------

[Polls tutorial](https://aiohttp-demos.readthedocs.io/en/latest/index.html#aiohttp-demos-polls-beginning "(in aiohttp-demos v0.2)")

Source code[¶](https://docs.aiohttp.org/#source-code "Link to this heading")
----------------------------------------------------------------------------

The project is hosted on [GitHub](https://github.com/aio-libs/aiohttp)

Please feel free to file an issue on the [bug tracker](https://github.com/aio-libs/aiohttp/issues) if you have found a bug or have some suggestion in order to improve the library.

Dependencies[¶](https://docs.aiohttp.org/#dependencies "Link to this heading")
------------------------------------------------------------------------------

*   _attrs_

*   _multidict_

*   _yarl_

*   _Optional_[aiodns](https://docs.aiohttp.org/glossary.html#term-aiodns) for fast DNS resolving. The library is highly recommended.

$ pip install aiodns  
*   _Optional_[Brotli](https://docs.aiohttp.org/glossary.html#term-Brotli) or [brotlicffi](https://docs.aiohttp.org/glossary.html#term-brotlicffi) for brotli ([**RFC 7932**](https://datatracker.ietf.org/doc/html/rfc7932.html)) client compression support.

$ pip install Brotli  

Communication channels[¶](https://docs.aiohttp.org/#communication-channels "Link to this heading")
--------------------------------------------------------------------------------------------------

_aio-libs Discussions_: [https://github.com/aio-libs/aiohttp/discussions](https://github.com/aio-libs/aiohttp/discussions)

Feel free to post your questions and ideas here.

_Matrix_: [#aio-libs:matrix.org](https://matrix.to/#/#aio-libs:matrix.org)

We support [Stack Overflow](https://stackoverflow.com/questions/tagged/aiohttp). Please add _aiohttp_ tag to your question there.

Contributing[¶](https://docs.aiohttp.org/#contributing "Link to this heading")
------------------------------------------------------------------------------

Please read the [instructions for contributors](https://docs.aiohttp.org/contributing.html#aiohttp-contributing) before making a Pull Request.

Authors and License[¶](https://docs.aiohttp.org/#authors-and-license "Link to this heading")
--------------------------------------------------------------------------------------------

The `aiohttp` package is written mostly by Nikolay Kim and Andrew Svetlov.

It’s _Apache 2_ licensed and freely available.

Feel free to improve this package and send a pull request to [GitHub](https://github.com/aio-libs/aiohttp).

Policy for Backward Incompatible Changes[¶](https://docs.aiohttp.org/#policy-for-backward-incompatible-changes "Link to this heading")
--------------------------------------------------------------------------------------------------------------------------------------

_aiohttp_ keeps backward compatibility.

After deprecating some _Public API_ (method, class, function argument, etc.) the library guaranties the usage of _deprecated API_ is still allowed at least for a year and half after publishing new release with deprecation.

All deprecations are reflected in documentation and raises [`DeprecationWarning`](https://docs.python.org/3/library/exceptions.html#DeprecationWarning "(in Python v3.14)").

Sometimes we are forced to break the own rule for sake of very strong reason. Most likely the reason is a critical bug which cannot be solved without major API change, but we are working hard for keeping these changes as rare as possible.

Table Of Contents[¶](https://docs.aiohttp.org/#table-of-contents "Link to this heading")
----------------------------------------------------------------------------------------

*   [Client](https://docs.aiohttp.org/client.html)
    *   [Quickstart](https://docs.aiohttp.org/client_quickstart.html)
    *   [Advanced Usage](https://docs.aiohttp.org/client_advanced.html)
    *   [Client Middleware Cookbook](https://docs.aiohttp.org/client_middleware_cookbook.html)
    *   [Reference](https://docs.aiohttp.org/client_reference.html)
    *   [Tracing Reference](https://docs.aiohttp.org/tracing_reference.html)
    *   [The aiohttp Request Lifecycle](https://docs.aiohttp.org/http_request_lifecycle.html)

*   [Server](https://docs.aiohttp.org/web.html)
    *   [Tutorial](https://demos.aiohttp.org/)
    *   [Quickstart](https://docs.aiohttp.org/web_quickstart.html)
    *   [Advanced Usage](https://docs.aiohttp.org/web_advanced.html)
    *   [Low Level](https://docs.aiohttp.org/web_lowlevel.html)
    *   [Reference](https://docs.aiohttp.org/web_reference.html)
    *   [Logging](https://docs.aiohttp.org/logging.html)
    *   [Testing](https://docs.aiohttp.org/testing.html)
    *   [Deployment](https://docs.aiohttp.org/deployment.html)

*   [Utilities](https://docs.aiohttp.org/utilities.html)
    *   [Abstract Base Classes](https://docs.aiohttp.org/abc.html)
    *   [Working with Multipart](https://docs.aiohttp.org/multipart.html)
    *   [Multipart reference](https://docs.aiohttp.org/multipart_reference.html)
    *   [Streaming API](https://docs.aiohttp.org/streams.html)
    *   [Common data structures](https://docs.aiohttp.org/structures.html)
    *   [WebSocket utilities](https://docs.aiohttp.org/websocket_utilities.html)

*   [FAQ](https://docs.aiohttp.org/faq.html)
    *   [Are there plans for an @app.route decorator like in Flask?](https://docs.aiohttp.org/faq.html#are-there-plans-for-an-app-route-decorator-like-in-flask)
    *   [Does aiohttp have a concept like Flask’s “blueprint” or Django’s “app”?](https://docs.aiohttp.org/faq.html#does-aiohttp-have-a-concept-like-flask-s-blueprint-or-django-s-app)
    *   [How do I create a route that matches urls with a given prefix?](https://docs.aiohttp.org/faq.html#how-do-i-create-a-route-that-matches-urls-with-a-given-prefix)
    *   [Where do I put my database connection so handlers can access it?](https://docs.aiohttp.org/faq.html#where-do-i-put-my-database-connection-so-handlers-can-access-it)
    *   [How can middleware store data for web handlers to use?](https://docs.aiohttp.org/faq.html#how-can-middleware-store-data-for-web-handlers-to-use)
    *   [Can a handler receive incoming events from different sources in parallel?](https://docs.aiohttp.org/faq.html#can-a-handler-receive-incoming-events-from-different-sources-in-parallel)
    *   [How do I programmatically close a WebSocket server-side?](https://docs.aiohttp.org/faq.html#how-do-i-programmatically-close-a-websocket-server-side)
    *   [How do I make a request from a specific IP address?](https://docs.aiohttp.org/faq.html#how-do-i-make-a-request-from-a-specific-ip-address)
    *   [What is the API stability and deprecation policy?](https://docs.aiohttp.org/faq.html#what-is-the-api-stability-and-deprecation-policy)
    *   [How do I enable gzip compression globally for my entire application?](https://docs.aiohttp.org/faq.html#how-do-i-enable-gzip-compression-globally-for-my-entire-application)
    *   [How do I manage a ClientSession within a web server?](https://docs.aiohttp.org/faq.html#how-do-i-manage-a-clientsession-within-a-web-server)
    *   [How do I access database connections from a subapplication?](https://docs.aiohttp.org/faq.html#how-do-i-access-database-connections-from-a-subapplication)
    *   [How do I perform operations in a request handler after sending the response?](https://docs.aiohttp.org/faq.html#how-do-i-perform-operations-in-a-request-handler-after-sending-the-response)
    *   [How do I make sure my custom middleware response will behave correctly?](https://docs.aiohttp.org/faq.html#how-do-i-make-sure-my-custom-middleware-response-will-behave-correctly)
    *   [Why is creating a ClientSession outside of an event loop dangerous?](https://docs.aiohttp.org/faq.html#why-is-creating-a-clientsession-outside-of-an-event-loop-dangerous)

*   [Miscellaneous](https://docs.aiohttp.org/misc.html)
    *   [Essays](https://docs.aiohttp.org/essays.html)
    *   [Glossary](https://docs.aiohttp.org/glossary.html)
    *   [Changelog](https://docs.aiohttp.org/changes.html)
    *   [Indices and tables](https://docs.aiohttp.org/misc.html#indices-and-tables)

*   [Who uses aiohttp?](https://docs.aiohttp.org/external.html)
    *   [Third-Party libraries](https://docs.aiohttp.org/third_party.html)
    *   [Built with aiohttp](https://docs.aiohttp.org/built_with.html)
    *   [Powered by aiohttp](https://docs.aiohttp.org/powered_by.html)

*   [Contributing](https://docs.aiohttp.org/contributing.html)
    *   [Instructions for contributors](https://docs.aiohttp.org/contributing.html#instructions-for-contributors)
    *   [Preconditions for running aiohttp test suite](https://docs.aiohttp.org/contributing.html#preconditions-for-running-aiohttp-test-suite)
    *   [LLHTTP](https://docs.aiohttp.org/contributing.html#llhttp)
    *   [Run autoformatter](https://docs.aiohttp.org/contributing.html#run-autoformatter)
    *   [Run aiohttp test suite](https://docs.aiohttp.org/contributing.html#run-aiohttp-test-suite)
    *   [Code coverage](https://docs.aiohttp.org/contributing.html#code-coverage)
    *   [Other tools](https://docs.aiohttp.org/contributing.html#other-tools)
    *   [Documentation](https://docs.aiohttp.org/contributing.html#documentation)
    *   [Spell checking](https://docs.aiohttp.org/contributing.html#spell-checking)
    *   [Preparing a pull request](https://docs.aiohttp.org/contributing.html#preparing-a-pull-request)
    *   [Changelog update](https://docs.aiohttp.org/contributing.html#changelog-update)
    *   [Making a pull request](https://docs.aiohttp.org/contributing.html#making-a-pull-request)
    *   [Backporting](https://docs.aiohttp.org/contributing.html#backporting)
    *   [How to become an aiohttp committer](https://docs.aiohttp.org/contributing.html#how-to-become-an-aiohttp-committer)

[![Image 1: Logo of aiohttp](https://docs.aiohttp.org/_static/aiohttp-plain.svg)](https://docs.aiohttp.org/#)

[aiohttp](https://docs.aiohttp.org/#)
=====================================

Async HTTP client/server for asyncio and Python

*   [![Image 2: Azure Pipelines CI status](https://github.com/aio-libs/aiohttp/workflows/CI/badge.svg)](https://github.com/aio-libs/aiohttp/actions?query=workflow%3ACI)
*   [![Image 3: Code coverage status](https://codecov.io/github/aio-libs/aiohttp/coverage.svg?branch=master)](https://codecov.io/github/aio-libs/aiohttp)
*   [![Image 4: Latest PyPI package version](https://badge.fury.io/py/aiohttp.svg)](https://badge.fury.io/py/aiohttp)
*   [![Image 5: Chat on Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/aio-libs/Lobby)

### Navigation

*   [Client](https://docs.aiohttp.org/client.html)
*   [Server](https://docs.aiohttp.org/web.html)
*   [Utilities](https://docs.aiohttp.org/utilities.html)
*   [FAQ](https://docs.aiohttp.org/faq.html)
*   [Miscellaneous](https://docs.aiohttp.org/misc.html)
*   [Who uses aiohttp?](https://docs.aiohttp.org/external.html)
*   [Contributing](https://docs.aiohttp.org/contributing.html)

### Quick search

 ©aiohttp contributors. | Powered by [Sphinx 9.0.4](http://sphinx-doc.org/) | [Page source](https://docs.aiohttp.org/_sources/index.rst.txt)

[![Image 6: Fork me on GitHub](https://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png)](https://github.com/aio-libs/aiohttp)
