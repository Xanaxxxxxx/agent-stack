# Rules

Repo policy for cross-client runtime management.

## Shared Runtime Rules

- One reusable MCP implementation is better than several client-specific copies.
- Shared behavior should be expressed in repo docs and wrappers first.
- Client-specific exceptions should be explicit and documented.

## Secret Rules

- Do not commit active secrets.
- Do not hardcode tokens in live config templates.
- Prefer Keychain-backed wrappers when credentials are required.

## Sync Rules

- Use the sync script to manage supported clients.
- Do not rely on “smart” capability inference for plugin overlap.
- Preserve unrelated user config unless there is an explicit migration plan.

## Documentation Rules

- README explains the system.
- `docs/` explains the policy and operations.
- Templates show expected config shape, not secret values.
