# Proxy Provider Setup

This component configures proxied AI model endpoints for OpenCode via your local proxy server.

## Quick Start

1. Set the required environment variables
2. Select a model from the available providers
3. Start coding with OpenCode

## Required Environment Variables

```bash
export PROXY_API_KEY="your_api_key_here"
export PROXY_BASE_URL="http://localhost:8317"
```

## Available Models

### Claude (via cliproxy)

| Model | Features |
|-------|----------|
| `cliproxy/claude-opus-4-5-thinking` | Extended thinking, 200K context, 64K output |
| `cliproxy/claude-sonnet-4-5` | Fast, 200K context, 64K output |
| `cliproxy/claude-sonnet-4-5-thinking` | Extended thinking, 200K context, 64K output |

### Google Gemini (via cliproxygoogle)

| Model | Features |
|-------|----------|
| `cliproxygoogle/gemini-3-pro-preview` | Reasoning, 1M context |
| `cliproxygoogle/gemini-3-pro-image-preview` | Image support, 1M context |
| `cliproxygoogle/gemini-3-flash-preview` | Fast, 1M context |
| `cliproxygoogle/gemini-2.5-flash` | Balanced, 1M context |
| `cliproxygoogle/gemini-2.5-flash-lite` | Lightweight, 1M context |
| `cliproxygoogle/gemini-2.5-computer-use-preview-10-2025` | Computer use, 1M context |

### GPT (via cliproxygpt)

| Model | Features |
|-------|----------|
| `cliproxygpt/gpt-5.2` | Medium reasoning, 400K context |
| `cliproxygpt/gpt-5.2-codex` | Code-optimized, medium reasoning, 400K context |
| `cliproxygpt/gpt-5.1` | Medium reasoning, 400K context |
| `cliproxygpt/gpt-5.1-codex` | Code-optimized, medium reasoning, 400K context |
| `cliproxygpt/gpt-5.1-codex-max` | High effort reasoning, 400K context |
| `cliproxygpt/gpt-5.1-codex-mini` | Low effort reasoning, 400K context |
| `cliproxygpt/gpt-5` | Medium reasoning, 400K context |
| `cliproxygpt/gpt-5-codex` | Code-optimized, medium reasoning, 400K context |
| `cliproxygpt/gpt-5-codex-mini` | Low effort reasoning, 400K context |

## Usage

### Set Default Model

In your `opencode.jsonc`:

```jsonc
{
  "model": "cliproxy/claude-sonnet-4-5-thinking"
}
```

### Switch Models

Use the model picker in OpenCode (usually `Ctrl+M` or via command palette) to switch between models during a session.

## Model Selection Guide

| Use Case | Recommended Model |
|----------|-------------------|
| Complex reasoning tasks | `cliproxy/claude-opus-4-5-thinking` |
| General coding | `cliproxy/claude-sonnet-4-5-thinking` |
| Large codebase analysis | `cliproxygoogle/gemini-3-pro-preview` (1M context) |
| Quick tasks | `cliproxygoogle/gemini-3-flash-preview` |
| Code generation | `cliproxygpt/gpt-5.1-codex` |
| Deep analysis | `cliproxygpt/gpt-5.1-codex-max` |
