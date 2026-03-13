# Agent Skills

> Source: https://github.com/anthropics/skills
> Docs: https://agentskills.io
> Cached: 2026-03-12

## What are Skills?

Skills are folders of instructions, scripts, and resources that Claude loads dynamically to improve performance on specialized tasks. Skills teach Claude how to complete specific tasks in a repeatable way.

## Skill Structure

Each skill is a folder with a `SKILL.md` file containing:

```yaml
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name

[Instructions that Claude will follow when this skill is active]
```

## Installation

### Claude Code

```bash
# Add marketplace
/plugin marketplace add anthropics/skills

# Install specific skill sets
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

### Claude.ai

Skills are available to paid plans in Claude.ai.

### Claude API

Use skills via the Skills API. See the Skills API Quickstart.

## Skill Categories

- **Creative & Design** - Art, music, design
- **Development & Technical** - Testing, MCP server generation
- **Enterprise & Communication** - Communications, branding
- **Document Skills** - DOCX, PDF, PPTX, XLSX

## Creating Skills

1. Create a folder with `SKILL.md`
2. Add YAML frontmatter (`name`, `description`)
3. Write instructions in markdown
4. Include examples and guidelines

## Related Docs

- [Claude Code](../claude-code/) - Agentic coding tool
- [Anthropic API](../anthropic/) - Main API documentation
- [MCP](../mcp/) - Model Context Protocol
