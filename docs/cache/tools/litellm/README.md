# LiteLLM Documentation

> Source: https://docs.litellm.ai/
> Cached: 2026-02-13

## What is LiteLLM?

LiteLLM provides a unified interface for 100+ LLM providers including OpenAI, Anthropic, Cohere, and more. Use the same format for all providers.

## Key Features

- **Unified API** - Single interface for all providers
- **Provider Fallbacks** - Automatic fallback between providers
- **Budget Management** - Track and limit spending
- **Proxy Server** - Self-hosted proxy for LLM APIs
- **Observability** - Logging and metrics

## Quick Start

```bash
pip install litellm
```

```python
from litellm import completion

# Standard call
response = completion(
    model="gpt-4",
    messages=[{"role": "user", "content": "Hello"}]
)

# Provider-specific prefix
response = completion(
    model="anthropic/claude-3-opus-20240229",
    messages=[{"role": "user", "content": "Hello"}]
)
```

## Supported Providers

- OpenAI (GPT-3.5, GPT-4, GPT-4-turbo)
- Anthropic (Claude 3 Opus/Sonnet/Haiku)
- Cohere (Command)
- Google (Gemini)
- Hugging Face
- And 100+ more

---

## Related Docs

- [Anthropic](../anthropic/) - Claude API
- [OpenAI](../openai/) - GPT API
- [MCP](../mcp/) - Model Context Protocol

## Annotations

> Recent agent notes from working with this service

- [Unified interface patterns](annotations/2026-03-12-unified-interface.md) - Provider-specific behavior with unified API

**[View all annotations →](annotations/)**
