---
name: zothos-setup
description: Install zoth-relay, create a bearer token, and configure the ZOTHOS Cursor/Grok Bot plugin variables. Use when setting up ZOTHOS remote machine access or when ZOTH_RELAY_URL / ZOTH_RELAY_TOKEN are missing.
---

# ZOTHOS / zoth-relay setup

Agents reach a machine through **zoth-relay**. This plugin talks to the relay over Streamable HTTP MCP.

## Prerequisites

- A host you control (ZOTHOS or any machine where you install the relay)
- Ability to generate a long random bearer token and keep it out of git

## Install the relay

Follow the current zoth-relay install docs for your host. Typical shape:

1. Install the `zoth-relay` binary or package on the target machine.
2. Start the relay so it listens on a URL you can reach from Cursor / Grok Bot (HTTPS recommended when remote).
3. Confirm the MCP endpoint is `{base}/mcp` (no trailing slash on `{base}`).

Stdio alternative for local-only clients:

```bash
zoth-relay mcp-stdio
```

Prefer the HTTP transport for this marketplace plugin (`mcp.json` uses `${ZOTH_RELAY_URL}/mcp`).

## Create a token

1. On the relay host, create a dedicated bearer token (do not reuse passwords).
2. Store it in a password manager or vault.
3. Never put the token in the plugin repo, screenshots, issues, or chat logs.

## Configure the plugin

In Cursor or Grok Bot: **Plugins → Configure** for `zothos`:

| Variable | Example shape | Notes |
| --- | --- | --- |
| `ZOTH_RELAY_URL` | `https://relay.example.com` | Base URL only, no `/mcp`, no trailing slash |
| `ZOTH_RELAY_TOKEN` | (secret) | Sent as `Authorization: Bearer …` |

Dashboard values substitute into `mcp.json` placeholders. The plugin never ships secret values.

## Smoke test

1. Reload plugins / reconnect MCP.
2. Call `status` (or the equivalent health tool from the relay).
3. Call `list_dir` on a harmless path you expect to exist.
4. Only then use `read_file`, `write_file`, or `run_command`.

## Tools exposed by the relay

| Tool | Purpose |
| --- | --- |
| `status` | Relay / host health |
| `list_dir` | List a directory |
| `read_file` | Read a file |
| `write_file` | Write a file |
| `run_command` | Run a shell command on the host |

If tools are missing, the relay version or auth is wrong — fix setup before inventing workarounds.

## Related

- Safety rules: skill `zothos-safety`
- Product home: https://zothos.nullai.tech
- Separate from the Hermes community plugin `hermes-zoth` (different runtime)
