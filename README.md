# AuraCite MCP Server (Preview)

> Native [Model Context Protocol](https://modelcontextprotocol.io) server for AI visibility data. Planned to let Claude Desktop, Cline, Continue or any MCP client query real-time Generative Engine Optimization metrics from your [AuraCite](https://auracite.de) projects.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-preview-orange)](#roadmap)

## Status: Preview

This repository is a placeholder for the upcoming public `@getauracite/mcp-server` NPM package.

**What is live today**

- Roadmap and planned tool surface (below)
- Public design decisions and change log

**What is not live yet**

- The NPM package `@getauracite/mcp-server`
- A stable MCP tool contract
- A public API key flow for MCP usage

We will flip this repo to a working implementation **once the underlying AuraCite public API is stable** and we can commit to backwards-compatible MCP tool names.

Want to be notified? Star the repo or email <g@auracite.de>.

## Planned: what it will do

The AuraCite MCP Server will expose AI visibility analytics as MCP tools so any MCP-compatible AI agent can ask questions like:

> What is my brand`s AI visibility score across ChatGPT and Perplexity?
>
> Which competitors do LLMs recommend instead of us?
>
> Show me the last 30 days of citation trend for Brand X.

…and get real, empirical data back — not hallucinations.

## Roadmap

- [ ] v0.1 — read-only tools: get visibility score, list recent citations
- [ ] v0.2 — comparison: competitor share-of-voice
- [ ] v0.3 — time-series: mention trend
- [ ] v0.4 — OAuth flow (replacing static API keys)
- [ ] v1.0 — stable tool contract, published on NPM

Detailed tool contracts will land in this repo **with a real implementation**, not before.

## Why MCP?

LLMs hallucinate when asked about brand authority. With MCP, AI agents can call **verified data sources** instead of guessing. We believe this is where AI-assisted research is going, and we want AuraCite to be a first-class data source for it.

## License

MIT

## About AuraCite

[AuraCite](https://auracite.de) is an analytics platform for Generative Engine Optimization.

- Website: [auracite.de](https://auracite.de)
- Contact: <g@auracite.de>

---

**Star this repo** to get notified when v0.1 ships.