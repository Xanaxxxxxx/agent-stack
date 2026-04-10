# AGENTS

Top-level operating guide for humans and AI clients using this repo.

## Purpose

This repo defines a shared local runtime for multiple AI coding clients.

Use it to standardize:

- MCP access
- secret loading
- cross-client documentation
- client-specific sync policy

## Read Order

Read these files in order:

1. `README.md`
2. `docs/STACK.md`
3. `docs/WORKFLOWS.md`
4. `docs/RULES.md`
5. `docs/CLIENT-SETUP.md`

## Operating Model

- MCP is the shared tool layer.
- Markdown is the shared instruction layer.
- Keychain is the primary secret store.
- Client configs should remain thin.
- `sync-agent-stack` is the canonical way to apply managed MCP entries.

## Expectations

- Reuse shared MCP definitions before creating client-specific variants.
- Prefer durable Markdown over client-only prompt fragments.
- Treat repo-level docs as the source of truth for policy.
- Avoid manual live-config edits when the sync script already manages that surface.
