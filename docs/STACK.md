# Stack

## Layers

### 1. System layer
Shared runtimes and CLIs installed once on the machine:
- git
- node / npm / npx
- python / uv / pipx
- docker
- xcodebuild and simulator tooling when needed

### 2. MCP layer
Reusable tool servers shared by multiple clients:
- remote HTTP MCP servers
- local stdio MCP servers
- Docker-packaged MCP servers
- custom local wrappers

### Secret loading
Secrets are loaded from macOS Keychain through the shared wrapper:
- `~/.agent-stack/bin/agent-env-keychain`

Plaintext env files are no longer the primary runtime source of secrets.
`~/.agent-stack/env/common.env` remains as a placeholder and template only.

### 3. Markdown context layer
Cross-client docs that describe:
- architecture and project context
- coding standards
- common commands
- review and release workflows

### 4. Client adapter layer
Thin config for each client that points to the same MCP layer and docs.

## Directory layout

```text
~/.agent-stack/
  env/
  mcp/registry/
  docs/
  templates/
  bin/
```

## Scope guidance
- Put machine-wide tools here.
- Put project-specific MCP config inside each repo.
- Keep secrets out of templates.
- Use Keychain for real secrets whenever possible.
