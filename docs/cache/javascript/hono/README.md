# Hono Documentation

> Source: https://hono.dev/
> Cached: 2026-02-13

## Hono - Web application framework

Fast, lightweight, built on Web Standards. Support for any JavaScript runtime.

```typescript
import { Hono } from 'hono'
const app = new Hono()
app.get('/', (c) => c.text('Hello Hono!'))
export default app
```

## Features

### Ultrafast & Lightweight
The router RegExpRouter is really fast. The hono/tiny preset is under 14kB. Using only Web Standard APIs.

### Multi-runtime
Works on Cloudflare, Fastly, Deno, Bun, AWS, or Node.js. The same code runs on all platforms.

### Batteries Included
Hono has built-in middleware, custom middleware, third-party middleware, and helpers. Batteries included.

### Delightful DX
Super clean APIs. First-class TypeScript support. Now, we've got "Types".

## Supported Runtimes

- Cloudflare Workers
- Fastly Compute
- Deno
- Bun
- Vercel
- Netlify
- AWS Lambda
- Lambda@Edge
- Node.js
