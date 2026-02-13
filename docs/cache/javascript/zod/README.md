# Zod Documentation

> Source: https://zod.dev/
> Cached: 2026-02-13

## Introduction

Zod is a TypeScript-first validation library. Using Zod, you can define _schemas_ you can use to validate data, from a simple `string` to a complex nested object.

```typescript
import * as z from "zod";

const User = z.object({
  name: z.string(),
});

// some untrusted data...
const input = { /* stuff */ };

// the parsed result is validated and type safe!
const data = User.parse(input);

// so you can use it with confidence :)
console.log(data.name);
```

## Features

- Zero external dependencies
- Works in Node.js and all modern browsers
- Tiny: 2kb core bundle (gzipped)
- Immutable API: methods return a new instance
- Concise interface
- Works with TypeScript and plain JS
- Built-in JSON Schema conversion
- Extensive ecosystem

## Installation

```bash
npm install zod
```

Zod is also available as `@zod/zod` on jsr.io.

## Requirements

Zod is tested against _TypeScript v5.5_ and later. Older versions may work but are not officially supported.

### `"strict"` Mode Required

You must enable `strict` mode in your `tsconfig.json`. This is a best practice for all TypeScript projects.

```json
// tsconfig.json
{
  // ...
  "compilerOptions": {
    // ...
    "strict": true
  }
}
```

## Ecosystem

Zod has a thriving ecosystem of libraries, tools, and integrations:

- **Resources**
- **API Libraries**
- **Form Integrations**
- **Zod to X**
- **X to Zod**
- **Mocking Libraries**
- **Powered by Zod**

### Notable Projects

- **tRPC** - End-to-end typesafe APIs, with support for Zod schemas
- **React Hook Form** - Hook-based form validation with a Zod resolver
- **zshy** - Bundler-free, batteries-included build tool for TypeScript libraries
