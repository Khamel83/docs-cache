# Sentry Documentation

> Source: https://docs.sentry.io/
> Cached: 2026-02-13

## Application Performance Monitoring & Error Tracking

Sentry provides end-to-end distributed tracing, enabling developers to identify and debug performance issues and errors across their systems and services.

## Features

- **Error Tracking** - Real-time error monitoring with stack traces and context
- **Performance Monitoring** - Distributed tracing to identify bottlenecks
- **Session Replay** - Replay user sessions to understand issues
- **Alerts** - Configurable alerts for errors and performance issues
- **Issue Grouping** - Smart grouping of similar errors

## Supported SDKs

Sentry supports a wide range of platforms:

- **JavaScript/TypeScript**: Next.js, React, Node.js, React Native
- **Python**: Django, Flask, FastAPI
- **PHP**: Laravel
- **Go**
- **Ruby**: Rails
- **Java**
- **Rust**
- **.NET**
- **Mobile**: Android, Apple (iOS/macOS)
- And many more...

## Quick Start (Python)

```python
import sentry_sdk

sentry_sdk.init(
    dsn="https://examplePublicKey@o0.ingest.sentry.io/0",
    traces_sample_rate=1.0,
)
```

## Quick Start (JavaScript)

```javascript
import * as Sentry from "@sentry/browser";

Sentry.init({
  dsn: "https://examplePublicKey@o0.ingest.sentry.io/0",
  tracesSampleRate: 1.0,
});
```

## Key Concepts

- **DSN** - Data Source Name, the connection string for your project
- **Events** - Individual error or transaction records
- **Issues** - Grouped similar events
- **Projects** - Logical grouping of applications
- **Environments** - Separate error tracking for different environments (dev, staging, prod)

## CLI

Sentry provides a command-line interface for source map uploads, release management, and more:

```bash
sentry-cli releases new <version>
sentry-cli releases set-commits --auto <version>
sentry-cli releases finalize <version>
```

## Pricing

- Free tier available for small teams
- Team and Business plans for growing organizations
- Enterprise options for large-scale deployments
