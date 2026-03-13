# Claude Code

> Source: https://github.com/anthropics/claude-code
> Docs: https://code.claude.com/docs/en/overview
> Cached: 2026-03-12

## What is Claude Code?

Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows -- all through natural language commands.

## Installation

### MacOS/Linux (Recommended)
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

### Homebrew (MacOS/Linux)
```bash
brew install --cask claude-code
```

### Windows (Recommended)
```powershell
irm https://claude.ai/install.ps1 | iex
```

### WinGet (Windows)
```powershell
winget install Anthropic.ClaudeCode
```

## Quick Start

1. Install Claude Code using one of the methods above
2. Navigate to your project directory
3. Run `claude`
4. Give natural language commands

## Features

- **Codebase Understanding** - Reads and understands your entire codebase
- **Task Execution** - Executes routine development tasks
- **Code Explanation** - Explains complex code in simple terms
- **Git Workflows** - Handles commits, branches, PRs through natural language
- **Terminal Integration** - Lives directly in your terminal
- **IDE Integration** - Works with VS Code and other IDEs
- **GitHub Integration** - Tag @claude on GitHub issues/PRs

## Plugins

Extend Claude Code with custom plugins:

```bash
# Add plugin marketplace
/plugin marketplace add anthropics/skills

# Install specific plugins
/plugin install document-skills@anthropic-agent-skills
```

## Built-in Commands

- `/bug` - Report bugs directly within Claude Code
- `/clear` - Clear conversation context
- `/help` - Show available commands
- `/handoff` - Create handoff document for context preservation

## Data Collection

Claude Code collects feedback including:
- Usage data (code acceptance/rejections)
- Associated conversation data
- User feedback via `/bug` command

**Privacy safeguards:**
- Limited retention periods for sensitive information
- Restricted access to user session data
- No use of feedback for model training

## Related Docs

- [Agent Skills](../skills/) - Extensible skills system
- [Anthropic TypeScript SDK](../anthropic-sdk-typescript/) - SDK for building Claude apps
- [Anthropic Python SDK](../anthropic-sdk-python/) - Python SDK
- [MCP](../mcp/) - Model Context Protocol
