# Agent Stack

Shared local tooling layer for multiple AI coding clients.

Supported clients:
- Codex
- Cursor
- Claude Code
- Antigravity

This directory is the source of truth for:
- shared secret-loading conventions
- shared MCP server registry templates
- shared Markdown context files
- per-client config templates that point to the same MCP layer

Principles:
- put reusable capabilities in MCP servers
- put reusable project and workflow context in Markdown
- keep client-specific configuration thin
- prefer Keychain-backed secret loading over plaintext env files

Runtime model:
- secrets live in macOS Keychain
- `common.env` is now a placeholder file, not the primary secret store
- `bin/agent-env-keychain` is the shared wrapper for MCP processes that need secrets
- `bin/sync-agent-stack` is the rules-driven sync tool for supported clients
