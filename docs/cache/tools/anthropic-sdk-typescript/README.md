# Anthropic TypeScript SDK

> Source: https://github.com/anthropics/anthropic-sdk-typescript
> Docs: https://docs.anthropic.com/en/api/sdks/typescript
> Cached: 2026-03-12

## Installation

```bash
npm install @anthropic-ai/sdk
```

## Quick Start

```typescript
import Anthropic from '@anthropic-ai/sdk';

const client = new Anthropic({
  apiKey: process.env['ANTHROPIC_API_KEY'],
});

const message = await client.messages.create({
  max_tokens: 1024,
  messages: [{ role: 'user', content: 'Hello, Claude' }],
  model: 'claude-sonnet-4-5-20250929',
});

console.log(message.content);
```

## Streaming

```typescript
const stream = await client.messages.create({
  max_tokens: 1024,
  messages: [{ role: 'user', content: 'Hello, Claude' }],
  model: 'claude-sonnet-4-5-20250929',
  stream: true,
});

for await (const messageStreamEvent of stream) {
  console.log(messageStreamEvent.type);
}
```

## Streaming Helpers

```typescript
const anthropic = new Anthropic();

const stream = anthropic.messages
  .stream({
    model: 'claude-sonnet-4-5-20250929',
    max_tokens: 1024,
    messages: [{ role: 'user', content: 'Say hello there!' }],
  })
  .on('text', (text) => {
    console.log(text);
  });

const message = await stream.finalMessage();
```

## Tool Use with Zod

```typescript
import Anthropic from '@anthropic-ai/sdk';
import { betaZodTool } from '@anthropic-ai/sdk/helpers/beta/zod';
import { z } from 'zod';

const anthropic = new Anthropic();

const weatherTool = betaZodTool({
  name: 'get_weather',
  inputSchema: z.object({
    location: z.string(),
  }),
  description: 'Get the current weather in a given location',
  run: (input) => {
    return `The weather in ${input.location} is foggy and 60°F`;
  },
});

const finalMessage = await anthropic.beta.messages.toolRunner({
  model: 'claude-3-5-sonnet-20241022',
  max_tokens: 1000,
  messages: [{ role: 'user', content: 'What is the weather in San Francisco?' }],
  tools: [weatherTool],
});
```

## MCP Helpers

```typescript
import {
  mcpTools,
  mcpMessages,
  mcpResourceToContent,
} from '@anthropic-ai/sdk/helpers/beta/mcp';
import { Client } from '@modelcontextprotocol/sdk/client/index.js';
import { StdioClientTransport } from '@modelcontextprotocol/sdk/client/stdio.js';

// Connect to MCP server
const transport = new StdioClientTransport({ command: 'mcp-server', args: [] });
const mcpClient = new Client({ name: 'my-client', version: '1.0.0' });
await mcpClient.connect(transport);

// Use MCP tools with toolRunner
const { tools } = await mcpClient.listTools();
const runner = await anthropic.beta.messages.toolRunner({
  model: 'claude-sonnet-4-20250514',
  max_tokens: 1024,
  messages: [{ role: 'user', content: 'Use the available tools' }],
  tools: mcpTools(tools, mcpClient),
});
```

## Requirements

- TypeScript >= 4.9
- Node.js 20 LTS+
- Deno v1.28.0+
- Bun 1.0+
- Cloudflare Workers
- Vercel Edge Runtime

## Related Docs

- [Anthropic API](../anthropic/) - Main API documentation
- [MCP](../mcp/) - Model Context Protocol
- [Zod](../zod/) - TypeScript-first schema validation
