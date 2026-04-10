# Coding Standards

This file defines authoring standards for this repo itself.

## Writing Style

- Prefer direct, technical language.
- Write for fast comprehension.
- Use stable terminology for layers, clients, and secret handling.
- Avoid client-specific jargon when a cross-client term exists.

## Configuration Standards

- Prefer reusable wrappers over duplicated command definitions.
- Prefer portable paths and home-relative conventions over machine-specific paths.
- Keep templates generic and live configs minimal.
- Treat idempotent sync as the default operating model.

## Security Standards

- Do not commit active secrets.
- Do not hardcode machine-local usernames or private absolute paths.
- Prefer Keychain-backed loading for runtime credentials.

## Maintenance Standards

- Update docs when sync policy changes.
- Update templates when managed live config shape changes.
- Keep README and docs aligned with actual behavior.
