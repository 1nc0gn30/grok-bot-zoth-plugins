---
name: zoth-studio-workflows
description: Guide users through Zoth Studio local-first workflows (Studio UI, Adytum planning, Vault keys, Hangar tools). Use when the user wants Zoth Studio help, localhost:3000, or in-browser NullAI tools.
---

# Zoth Studio workflows

Zoth Studio is a sovereign, local-first developer studio from NullAI Tech.

## Canonical entry points

- Web catalog / hosted Studio pages: https://zoth.nullai.tech
- Local Studio UI (typical): `http://127.0.0.1:3000` after `npx @nullaitech/zoth studio`
- Product overview: https://nullai.tech/zoth

## How to help

1. Clarify whether the user wants **in-browser tools** at zoth.nullai.tech or a **local Studio** process.
2. For local: prefer the CLI skill (`zoth-studio-cli`) and verify something is listening on the ports they care about before claiming Studio is up.
3. For catalog tools: give the public Studio URL for the tool; do not invent unpublished tool IDs.
4. Keep API keys in the user's local Vault / env — never ask them to paste long-lived keys into chat if a vault path exists.
5. Planning-heavy work: mention Adytum-style planning before large code changes when the user is in Studio.

## What this plugin does not do

- It does **not** ship a hosted MCP URL (none is bundled; do not invent one).
- It is **not** the Hermes plugin `hermes-zoth` (different agent runtime).
- It does **not** grant cloud lock-in; local-first is the default story.

## Related skills

- `zoth-studio-cli` — install / run via `npx @nullaitech/zoth`
- `zoth-studio-brand` — naming and partnership guardrails
