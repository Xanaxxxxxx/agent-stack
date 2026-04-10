# Workflows

Operational workflows for extending and maintaining this repo.

## Sync Managed Clients

Use the sync script as the default path:

```bash
~/.agent-stack/bin/sync-agent-stack
```

What it does:

1. Detects supported clients by install or config footprint.
2. Applies only the MCP entries explicitly managed for that client.
3. Leaves unrelated config intact.

What it does not do:

1. It does not guess whether every built-in plugin equals every MCP server.
2. It does not rewrite unrelated user settings.
3. It does not manage unsupported clients.

## Add a New MCP Server

1. Define the server in the registry or templates.
2. Decide whether it needs Keychain-backed secret loading.
3. Decide which clients should manage it through sync.
4. Update docs before relying on it operationally.

## Add a New Client

1. Identify the client’s live config surface.
2. Decide which MCP entries should be managed.
3. Encode that policy in `sync-agent-stack`.
4. Document the client in `docs/CLIENT-SETUP.md`.

## Add a New Project

1. Keep machine-wide concerns in `~/.agent-stack`.
2. Put project-specific docs and repo-local MCP in the project repo.
3. Avoid moving project policy into the global runtime unless it is truly reusable.

## Change Secret Strategy

1. Update wrappers first.
2. Update sync behavior second.
3. Update docs immediately after.
4. Migrate live configs only after the new path is verified.
