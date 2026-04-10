# Commands

This file is for machine-wide command conventions that multiple clients can rely on.

## Environment
- Shared env file: `~/.agent-stack/env/common.env`
- Env loader wrapper: `~/.agent-stack/bin/agent-env`
- Keychain env loader wrapper: `~/.agent-stack/bin/agent-env-keychain`

## Recommended patterns
- Run a command with shared env: `~/.agent-stack/bin/agent-env <command> ...`
- Run a command with Keychain-backed secrets: `~/.agent-stack/bin/agent-env-keychain <command> ...`
- Keep reusable scripts in `~/.agent-stack/bin/`
- Keep reusable MCP definitions in `~/.agent-stack/mcp/registry/base.mcp.json`
- Sync supported clients: `~/.agent-stack/bin/sync-agent-stack`

## Notes
- Avoid storing secrets in shell history.
- Prefer system Keychain backed flows over plaintext env files.
- Keep project-specific commands documented in each repo.
