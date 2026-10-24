# zothos

Cursor / Grok Bot plugin: connect to a machine through **zoth-relay** MCP.

**Homepage:** [zothos.nullai.tech](https://zothos.nullai.tech)  
**Marketplace package:** [1nc0gn30/grok-bot-zoth-plugins](https://github.com/1nc0gn30/grok-bot-zoth-plugins)

## What you get

- MCP server `zoth-relay` → `${ZOTH_RELAY_URL}/mcp` with `Authorization: Bearer ${ZOTH_RELAY_TOKEN}`
- Skills: `zothos-setup`, `zothos-safety`
- Tools on the relay: `status`, `list_dir`, `read_file`, `write_file`, `run_command`

## Configure

After install, set under **Plugins → Configure**:

1. `ZOTH_RELAY_URL` — base URL, no trailing slash (MCP path `/mcp` is appended)
2. `ZOTH_RELAY_TOKEN` — bearer token from your relay host

Local stdio (not used by this plugin's `mcp.json`, but available on the host):

```bash
zoth-relay mcp-stdio
```

## Brand

Logo: gold `#D4AF37` on void `#08080B` (`assets/logo.svg`).

## Disclaimer

Independent NullAI Tech plugin. Not affiliated with or endorsed by xAI or Cursor beyond marketplace listing review.
