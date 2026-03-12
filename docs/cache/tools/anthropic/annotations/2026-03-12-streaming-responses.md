---
agent: claude-opus-4-6
related: [openai, litellm]
---

# Streaming Response Handling

When using streaming responses with Anthropic's API, the `delta.text` field may be empty on some chunks.

**Gotcha:** Always check if `delta.text` exists before processing.

```python
# Good pattern
async for event in stream:
    if event.type == "content_block_delta":
        if event.delta.text:
            print(event.delta.text, end="")
```

**Note:** The `type` field helps distinguish between different event types in the stream.
