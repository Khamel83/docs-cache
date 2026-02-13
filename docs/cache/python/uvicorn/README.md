# Uvicorn Documentation

> Source: https://www.uvicorn.org/
> Cached: 2026-02-13

## ASGI Web Server for Python

Uvicorn is an ASGI web server implementation for Python. Until recently Python has lacked a minimal low-level server/application interface for async frameworks. The ASGI specification fills this gap, and means we're now able to start building a common set of tooling usable across all async frameworks.

Uvicorn currently supports **HTTP/1.1** and **WebSockets**.

## Installation

```bash
pip install uvicorn
```

## Quickstart

Create a simple ASGI application:

```python
async def app(scope, receive, send):
    assert scope['type'] == 'http'
    await send({
        'type': 'http.response.start',
        'status': 200,
        'headers': [
            (b'content-type', b'text/plain'),
            (b'content-length', b'13'),
        ],
    })
    await send({
        'type': 'http.response.body',
        'body': b'Hello, world!',
    })
```

Run it with Uvicorn:

```bash
uvicorn main:app
```

## Command Line Options

| Option | Description | Default |
|--------|-------------|---------|
| `--host TEXT` | Bind socket to this host | 127.0.0.1 |
| `--port INTEGER` | Bind socket to this port | 8000 |
| `--reload` | Enable auto-reload | False |
| `--workers INTEGER` | Number of worker processes | 1 |
| `--loop` | Event loop (auto/asyncio/uvloop) | auto |
| `--http` | HTTP protocol (auto/h11/httptools) | auto |
| `--ws` | WebSocket protocol | auto |
| `--lifespan` | Lifespan implementation | auto |
| `--log-level` | Log level | info |

## Running Programmatically

```python
import uvicorn

async def app(scope, receive, send):
    ...

if __name__ == "__main__":
    uvicorn.run("main:app", port=5000, log_level="info")
```

## Running with Gunicorn

For production deployments we recommend using gunicorn with the uvicorn worker class:

```bash
gunicorn example:app -w 4 -k uvicorn.workers.UvicornWorker
```

This allows you to increase or decrease the number of worker processes on the fly, restart worker processes gracefully, or perform server upgrades without downtime.
