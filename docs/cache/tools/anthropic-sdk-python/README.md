# Anthropic Python SDK

> Source: https://github.com/anthropics/anthropic-sdk-python
> Docs: https://docs.anthropic.com/en/api/sdks/python
> Cached: 2026-03-12

## Installation

```bash
pip install anthropic
```

## Quick Start

```python
import os
from anthropic import Anthropic

client = Anthropic(
    api_key=os.environ.get("ANTHROPIC_API_KEY"),
)

message = client.messages.create(
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": "Hello, Claude",
        }
    ],
    model="claude-opus-4-6",
)
print(message.content)
```

## Streaming

```python
with client.messages.stream(
    max_tokens=1024,
    messages=[{"role": "user", "content": "Hello"}],
    model="claude-opus-4-6",
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
```

## Tool Use

```python
import anthropic

client = Anthropic()

response = client.messages.create(
    model="claude-opus-4-6",
    max_tokens=1024,
    tools=[
        {
            "name": "get_weather",
            "description": "Get weather for a location",
            "input_schema": {
                "type": "object",
                "properties": {
                    "location": {
                        "type": "string",
                        "description": "City name"
                    }
                },
                "required": ["location"]
            }
        }
    ],
    messages=[{"role": "user", "content": "What's the weather in SF?"}]
)
```

## Requirements

- Python 3.9+

## Related Docs

- [Anthropic API](../anthropic/) - Main API documentation
- [MCP](../mcp/) - Model Context Protocol
