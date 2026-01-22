# Proxy Provider Setup

This component configures proxied AI model endpoints for OpenCode.

## Required Environment Variables

Set these environment variables before using the proxied models:

```bash
export PROXY_API_KEY="your_api_key_here"
export PROXY_BASE_URL="http://localhost:8317"  # Your proxy server URL
```

## Available Models

After installation, you can use these models in OpenCode:

### Claude (via cliproxy)
- `cliproxy/claude-opus-4-5-thinking` - Claude Opus 4.5 with extended thinking
- `cliproxy/claude-sonnet-4-5` - Claude Sonnet 4.5
- `cliproxy/claude-sonnet-4-5-thinking` - Claude Sonnet 4.5 with extended thinking

### Google Gemini (via cliproxygoogle)
- `cliproxygoogle/gemini-3-pro-preview` - Gemini 3 Pro Preview (reasoning)
- `cliproxygoogle/gemini-3-pro-image-preview` - Gemini 3 Pro Image Preview
- `cliproxygoogle/gemini-3-flash-preview` - Gemini 3 Flash Preview
- `cliproxygoogle/gemini-2.5-flash` - Gemini 2.5 Flash
- `cliproxygoogle/gemini-2.5-flash-lite` - Gemini 2.5 Flash Lite
- `cliproxygoogle/gemini-2.5-computer-use-preview-10-2025` - Gemini 2.5 Computer Use

### GPT (via cliproxygpt)
- `cliproxygpt/gpt-5.2` - GPT 5.2 (reasoning)
- `cliproxygpt/gpt-5.2-codex` - GPT 5.2 Codex (reasoning)
- `cliproxygpt/gpt-5.1` - GPT 5.1 (reasoning)
- `cliproxygpt/gpt-5.1-codex` - GPT 5.1 Codex (reasoning)
- `cliproxygpt/gpt-5.1-codex-max` - GPT 5.1 Codex Max (high effort reasoning)
- `cliproxygpt/gpt-5.1-codex-mini` - GPT 5.1 Codex Mini (low effort reasoning)
- `cliproxygpt/gpt-5` - GPT 5 (reasoning)
- `cliproxygpt/gpt-5-codex` - GPT 5 Codex (reasoning)
- `cliproxygpt/gpt-5-codex-mini` - GPT 5 Codex Mini (low effort reasoning)

## Usage

Set your default model in `opencode.jsonc`:

```jsonc
{
  "model": "cliproxy/claude-sonnet-4-5-thinking"
}
```

Or switch models during a session using the model picker.
