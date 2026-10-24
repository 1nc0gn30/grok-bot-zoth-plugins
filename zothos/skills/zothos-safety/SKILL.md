---
name: zothos-safety
description: Safety and least-privilege rules when using zoth-relay MCP tools (status, list_dir, read_file, write_file, run_command) on a remote machine. Use before destructive file or shell actions through ZOTHOS.
---

# ZOTHOS / zoth-relay safety

The relay can read files, write files, and run commands on a real machine. Treat every call as privileged.

## Rules

1. **Confirm the host** with `status` before mutating anything.
2. **Prefer read-only first**: `list_dir` / `read_file` over `write_file` / `run_command`.
3. **No secrets in prompts or commits**: never echo `ZOTH_RELAY_TOKEN`, private keys, `.env` contents, or session cookies into logs.
4. **Least privilege commands**: avoid `rm -rf`, disk wipes, firewall flushes, or mass `chmod` unless the user explicitly asked for that exact action.
5. **Scope writes**: write only to paths the user named; do not "clean up" unrelated directories.
6. **No credential theft paths**: do not scrape browser profiles, SSH agents, or password stores through the relay.
7. **Irreversible actions need explicit user approval**: deleting data, sending messages as the user, purchasing, or exposing the host to the public internet.
8. **Do not claim official partnership** with xAI, Cursor, or other vendors — NullAI Tech ships this plugin independently.

## When something fails

- `401` / auth errors → token wrong or revoked; reconfigure `ZOTH_RELAY_TOKEN`.
- Connection errors → check `ZOTH_RELAY_URL` (base only) and that `{base}/mcp` is reachable.
- Missing tools → relay build/version mismatch; do not invent fake tool names.

## Disclosure

This plugin connects outbound to the URL the user configures. There is no NullAI telemetry in the plugin package itself.
