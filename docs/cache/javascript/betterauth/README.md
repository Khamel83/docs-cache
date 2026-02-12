# BetterAuth Documentation

> Framework-agnostic, universal authentication and authorization framework for TypeScript.

**Source**: https://www.better-auth.com/docs
**Cached**: 2026-02-12

## Overview

Better Auth is a comprehensive authentication library for TypeScript that provides a wide range of features out of the box with an extensive plugin ecosystem.

## Features

### Core Features
- **Framework Agnostic** - Support for most popular frameworks
- **Email & Password** - Built-in secure email/password authentication
- **Account & Session Management** - Manage user accounts and sessions
- **Built-In Rate Limiter** - Custom rate limiting rules
- **Automatic Database Management** - Auto migrations and schema management
- **Social Sign-on** - Multiple OAuth providers
- **Organization & Access Control** - Multi-tenant support
- **Two Factor Authentication** - 2FA support

### Advanced Features
- Passkey support
- Multi-tenancy
- Multi-session support
- Enterprise SSO
- Create your own IDP

## Installation

```bash
npm install better-auth
```

## Quick Start

```typescript
import { betterAuth } from "better-auth"

export const auth = betterAuth({
  database: {
    // database configuration
  },
  emailAndPassword: {
    enabled: true
  }
})
```

## AI Tooling

### LLMs.txt
Better Auth exposes an `LLMs.txt` for AI model integration:
https://better-auth.com/llms.txt

### MCP Integration
Better Auth provides an MCP server for AI assistants:

```bash
# Add to Claude Code
npx @better-auth/cli mcp --claude-code

# Add to Cursor
npx @better-auth/cli mcp --cursor

# Manual configuration
claude mcp add --transport http better-auth https://mcp.chonkie.ai/better-auth/better-auth-builder/mcp
```

## Plugin Ecosystem

Extend functionality with plugins:
- Two-factor authentication
- Passkeys
- Organizations
- SSO providers
- And more

## Links

- **Docs**: https://www.better-auth.com/docs
- **GitHub**: https://github.com/better-auth/better-auth
- **LLMs.txt**: https://better-auth.com/llms.txt
- **MCP Server**: https://mcp.chonkie.ai/better-auth/better-auth-builder/mcp
