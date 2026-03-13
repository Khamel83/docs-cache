# Astro Documentation

> JavaScript web framework optimized for building fast, content-driven websites.

**Source**: https://docs.astro.build/
**Cached**: 2026-02-12

## Overview

Astro is a modern web framework designed for content-driven websites. It uses server-first rendering and islands architecture for optimal performance.

## Installation

```bash
# Create a new project with npm
npm create astro@latest
```

**Requirements**: Node.js v16.12.0 or higher

## Key Features

### Islands Architecture
- Ship zero JavaScript by default
- Hydrate interactive components on demand
- Better performance than traditional SPA frameworks

### Server-First Rendering
- HTML rendered on the server
- No heavy client-side JavaScript bundle
- Fast initial page loads

### Content Collections
- Type-safe content management
- Schema validation
- Built for blogs, docs, and marketing sites

### View Transitions
- Smooth page transitions
- No full page reloads
- Progressive enhancement

## Project Structure

```
/
├── public/
├── src/
│   ├── components/
│   ├── layouts/
│   ├── pages/
│   └── content/
├── astro.config.mjs
└── package.json
```

## Astro Components

```astro
---
// Component script (server-side JavaScript/TypeScript)
const title = "Hello World";
---

<!-- Component template (HTML-like syntax) -->
<h1>{title}</h1>

<style>
  /* Scoped CSS */
  h1 {
    color: blue;
  }
</style>
```

## Integrations

Add UI frameworks and tools:

```bash
# Add React
npx astro add react

# Add Vue
npx astro add vue

# Add Svelte
npx astro add svelte

# Add Tailwind
npx astro add tailwind
```

## Content Collections

Define schemas for your content:

```typescript
import { defineCollection, z } from 'astro:content';

const blog = defineCollection({
  schema: z.object({
    title: z.string(),
    date: z.date(),
    tags: z.array(z.string()),
  }),
});

export const collections = { blog };
```

## View Transitions

```astro
---
import { ViewTransitions } from 'astro:transitions';
---

<head>
  <ViewTransitions />
</head>
```

## Latest Version

**Astro 6 Beta** (January 2026):
- Redesigned development server
- Improved rendering performance
- Enhanced build info integration

## Resources

- **Official Docs**: https://docs.astro.build/
- **Getting Started**: https://docs.astro.build/en/getting-started/
- **Installation Guide**: https://docs.astro.build/en/install-and-setup/
- **Themes**: https://astro.build/themes/
- **GitHub**: https://github.com/withastro/astro
- **Discord**: https://astro.build/chat

## Related

- [Build a Blog Tutorial](https://docs.astro.build/en/tutorial/0-introduction/)
- [Starter Themes](https://astro.build/themes/)
- [Integrations](https://astro.build/integrations/)
