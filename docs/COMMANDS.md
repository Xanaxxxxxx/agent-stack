# Commands

Reference commands for operating this repo.

## Core Commands

Sync managed client config:

```bash
~/.agent-stack/bin/sync-agent-stack
```

Run a command with placeholder env loading:

```bash
~/.agent-stack/bin/agent-env <command> ...
```

Run a command with Keychain-backed secret loading:

```bash
~/.agent-stack/bin/agent-env-keychain <command> ...
```

## Typical Use Cases

Re-apply MCP policy after pulling repo updates:

```bash
~/.agent-stack/bin/sync-agent-stack
```

Run a secret-bearing subprocess through the shared wrapper:

```bash
~/.agent-stack/bin/agent-env-keychain docker run ...
```

## Notes

- `common.env` is no longer the primary runtime secret source.
- Prefer the Keychain wrapper for any command that requires credentials.
- Keep project-specific command references in the project repo, not here.
