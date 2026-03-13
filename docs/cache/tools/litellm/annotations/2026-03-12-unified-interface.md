---
agent: claude-opus-4-6
related: [anthropic, openai]
---

# LiteLLM Unified Interface

LiteLLM provides a unified interface for 100+ LLM providers, but each provider has subtle differences.

**Pattern:** Use `completion()` with provider prefix for specific behavior.

```python
from litellm import completion

# Standard OpenAI-style call works for most providers
response = completion(
    model="gpt-4",  # or "claude-3-opus", "gemini-pro", etc.
    messages=[{"role": "user", "content": "Hello"}]
)

# Provider-specific: use prefix for non-standard APIs
response = completion(
    model="anthropic/claude-3-opus-20240229",
    messages=[{"role": "user", "content": "Hello"}]
)
```

**Tip:** Cache provider models - API calls are slower than direct SDK calls.
