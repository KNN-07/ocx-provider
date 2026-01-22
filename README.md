# OCX Provider Registry

Proxied AI model providers for OpenCode. Includes Claude, Google Gemini, and GPT models via your local proxy server.

## Quick Start

```bash
# Install dependencies
bun install

# Build the registry
bun run build

# Local development
bun run dev
```

## Components

| Component | Description |
|-----------|-------------|
| `norman-proxy/claude-proxy` | Claude models (Opus 4.5, Sonnet 4.5 with thinking) |
| `norman-proxy/google-proxy` | Google Gemini models (3 Pro, 3 Flash, 2.5 variants) |
| `norman-proxy/gpt-proxy` | OpenAI GPT models (5.x series with reasoning) |
| `norman-proxy/all-providers` | Bundle: All providers above |

## Installation

After deploying, users can add your registry:

```bash
# Add the registry
ocx registry add https://your-registry.workers.dev --name norman-proxy

# Install all providers
ocx add norman-proxy/all-providers

# Or install individually
ocx add norman-proxy/claude-proxy
ocx add norman-proxy/google-proxy
ocx add norman-proxy/gpt-proxy
```

## Required Environment Variables

Users need to set these before using the proxied models:

```bash
export PROXY_API_KEY="your_api_key"
export PROXY_BASE_URL="http://localhost:8317"
```

## Available Models

### Claude (cliproxy)
- `cliproxy/claude-opus-4-5-thinking`
- `cliproxy/claude-sonnet-4-5`
- `cliproxy/claude-sonnet-4-5-thinking`

### Google Gemini (cliproxygoogle)
- `cliproxygoogle/gemini-3-pro-preview`
- `cliproxygoogle/gemini-3-pro-image-preview`
- `cliproxygoogle/gemini-3-flash-preview`
- `cliproxygoogle/gemini-2.5-flash`
- `cliproxygoogle/gemini-2.5-flash-lite`
- `cliproxygoogle/gemini-2.5-computer-use-preview-10-2025`

### GPT (cliproxygpt)
- `cliproxygpt/gpt-5.2`
- `cliproxygpt/gpt-5.2-codex`
- `cliproxygpt/gpt-5.1`
- `cliproxygpt/gpt-5.1-codex`
- `cliproxygpt/gpt-5.1-codex-max`
- `cliproxygpt/gpt-5.1-codex-mini`
- `cliproxygpt/gpt-5`
- `cliproxygpt/gpt-5-codex`
- `cliproxygpt/gpt-5-codex-mini`

## Deploy

### Cloudflare Workers (Recommended)

```bash
bun run deploy
```

### Vercel

Push to GitHub and connect to Vercel. Config is in `vercel.json`.

### Netlify

Push to GitHub and connect to Netlify. Config is in `netlify.toml`.

## License

MIT
