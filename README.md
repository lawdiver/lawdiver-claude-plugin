# LawDiver — Claude plugin

Official Claude Code / Cowork plugin for [LawDiver](https://lawdiver.com): search and verify U.S. federal and state caselaw, statutes, and citations.

This repository is the **public Claude plugin package**. It is separate from the OpenAI / ChatGPT / Codex plugin surfaces. It does not modify those packages.

## What’s included

| Component | Purpose |
|---|---|
| Remote MCP (`https://lawdiver.com/mcp`) | Tools: search, retrieve case/statute/opinion, check citations, good-law, jurisdictions |
| Skills | `setup`, `caselaw-research`, `retrieve-opinion`, `check-citation-good-law`, `retrieve-statute` |

## Install (after directory listing)

Once published in Anthropic’s plugin directory / community marketplace, install from Claude Code or Cowork using the in-product Plugins UI, then authenticate LawDiver via `/mcp` (OAuth).

Until then, test locally:

```bash
claude --plugin-dir .
# or from a parent folder:
claude --plugin-dir ./plugins/claude-lawdiver
```

Then run `/mcp`, authenticate **lawdiver**, and try:

> Using LawDiver, is 410 U.S. 113 still good law?

## Authentication

- **Preferred:** OAuth through `/mcp` after enabling the plugin (no key paste).
- **Manual (Claude Code only):** API key header — see https://lawdiver.com/products/mcp

Create an account at https://lawdiver.com if you do not already have one.

## Documentation

- Product / MCP setup: https://lawdiver.com/products/mcp
- Privacy: https://lawdiver.com/privacy
- Terms: https://lawdiver.com/terms

## Privacy

LawDiver processes legal-research queries you send through the MCP tools under our [Privacy Policy](https://lawdiver.com/privacy). The plugin itself stores no API keys and does not run local binaries beyond Claude’s MCP client connecting to `https://lawdiver.com/mcp`.

## License

MIT — see [LICENSE](./LICENSE).

## Validate

```bash
claude plugin validate .
```
