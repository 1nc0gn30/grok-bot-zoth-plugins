# Marketplace submission notes

Draft fields only. **Do not auto-submit** web forms; Neal reviews and submits.

Repo: https://github.com/1nc0gn30/grok-bot-zoth-plugins

## Logos (raw URLs after push to `main`)

Replace `MAIN_SHA` with the commit SHA after push, or use the `main` branch ref if the host allows:

- ZOTHOS: `https://raw.githubusercontent.com/1nc0gn30/grok-bot-zoth-plugins/main/zothos/assets/logo.svg`
- Zoth Studio: `https://raw.githubusercontent.com/1nc0gn30/grok-bot-zoth-plugins/main/zoth-studio/assets/logo.svg`

Both are 1:1 SVG, gold `#D4AF37` on void `#08080B` with a background plate.

---

## A) Cursor — https://cursor.com/marketplace/publish

| Field | Suggested value |
| --- | --- |
| Repository URL | `https://github.com/1nc0gn30/grok-bot-zoth-plugins` |
| Format | Cursor multi-plugin (root `.cursor-plugin/marketplace.json`) |
| Marketplace name | `nullai-zoth` |
| Plugins | `zothos`, `zoth-studio` (unique) |
| Publisher / org | NullAI Tech |
| Description | ZOTHOS zoth-relay MCP and Zoth Studio local-first skills for Cursor |
| Homepage | https://nullai.tech |
| License | MIT |

### Testing steps (Cursor)

1. Clone this public repo.
2. Load / install as a multi-plugin marketplace source per current Cursor docs.
3. Enable **zothos**; set `ZOTH_RELAY_URL` + `ZOTH_RELAY_TOKEN` against a relay you control.
4. Confirm MCP tools appear; call `status` then `list_dir`.
5. Enable **zoth-studio**; ask the agent for Studio CLI help; confirm skills load and no MCP server is required.
6. Confirm logos render from `assets/logo.svg` paths.

---

## B) Grok Bot — https://x.ai/bot/marketplace/submit-a-plugin

| Field | Suggested value |
| --- | --- |
| Organization handle | `nullaitech` |
| Website URL | `https://nullai.tech` |
| Logotype URL | `https://raw.githubusercontent.com/1nc0gn30/grok-bot-zoth-plugins/main/zothos/assets/logo.svg` (or a dedicated org mark if preferred) |
| Where to be listed | **Grok Bot** and **Cursor** (both) |
| Plugin / repo URL | `https://github.com/1nc0gn30/grok-bot-zoth-plugins` |
| Summary | Independent NullAI Tech plugins: ZOTHOS (zoth-relay MCP) and Zoth Studio (skills + CLI). Not an xAI partnership. |

### Testing steps (Grok Bot)

1. After listing/review, install from Connect Apps.
2. Configure **zothos** variables; verify relay MCP.
3. Install **zoth-studio**; verify skills-only behavior.
4. Confirm no secrets are bundled in the repo (scan for tokens before each release).

---

## Disclosure language (use in forms)

> Independent plugin by NullAI Tech. Submitted for marketplace review. Not affiliated with or endorsed by xAI or Anysphere/Cursor except through normal marketplace listing.

## Checklist before submit

- [ ] Public GitHub repo
- [ ] `.cursor-plugin/marketplace.json` valid; unique plugin names
- [ ] Each plugin has `.cursor-plugin/plugin.json`, README, logo
- [ ] `zothos` declares `variables` for every `${VAR}` in `mcp.json`
- [ ] `zoth-studio` has no invented MCP URL
- [ ] Secret scan clean
- [ ] Raw logo URLs open in a private window
