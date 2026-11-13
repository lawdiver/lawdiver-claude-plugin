---
name: view-case-or-authority
description: Open a U.S. case or a statute, regulation, court rule, or constitutional provision in LawDiver’s interactive viewer so the user can read it in the side panel. Use when the user asks to see, open, view, read, or browse a case or authority. Do not use for free-form topic search (use caselaw-research) or when you only need text to quote in chat (use retrieve-opinion or retrieve-statute).
---

# Open in LawDiver viewer

Use LawDiver MCP tools only. Prefer the interactive viewer when the user wants to **see** or **open** the source; still call text tools before you quote or analyze.

## When to use

- User asks to open, view, show, read, or browse a case (citation or name)
- User asks to open a statute, CFR section, court rule, or constitutional provision
- User asks whether a known case is still good law **and** wants the viewer (Overruled / Reversed badge, Cited by)
- Prior search or cite-check returned a `caseId` or `authorityKey` and the user wants it on screen

## Steps — cases

1. Call `view_case` with `query` (citation or case name) or `caseId` from a prior tool.
2. If the result is a multi-match list, let the user pick in the viewer, or call again with one `caseId`.
3. With no arguments, `view_case` opens an empty lookup box — ask which case to open, or call again with a query.
4. `view_case` returns **metadata only**. Before you quote or analyze the opinion, call `get_opinion_text` with the confirmed `caseId`.
5. For good-law detail beyond the viewer badge, call `get_good_law` or `goodlaw_check`.

## Steps — statutes, regulations, rules, constitutions

1. Call `view_authority` with a Bluebook citation that includes a section number (e.g. `42 U.S.C. § 1983`, `Fed. R. Civ. P. 12`, `29 C.F.R. § 1630.2`), or with `authorityKey` from `retrieve_statute` / `check_citation`.
2. The tool result often includes section text you can quote. If text is unavailable, say so and do not invent the provision.
3. For more citing cases or code neighbours outside the viewer, use `get_statute_citing_cases` or `browse_statute` with `authorityKey`.

## Do not

- Treat the viewer as a substitute for `get_opinion_text` when you need to quote case language in chat
- Call `view_case` for statutes/rules (use `view_authority`) or `view_authority` for cases (use `view_case`)
- Fabricate opinion or statutory text if the tools return unavailable or empty
