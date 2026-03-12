# Anthropic Tools (DEPRECATED)

> Source: https://github.com/anthropics/anthropic-tools
> Status: **DEPRECATED** - No longer maintained
> Cached: 2026-03-12

## ⚠️ Deprecation Notice

**This repository is deprecated and no longer maintained.**

For up-to-date information on using tools with Claude, please refer to the official documentation:
https://docs.anthropic.com/en/docs/build-with-claude/tool-use

The official API provides a more robust, supported, and production-ready implementation of tool use functionality.

## What was this?

This was an early alpha SDK for tool/function calling with Anthropic models. It introduced a simple architecture with `BaseTool` and `ToolUser` classes for defining and using tools with Claude.

### Key Concepts (Historical Reference)

- **BaseTool** - Base class for defining individual tools with `use_tool()` method
- **ToolUser** - Class for using Claude with a list of tools
- **Structured Prompt Format** - Early message format similar to Messages API

### Execution Modes

- **Automatic** - Claude executes functions automatically
- **Manual** - Client handles execution with more control

## Migration Path

Use the official Anthropic API tool use functionality instead:
- https://docs.anthropic.com/en/docs/build-with-claude/tool-use

## Related Docs

- [Anthropic API](../anthropic/) - Official API with tool use support
- [Claude Cookbooks](../claude-cookbooks/) - Current examples and patterns
