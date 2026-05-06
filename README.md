# AuraCite MCP Server Preview

> Preview roadmap for [Model Context Protocol](https://modelcontextprotocol.io) workflows around AI visibility data. Public self-service installation is not generally available yet.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-preview-orange)](#roadmap)

## Status: Preview

This repository tracks the public preview direction for AuraCite MCP-ready workflows. The goal is to expose **authorized AI visibility analytics** to supported MCP clients after package, endpoint, authentication, and customer documentation are ready.

Target workflows include questions such as:

> What is my brand's AI visibility score across ChatGPT and Perplexity?
>
> Which competitors do LLMs recommend instead of us?
>
> Show me the last 30 days of citation trend for Brand X.

...and get measured data back, not guesses.

The production contract is still being finalized. Do not treat this repository as an installable npm package until a tagged release says so.

## Why MCP?

LLMs can be unreliable when asked about brand authority. With MCP, AI agents can call authorized data sources instead of guessing.

## Current Status

- Public npm package: not generally advertised yet
- Public self-service endpoint: not generally advertised yet
- Access model: authorized packages and integrations
- Contact: `g@auracite.de`

## Planned Installation Pattern

Once released, supported clients will receive package-specific setup instructions similar to:

```json
{
  "mcpServers": {
    "auracite_geo": {
      "configured_by": "AuraCite after API/MCP access is enabled"
    }
  }
}
```

Actual endpoint and authentication details will be published only after release.

## Planned Capability Areas

- Visibility score retrieval for authorized brands
- Competitor / Share of AI Voice summaries
- Citation and source analysis
- Mention tracking across configured engines
- GEO recommendation summaries

## Development

Implementation details will be added after the public server contract is stable.

## Security

- API keys are never logged
- All requests over HTTPS/TLS
- EU-hosted with GDPR-oriented processing
Security policy details will be added with the first public implementation.

## Roadmap

- [ ] Public package release
- [ ] Stable authentication model
- [ ] `get_visibility_score`
- [ ] `compare_competitors`
- [ ] `get_citations`
- [ ] `suggest_improvements`
- [ ] `track_over_time`
- [ ] Streaming responses for long queries
- [ ] Rate-limit feedback via MCP
- [ ] OAuth support (vs. API keys)

## Contributing

PRs will be welcome once the first public implementation is available.

## License

MIT

## About AuraCite

[AuraCite](https://auracite.de) is an analytics platform for Generative Engine Optimization with MCP-ready workflows for brand visibility data.

- [auracite.de](https://auracite.de)
- <g@auracite.de>

---

**Star this repo** if you find it useful; it helps other developers discover the MCP + GEO ecosystem.
