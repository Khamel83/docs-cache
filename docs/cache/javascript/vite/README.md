# Vite Documentation

> Source: https://vite.dev/guide/
> Cached: 2026-02-13

## Overview

Vite (French word for "quick", pronounced `/vit/`, like "veet") is a build tool that aims to provide a faster and leaner development experience for modern web projects. It consists of two major parts:

* A dev server that provides [rich feature enhancements](https://vite.dev/guide/features) over [native ES modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules), for example extremely fast [Hot Module Replacement (HMR)](https://vite.dev/guide/features#hot-module-replacement).
* A build command that bundles your code with [Rollup](https://rollupjs.org/), pre-configured to output highly optimized static assets for production.

## Browser Support

During development, Vite assumes that a modern browser is used. For production builds, Vite by default targets [Baseline](https://web-platform-dx.github.io/web-features/) Widely Available browsers (released at least 2.5 years ago).

## Scaffolding Your First Vite Project

```bash
$ npm create vite@latest
```

Then follow the prompts!

### Compatibility Note
Vite requires [Node.js](https://nodejs.org/en/) version 20.19+, 22.12+.

### With Command Line Options

```bash
# npm 7+, extra double-dash is needed:
$ npm create vite@latest my-vue-app -- --template vue
```

### Supported Templates

| JavaScript | TypeScript |
| --- | --- |
| [vanilla](https://vite.new/vanilla) | [vanilla-ts](https://vite.new/vanilla-ts) |
| [vue](https://vite.new/vue) | [vue-ts](https://vite.new/vue-ts) |
| [react](https://vite.new/react) | [react-ts](https://vite.new/react-ts) |
| [preact](https://vite.new/preact) | [preact-ts](https://vite.new/preact-ts) |
| [lit](https://vite.new/lit) | [lit-ts](https://vite.new/lit-ts) |
| [svelte](https://vite.new/svelte) | [svelte-ts](https://vite.new/svelte-ts) |
| [solid](https://vite.new/solid) | [solid-ts](https://vite.new/solid-ts) |
| [qwik](https://vite.new/qwik) | [qwik-ts](https://vite.new/qwik-ts) |

## Manual Installation

```bash
$ npm install -D vite
```

Create an `index.html` file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Vite App</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/main.js"></script>
  </body>
</html>
```

Then run:

```bash
$ npx vite
```

The `index.html` will be served on `http://localhost:5173`.

## `index.html` and Project Root

In a Vite project, `index.html` is front-and-central instead of being tucked away inside `public`. This is intentional: during development Vite is a server, and `index.html` is the entry point to your application.

Vite treats `index.html` as source code and part of the module graph.
