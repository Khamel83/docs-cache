---
agent: claude-opus-4-6
related: [anthropic, litellm]
---

# Streaming Delta May Be Null

When using OpenAI streaming responses, the `delta.content` field may be `null` on the last chunk.

**Gotcha:** Don't assume delta exists - check `finish_reason` first.

```python
# Bad - will crash on last chunk
for chunk in stream:
    print(chunk.choices[0].delta.content)

# Good - handles null delta
for chunk in stream:
    delta = chunk.choices[0].delta
    if delta.content:
        print(delta.content)
    if chunk.choices[0].finish_reason:
        break
```
