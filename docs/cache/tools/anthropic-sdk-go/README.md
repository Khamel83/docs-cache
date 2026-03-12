# Anthropic Go SDK

> Source: https://github.com/anthropics/anthropic-sdk-go
> Docs: https://pkg.go.dev/github.com/anthropics/anthropic-sdk-go
> Cached: 2026-03-12

## Installation

```bash
go get github.com/anthropics/anthropic-sdk-go
```

## Quick Start

```go
package main

import (
    "context"
    "fmt"

    "github.com/anthropics/anthropic-sdk-go"
    "github.com/anthropics/anthropic-sdk-go/option"
)

func main() {
    client := anthropic.NewClient(
        option.WithAPIKey("my-anthropic-api-key"),
    )

    message, err := client.Messages.New(context.TODO(), anthropic.MessageNewParams{
        MaxTokens: 1024,
        Messages: []anthropic.MessageParam{
            anthropic.NewUserMessage(anthropic.NewTextBlock("What is a quaternion?")),
        },
        Model: anthropic.ModelClaudeSonnet4_5_20250929,
    })

    fmt.Printf("%+v\n", message.Content)
}
```

## Streaming

```go
stream := client.Messages.NewStreaming(context.TODO(), anthropic.MessageNewParams{
    Model:     anthropic.ModelClaudeSonnet4_5_20250929,
    MaxTokens: 1024,
    Messages: []anthropic.MessageParam{
        anthropic.NewUserMessage(anthropic.NewTextBlock(content)),
    },
})

for stream.Next() {
    event := stream.Current()
    // Handle events
}
```

## Tool Use with Helpers

```go
import "github.com/anthropics/anthropic-sdk-go/toolrunner"

type GetWeatherInput struct {
    City string `json:"city" jsonschema:"required,description=The city name"`
}

func main() {
    weatherTool, _ := toolrunner.NewBetaToolFromJSONSchema(
        "get_weather",
        "Get weather for a city",
        func(ctx context.Context, input GetWeatherInput) (anthropic.BetaToolResultBlockParamContentUnion, error) {
            return anthropic.BetaToolResultBlockParamContentUnion{
                OfText: &anthropic.BetaTextBlockParam{
                    Text: fmt.Sprintf("The weather in %s is sunny, 72°F", input.City),
                },
            }, nil
        },
    )

    runner := client.Beta.Messages.NewToolRunner([]anthropic.BetaTool{weatherTool}, anthropic.BetaToolRunnerParams{
        BetaMessageNewParams: anthropic.BetaMessageNewParams{
            Model:     anthropic.ModelClaudeSonnet4_20250514,
            MaxTokens: 1024,
            Messages: []anthropic.BetaMessageParam{
                anthropic.NewBetaUserMessage(anthropic.NewBetaTextBlock("What's the weather in Paris?")),
            },
        },
        MaxIterations: 5,
    })

    message, err := runner.RunToCompletion(context.Background())
}
```

## Bedrock Support

```go
import "github.com/anthropics/anthropic-sdk-go/bedrock"

client := anthropic.NewClient(
    bedrock.WithLoadDefaultConfig(context.Background()),
)
```

## Vertex AI Support

```go
import "github.com/anthropics/anthropic-sdk-go/vertex"

client := anthropic.NewClient(
    vertex.WithGoogleAuth(context.Background(), "us-central1", "id-xxx"),
)
```

## Requirements

- Go 1.22+

## Related Docs

- [Anthropic API](../anthropic/) - Main API documentation
- [MCP](../mcp/) - Model Context Protocol
