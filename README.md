# AuraCite MCP Server

> Hosted [Model Context Protocol](https://modelcontextprotocol.io) server for AI visibility / GEO analytics — ask how AI engines mention, cite, rank, and describe your brand, and get measured data back, not guesses.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-live-brightgreen)](#installation)
[![MCP Registry](https://img.shields.io/badge/MCP_Registry-de.auracite%2Fai--visibility-6e56cf)](https://registry.modelcontextprotocol.io/v0/servers?search=de.auracite/ai-visibility)

## Status: Live

The AuraCite MCP server is in production:

- **Endpoint:** `https://auracite.de/mcp/rpc` (Streamable HTTP) · `https://auracite.de/mcp/sse` (SSE)
- **Auth:** OAuth 2.0 with dynamic client registration — sign in with your AuraCite account, approve scoped access. No API keys to paste.
- **Registry:** listed in the official MCP registry as [`de.auracite/ai-visibility`](https://registry.modelcontextprotocol.io/v0/servers?search=de.auracite/ai-visibility)
- **Tools:** 45 read-mostly tools, all annotated (`readOnlyHint` / `destructiveHint`)
- **Docs:** [auracite.de/mcp-integration.html](https://auracite.de/mcp-integration.html)

Example questions your agent can answer with it:

> What is my brand's AI visibility score across ChatGPT, Gemini, and Perplexity?
>
> Which competitors do LLMs recommend instead of us, and which sources do they cite?
>
> Show me my Google Search Console top queries and the device/country breakdown for the last 30 days.

## Installation

### Claude Code (plugin)

```bash
claude plugin marketplace add getauracite/claude-plugins
claude plugin install auracite-agent-hub@auracite
```

Then run `/mcp` to OAuth-connect. Plugin source: [getauracite/claude-plugins](https://github.com/getauracite/claude-plugins).

### Claude.ai / Claude Desktop (custom connector)

Settings → Connectors → *Add custom connector* → URL `https://auracite.de/mcp/rpc` → sign in via OAuth.

### Cursor

[![Add AuraCite to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=AuraCite&config=eyJ1cmwiOiJodHRwczovL2F1cmFjaXRlLmRlL21jcC9ycGMifQ==)

Or manually in `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "auracite": { "url": "https://auracite.de/mcp/rpc" }
  }
}
```

### OpenAI Codex (plugin)

```bash
codex plugin marketplace add getauracite/codex-plugins
codex plugin add auracite-agent-hub@auracite-marketplace
```

Plugin source: [getauracite/codex-plugins](https://github.com/getauracite/codex-plugins).

### Continue

```yaml
mcpServers:
  - name: AuraCite
    type: streamable-http
    url: https://auracite.de/mcp/rpc
```

### Any other MCP client

Generic config — Streamable HTTP with OAuth:

```json
{
  "mcpServers": {
    "auracite": {
      "type": "http",
      "url": "https://auracite.de/mcp/rpc"
    }
  }
}
```

## Capability Areas

- **AI visibility:** visibility score, AI engine breakdown, mentions, citations, share of voice, trends, brand comparison
- **Search data:** Google Search Console top queries / top pages / search analytics / trend / country & device breakdown
- **Competitive intelligence:** competitor lists, opportunity briefs, intelligence freshness and refresh status
- **Workflow (guarded):** prompt catalog management, scan triggers, action handoffs, project memory — write/spend tools require explicit OAuth scopes (`mcp:write`, `mcp:spend`), server-issued confirmations, idempotency, and audit events

## Security

- OAuth 2.0 with dynamic client registration; scoped access (`mcp:read` by default)
- Read-only by default — mutating, cost-bearing, admin, and bulk tools stay disabled without explicit scopes
- Provider-spend tools are capped by CostGuard (hard daily limits) and per-call credit/USD caps
- All requests over HTTPS/TLS; API keys (when used instead of OAuth) are never logged
- EU-hosted with GDPR-oriented processing — [privacy](https://auracite.de/datenschutz) · [terms](https://auracite.de/terms)

## License

MIT

## About AuraCite

[AuraCite](https://auracite.de) is an analytics platform for Generative Engine Optimization (GEO): it tracks how ChatGPT, Gemini, Perplexity, and Google AI answers mention, rank, and cite brands — and turns that evidence into actions.

- [auracite.de](https://auracite.de)
- `g@auracite.de`

---

**Star this repo** if you find it useful; it helps other developers discover the MCP + GEO ecosystem.
