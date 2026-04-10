# Stack

Layer model for the local multi-agent runtime.

## Layer 1: System

Shared machine-level dependencies installed once:

- git
- node / npm / npx
- python / uv / pipx
- docker
- other local CLIs required by specific MCP servers

## Layer 2: Secret Loading

Primary secret source:

- macOS Keychain

Shared runtime wrapper:

- `~/.agent-stack/bin/agent-env-keychain`

Compatibility wrapper:

- `~/.agent-stack/bin/agent-env`

Notes:

- `common.env` exists as a placeholder and bootstrap artifact.
- It is not the preferred runtime source for active credentials.

## Layer 3: MCP

Reusable tool access exposed through:

- remote HTTP MCP servers
- local stdio MCP servers
- Docker-backed MCP subprocesses
- thin wrappers that standardize env injection

## Layer 4: Documentation

Cross-client knowledge lives in Markdown:

- architecture
- policy
- command references
- client setup rules

## Layer 5: Client Adapters

Each supported client keeps a thin live config that points into the shared runtime.

Current targets:

- Codex
- Cursor
- Claude Code
- Antigravity

## Layout

```text
~/.agent-stack/
  bin/
  docs/
  env/
  mcp/
  templates/
```

## Scope

- Put machine-wide runtime concerns here.
- Put project-specific MCP config inside the project repo.
- Keep this repo generic enough to move between machines.
