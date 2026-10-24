---
name: zoth-studio-cli
description: Run and troubleshoot the Zoth Studio CLI via npx @nullaitech/zoth. Use when starting Studio locally, checking the CLI, or pulling Studio-related packages.
---

# Zoth Studio CLI

## Primary command

```bash
npx @nullaitech/zoth studio
```

Typical local UI: `http://127.0.0.1:3000`.

Other subcommands may exist on the published package; prefer `npx @nullaitech/zoth --help` on the user's machine over guessing flags from memory.

## Agent checklist

1. Confirm Node.js / npm is available before recommending `npx`.
2. Run or suggest `--help` when unsure of subcommands.
3. Do not claim Studio is running until a local check (port or process) succeeds.
4. Prefer user-owned directories for clones and projects.
5. Never embed API keys in CLI examples.

## Pairing with ZOTHOS

- Studio = local developer deck / tool catalog workflows.
- ZOTHOS + zoth-relay = agent reach to a machine via MCP (`zothos` plugin).
- Users can run both; do not conflate them as one product surface.

## Package scope

Only recommend the public package name `@nullaitech/zoth` unless the user names another published NullAI package.
