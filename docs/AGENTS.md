# AGENTS

This directory defines a shared foundation for multiple AI coding clients.

Read order:
1. `README.md`
2. `docs/STACK.md`
3. `docs/WORKFLOWS.md`
4. `docs/RULES.md`

Design intent:
- MCP is the shared tool layer.
- Markdown is the shared reasoning and workflow layer.
- Each client keeps only a thin adapter config.

Operating rules:
- Reuse existing MCP servers before introducing client-specific automation.
- Prefer Keychain-backed secret loading over inline secrets or plaintext env files.
- Keep user-level tools global and project-level tools local.
- Treat Markdown docs as the cross-client source of truth.
- Use `~/.agent-stack/bin/sync-agent-stack` to apply the managed MCP policy to supported clients.
