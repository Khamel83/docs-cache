# Cloudflare Workers Documentation

> Source: https://developers.cloudflare.com/workers/
> Cached: 2026-02-13

## Serverless Platform

Cloudflare Workers is a serverless platform for building, deploying, and scaling apps across Cloudflare's global network with a single command — no infrastructure to manage, no complex configuration.

## Features

- Deliver fast performance with high reliability anywhere in the world
- Build full-stack apps with your framework of choice (React, Vue, Svelte, Next.js, Astro, React Router, and more)
- Use your preferred language (JavaScript, TypeScript, Python, Rust, and more)
- Gain deep visibility with built-in observability
- Get started for free with flexible pricing

## Quick Start

```bash
# Install Wrangler CLI
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Create a new project
wrangler init my-worker

# Develop locally
wrangler dev

# Deploy
wrangler deploy
```

## Build with Workers

### Front-end Applications
Deploy static assets to Cloudflare's CDN & cache for fast rendering.

### Back-end Applications
Build APIs and connect to data stores with Smart Placement to optimize latency.

### Serverless AI Inference
Run LLMs, generate images, and more with Workers AI.

### Background Jobs
Schedule cron jobs, run durable Workflows, and integrate with Queues.

## Integrations (Bindings)

### Storage
- **Durable Objects** - Scalable stateful storage for real-time coordination
- **D1** - Serverless SQL database built for fast, global queries
- **KV** - Low-latency key-value storage for fast, edge-cached reads
- **Queues** - Guaranteed delivery with no charges for egress bandwidth
- **R2** - Zero-egress object storage for cost-efficient data access
- **Hyperdrive** - Connect to external databases with accelerated queries

### Compute
- **Workers AI** - Machine learning models powered by serverless GPUs
- **Workflows** - Durable, long-running operations with automatic retries
- **Vectorize** - Vector database for AI-powered semantic search
- **Browser Rendering** - Programmatic serverless browser instances

### Media
- **Cache/CDN** - Global caching for high-performance delivery
- **Images** - Streamlined image infrastructure from a single API

## Example Worker

```javascript
export default {
  async fetch(request, env, ctx) {
    return new Response('Hello World!');
  },
};
```

## Wrangler Configuration (wrangler.toml)

```toml
name = "my-worker"
main = "src/index.js"
compatibility_date = "2024-01-01"

[vars]
ENVIRONMENT = "production"

[[kv_namespaces]]
binding = "MY_KV"
id = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

## Framework Guides

- React + Vite
- Astro
- Next.js
- Vue
- SvelteKit
- Hono
- And more...

## Testing

Workers supports Vitest integration for testing:

```bash
npm install -D vitest @cloudflare/vitest-pool-workers
```

## Pricing

- Free tier: 100,000 requests/day
- Paid: $5/month for 10M requests
- No egress fees
