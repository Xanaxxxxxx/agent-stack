# Rules

- Do not hardcode secrets in MCP configs.
- Prefer one shared MCP implementation over per-client copies.
- Prefer Markdown for durable instructions that multiple clients can read.
- Use user-level client config for personal tools and project-level config for repo-specific tools.
- Keep templates as examples; copy them into live client config only after review.
- Prefer Keychain-backed wrappers when secrets are required.
- Use the sync script to enforce client-specific allowlists instead of guessing capability overlap.
