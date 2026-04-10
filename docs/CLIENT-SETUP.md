# Client Setup

## Codex
- Live config file: `~/.codex/config.toml`
- Template source: `~/.agent-stack/templates/codex/config.toml`
- Prefer `~/.agent-stack/bin/sync-agent-stack` over manual edits.
- Current managed entries: `openaiDeveloperDocs`

## Cursor
- Live config file: `~/.cursor/mcp.json`
- Template source: `~/.agent-stack/templates/cursor/mcp.json`
- Prefer `~/.agent-stack/bin/sync-agent-stack` over manual edits.
- Current managed entries: `openaiDeveloperDocs`, Keychain-backed `github`

## Claude Code
- Use the Claude MCP CLI for durable setup when possible.
- Template notes: `~/.agent-stack/templates/claude-code/README.md`
- Prefer user scope for personal tools and project scope for repo-specific tools.
- Current managed entries: `openaiDeveloperDocs`

## Antigravity
- Open Manage MCP Servers.
- Open the raw MCP config editor.
- Use `~/.agent-stack/templates/antigravity/mcp_config.json` as the source template.
- Prefer `~/.agent-stack/bin/sync-agent-stack` over manual edits.
- Current managed entries: `openaiDeveloperDocs`, Keychain-backed `github-mcp-server`

## Shared rule
- All clients should point to the same MCP servers and shared Keychain-backed secret loader.
- Do not duplicate server logic per client.
