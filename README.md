# OCX Provider Registry

[![Registry](https://img.shields.io/badge/registry-live-brightgreen)](https://ocx-provider-registry.knn07.workers.dev)
[![GitHub](https://img.shields.io/github/license/KNN-07/ocx-provider)](https://github.com/KNN-07/ocx-provider)

Proxied AI model providers for [OpenCode](https://opencode.ai). Access Claude, Google Gemini, and GPT models through your local proxy server.

**Registry URL:** https://ocx-provider-registry.knn07.workers.dev

## Installation

```bash
# Add the registry (one-time)
ocx registry add https://ocx-provider-registry.knn07.workers.dev --name norman-proxy

# Install all providers
ocx add norman-proxy/all-providers

# Or install individually
ocx add norman-proxy/claude-proxy
ocx add norman-proxy/google-proxy
ocx add norman-proxy/gpt-proxy
```

## Components

| Component | Description |
|-----------|-------------|
| `norman-proxy/claude-proxy` | Claude Opus 4.5, Sonnet 4.5 (with thinking variants) |
| `norman-proxy/google-proxy` | Google Gemini 3 Pro, 3 Flash, 2.5 variants |
| `norman-proxy/gpt-proxy` | OpenAI GPT 5.x series with reasoning |
| `norman-proxy/all-providers` | Bundle: All providers above |

## Configuration

### Required Environment Variables

Set these before using the proxied models:

```bash
export PROXY_API_KEY="your_api_key"
export PROXY_BASE_URL="http://localhost:8317"
```

### Set Default Model

In your `opencode.jsonc`:

```jsonc
{
  "model": "cliproxyanthropic/claude-sonnet-4-5-thinking"
}
```

## Available Models

### Claude (cliproxyanthropic)

| Model | Description |
|-------|-------------|
| `cliproxyanthropic/claude-opus-4-5-thinking` | Claude Opus 4.5 with extended thinking (200K context) |
| `cliproxyanthropic/claude-sonnet-4-5` | Claude Sonnet 4.5 (200K context) |
| `cliproxyanthropic/claude-sonnet-4-5-thinking` | Claude Sonnet 4.5 with extended thinking (200K context) |

### Google Gemini (cliproxygoogle)

| Model | Description |
|-------|-------------|
| `cliproxygoogle/gemini-3-pro-preview` | Gemini 3 Pro Preview with reasoning (1M context) |
| `cliproxygoogle/gemini-3-pro-image-preview` | Gemini 3 Pro Image Preview (1M context) |
| `cliproxygoogle/gemini-3-flash-preview` | Gemini 3 Flash Preview (1M context) |
| `cliproxygoogle/gemini-2.5-flash` | Gemini 2.5 Flash (1M context) |
| `cliproxygoogle/gemini-2.5-flash-lite` | Gemini 2.5 Flash Lite (1M context) |
| `cliproxygoogle/gemini-2.5-computer-use-preview-10-2025` | Gemini 2.5 Computer Use (1M context) |

### GPT (cliproxyopenai)

| Model | Description |
|-------|-------------|
| `cliproxyopenai/gpt-5.2` | GPT 5.2 with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5.2-codex` | GPT 5.2 Codex with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5.1` | GPT 5.1 with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5.1-codex` | GPT 5.1 Codex with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5.1-codex-max` | GPT 5.1 Codex with high effort reasoning (400K context) |
| `cliproxyopenai/gpt-5.1-codex-mini` | GPT 5.1 Codex with low effort reasoning (400K context) |
| `cliproxyopenai/gpt-5` | GPT 5 with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5-codex` | GPT 5 Codex with medium reasoning (400K context) |
| `cliproxyopenai/gpt-5-codex-mini` | GPT 5 Codex with low effort reasoning (400K context) |

## Development

```bash
# Install dependencies
bun install

# Build the registry
bun run build

# Local development server
bun run dev

# Deploy to Cloudflare Workers
bun run deploy
```

## Self-Hosting

### Cloudflare Workers (Recommended)

```bash
npx wrangler login
bun run deploy
```

### Vercel

Push to GitHub and connect to Vercel. Config is in `vercel.json`.

### Netlify

Push to GitHub and connect to Netlify. Config is in `netlify.toml`.

