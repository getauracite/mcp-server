# AuraCite MCP Server

> Native [Model Context Protocol](https://modelcontextprotocol.io) server for AI visibility data. Connect Claude Desktop, ChatGPT-via-MCP, or any MCP client to query real-time Generative Engine Optimization metrics.

[![NPM](https://img.shields.io/npm/v/@getauracite/mcp-server.svg)](https://www.npmjs.com/package/@getauracite/mcp-server)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![MCP](https://img.shields.io/badge/MCP-compatible-green.svg)](https://modelcontextprotocol.io)

## What is this?

The AuraCite MCP Server exposes **AI visibility analytics** as MCP tools that any MCP-compatible AI agent can call. Ask Claude Desktop things like:

> "What's my brand's AI visibility score across ChatGPT and Perplexity?"
>
> "Compare the Share of AI Voice between Stripe and Adyen."
>
> "Which competitors does ChatGPT recommend instead of us?"

And get real, empirical data back — not hallucinations.

## Why MCP?

LLMs hallucinate when asked about brand authority. With MCP, AI agents can call **verified data sources** (like AuraCite) instead of guessing. This is the future of accurate AI-assisted research.

## Installation

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "auracite_geo": {
      "command": "npx",
      "args": ["-y", "@getauracite/mcp-server"],
      "env": {
        "AURACITE_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

Restart Claude Desktop. You should see the AuraCite tools available.

### Get an API key

1. Sign up at [auracite.de](https://auracite.de)
2. Go to Settings → API Keys
3. Generate a new key with scope `mcp:read`
4. Copy into your `claude_desktop_config.json`

Free tier: 100 MCP calls/month. Paid plans from €49/month.

## Exposed Tools

### `auracite_get_visibility_score`

Get the AI Visibility Score (1–100) for a brand across all tracked engines.

**Parameters:**
- `brand_name` (string, required)
- `engines` (array, optional) — default: `["chatgpt", "claude", "perplexity", "gemini"]`
- `locale` (string, optional) — default: `"en"`

**Example:**
```
Claude: "What's Stripe's AI visibility score?"
→ Calls auracite_get_visibility_score({ brand_name: "Stripe" })
→ Returns: { overall: 87, chatgpt: 92, claude: 85, perplexity: 81, gemini: 90 }
```

### `auracite_compare_competitors`

Compare Share of AI Voice between multiple brands.

**Parameters:**
- `brands` (array, required) — 2–5 brand names
- `topic` (string, required) — e.g. "payment processors"

### `auracite_get_citations`

Get the exact URLs that LLMs cite when discussing a brand.

**Parameters:**
- `brand_name` (string, required)
- `engine` (string, optional) — specific engine or "all"

### `auracite_suggest_improvements`

Get actionable GEO recommendations based on current visibility data.

**Parameters:**
- `brand_name` (string, required)

## Development

```bash
git clone https://github.com/getauracite/mcp-server
cd mcp-server
npm install
npm run build
npm run dev
```

Test locally:
```bash
AURACITE_API_KEY=xxx npx @modelcontextprotocol/inspector npx @getauracite/mcp-server
```

## Security

- API keys are never logged
- All requests over TLS 1.3
- GDPR-compliant, EU-hosted
- [Security policy](SECURITY.md)

## Roadmap

- [x] `get_visibility_score`
- [x] `compare_competitors`
- [x] `get_citations`
- [ ] `suggest_improvements` (Q2 2026)
- [ ] `track_over_time` (Q2 2026)
- [ ] Streaming responses for long queries
- [ ] Rate-limit feedback via MCP
- [ ] OAuth support (vs. API keys)

## Contributing

PRs welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT

## About AuraCite

[AuraCite](https://auracite.de) is the operating system for Generative Engine Optimization. We're the first platform to offer a native MCP server for brand visibility data.

- 🌐 [auracite.de](https://auracite.de)
- 🐦 [@AuraCite](https://twitter.com/AuraCite)
- 📧 hello@auracite.de

---

**⭐ Star this repo** if you find it useful — it helps other developers discover the MCP + GEO ecosystem.
