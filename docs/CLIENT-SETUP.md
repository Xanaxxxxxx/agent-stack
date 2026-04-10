# Client Setup

Client setup is intentionally asymmetric. Each client should get only the MCP entries that make sense for that client.

## Codex

Live config:

- `~/.codex/config.toml`

Managed by sync:

- `openaiDeveloperDocs`

Notes:

- Codex already has strong built-in plugin coverage for some domains.
- The sync policy avoids layering duplicate GitHub or Figma MCP entries on top of those built-ins.

## Cursor

Live config:

- `~/.cursor/mcp.json`

Managed by sync:

- `openaiDeveloperDocs`
- Keychain-backed `github`

Notes:

- Cursor is expected to consume the shared GitHub MCP path from this repo.

## Claude Code

Live config:

- `~/.claude.json`

Managed by sync:

- `openaiDeveloperDocs`

Notes:

- Claude Code configuration is intentionally minimal.
- Network access to the remote OpenAI MCP endpoint may still vary by environment.

## Antigravity

Live config:

- `~/.gemini/antigravity/mcp_config.json`

Managed by sync:

- `openaiDeveloperDocs`
- Keychain-backed `github-mcp-server`

Preserved but not managed by this repo:

- existing non-agent-stack MCP entries, such as local or vendor-specific integrations

## Policy

- Shared logic belongs in this repo, not duplicated across clients.
- Live configs may differ, but they should differ for explicit reasons.
- The sync script is the preferred interface for applying managed entries.
