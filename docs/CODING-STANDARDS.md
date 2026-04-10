# Coding Standards

These are cross-client guidance notes, not language-specific lint rules.

- Prefer small, reversible changes over large speculative rewrites.
- Put shared operational instructions in Markdown, not only in client-specific prompts.
- Put reusable capabilities behind MCP where practical.
- Keep secrets and machine-local paths out of shareable templates.
- Treat user-level setup as global and project-level setup as local.
