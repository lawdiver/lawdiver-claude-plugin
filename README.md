# LawDiver — Claude plugin

Official Claude Code / Cowork plugin for [LawDiver](https://lawdiver.com): search and verify U.S. federal and state caselaw, statutes, and citations.

This repository is the **public Claude plugin package**. It is separate from the OpenAI / ChatGPT / Codex plugin surfaces. It does not modify those packages.

## What’s included

| Component | Purpose |
|---|---|
| Remote MCP (`https://lawdiver.com/mcp`) | Tools: search, retrieve case/statute/opinion, interactive viewer (`view_case`, `view_authority`), citation checks, good-law, statute browse/citing cases, jurisdictions |
| Skills | `setup`, `caselaw-research`, `retrieve-opinion`, `check-citation-good-law`, `retrieve-statute`, `view-case-or-authority` |

### MCP tools (live at `/mcp`)

`search_cases`, `retrieve_case`, `retrieve_statute`, `get_statute_citing_cases`, `browse_statute`, `get_case`, `get_opinion_text`, `get_good_law`, `goodlaw_check`, `check_citation`, `list_jurisdictions`, `view_case`, `view_authority`

`view_case` / `view_authority` open LawDiver’s interactive viewer on Claude web and desktop (opinion or authority text, good-law badges, Cited by). Other clients still receive the structured tool result. Full catalog: https://lawdiver.com/mcp/toolspec.json

## Install

```bash
/plugin install lawdiver
```

Or install **LawDiver** from Claude Code / Cowork Plugins UI, then authenticate via `/mcp` (OAuth).

Local checkout (development):

```bash
claude --plugin-dir .
```

Then run `/mcp`, authenticate **lawdiver**, and try:

> Using LawDiver, is Chevron still good law? Open the case in the viewer.

## Authentication

- **Preferred:** OAuth through `/mcp` after enabling the plugin (no key paste).
- **Manual (Claude Code only):** API key header — see https://lawdiver.com/products/mcp

Create an account at https://lawdiver.com if you do not already have one.

## Documentation

- Product / MCP setup: https://lawdiver.com/products/mcp
- Claude connect guide: https://lawdiver.com/products/mcp/connect-claude
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
