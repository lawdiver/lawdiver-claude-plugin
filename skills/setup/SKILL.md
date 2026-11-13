---
name: setup
description: Guide the user through authenticating the LawDiver MCP connector bundled with this plugin. Use when the plugin is newly installed, LawDiver tools fail with auth errors, or the user asks how to connect LawDiver.
---

# Set up LawDiver (Claude Code / Cowork)

This plugin bundles a remote MCP connector at `https://lawdiver.com/mcp`. It ships **no API keys**. Authenticate with OAuth after install.

## Prerequisites

- A LawDiver account (free signup at https://lawdiver.com)
- Claude Code, or Cowork with plugins enabled

## Claude Code

1. Confirm the plugin is enabled (`/plugin` → Installed, or `claude plugin list`).
2. Run `/mcp`, select the **lawdiver** server from this plugin, and choose **Authenticate**.
3. Complete LawDiver sign-in in the browser and allow access.
4. Confirm tools appear, including: `search_cases`, `retrieve_case`, `retrieve_statute`, `view_case`, `view_authority`, `get_case`, `get_opinion_text`, `get_good_law`, `goodlaw_check`, `check_citation`, `get_statute_citing_cases`, `browse_statute`, `list_jurisdictions`.

## Cowork

1. Install or enable the LawDiver plugin from Customize → Plugins.
2. When prompted to connect the connector, complete LawDiver OAuth sign-in.
3. Manage the connector from the plugin’s connector page if you need to re-auth.

## Verify

Ask: “Using LawDiver, is Chevron still good law? Open the case in the viewer.” Claude should call LawDiver (`view_case` and/or `get_good_law`) and answer from tool results only. On Claude web and desktop, the interactive case viewer can open.

## Re-authenticate

- Claude Code: `/mcp` → lawdiver → clear auth / re-authenticate.
- Cowork: sign out and back in from the plugin connector page.

## Do not

- Paste long-lived API keys into chat unless the user explicitly chooses the manual Claude Code header flow documented at https://lawdiver.com/products/mcp
- Claim tools work before authentication succeeds
