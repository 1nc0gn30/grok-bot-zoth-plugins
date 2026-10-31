# grok-bot-zoth-plugins

Public **Cursor / Grok Bot** multi-plugin marketplace package for **NullAI Tech**.

| Plugin | Purpose |
| --- | --- |
| [`zothos`](./zothos/) | zoth-relay MCP → reach a machine (`status`, files, `run_command`) |
| [`zoth-studio`](./zoth-studio/) | Skills for Zoth Studio + `npx @nullaitech/zoth` (no bundled MCP) |

Marketplace id: **`nullai-zoth`** (see [`.cursor-plugin/marketplace.json`](./.cursor-plugin/marketplace.json)).

## Install (after marketplace approval)

Install from the Cursor / Grok Bot Connect Apps marketplace when listed, or point a team marketplace at this public repo.

For **zothos**, set under Plugins → Configure:

- `ZOTH_RELAY_URL` — relay base URL (no trailing slash)
- `ZOTH_RELAY_TOKEN` — bearer token (never commit)

## Repository layout

```text
grok-bot-zoth-plugins/
├── .cursor-plugin/marketplace.json
├── zothos/
│   ├── .cursor-plugin/plugin.json
│   ├── mcp.json
│   ├── assets/logo.svg
│   ├── skills/
│   └── README.md
├── zoth-studio/
│   ├── .cursor-plugin/plugin.json
│   ├── assets/logo.svg
│   ├── skills/
│   └── README.md
├── SUBMISSION.md
└── README.md
```

## Submit for Connect Apps

See **[SUBMISSION.md](./SUBMISSION.md)** for form field drafts for:

- https://cursor.com/marketplace/publish
- https://x.ai/bot/marketplace/submit-a-plugin

Do not imply partnership with xAI or Cursor.

## Related (different runtime)

- Hermes community plugin: https://github.com/1nc0gn30/hermes-zoth

## License

MIT — NullAI (1nc0gn30)
