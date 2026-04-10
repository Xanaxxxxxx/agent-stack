# Workflows

## Add a new MCP server
1. Add it to `mcp/registry/base.mcp.json`.
2. Prefer the Keychain wrapper over plaintext secret files when the server needs credentials.
3. Copy or adapt the server entry into each client config only when needed.
4. Prefer project-level config for repo-specific tools.

## Add a new client
1. Keep the client config thin.
2. Point it to the same MCP server definitions.
3. Make the client read this Markdown layer first.
4. Avoid duplicating workflow logic inside client-specific prompts.

## Sync managed clients
1. Run `~/.agent-stack/bin/sync-agent-stack`.
2. The sync script detects supported clients by their install or config footprint.
3. It only manages explicitly approved MCP entries.
4. It does not try to infer whether a built-in plugin is fully equivalent to an MCP server.

## Current sync policy
1. `Codex`: ensure `openaiDeveloperDocs` only.
2. `Cursor`: ensure `openaiDeveloperDocs` and Keychain-backed `github`.
3. `Claude Code`: ensure `openaiDeveloperDocs` only.
4. `Antigravity`: ensure `openaiDeveloperDocs` and Keychain-backed `github-mcp-server`.

## Add a new project
1. Keep machine-wide tools in `~/.agent-stack`.
2. Add repo docs such as `AGENTS.md`, `docs/commands.md`, and `docs/coding-standards.md` in the project.
3. Add repo-local MCP config only for tools that depend on that repo.
