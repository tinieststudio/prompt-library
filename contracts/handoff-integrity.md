# Handoff Integrity

Before creating a ZIP or external-model handoff:

- run a secret scan over the exact files being sent;
- exclude credentials, tokens, private keys, `.env` files, caches, build output, `.git`, and unrelated archives;
- record the source commit or working-tree identity;
- include a manifest listing every included artifact and its relative path;
- prefer a patch or diff over blind replacement when the receiver has an existing checkout;
- include manifests, lockfiles, tests, fixtures, and project-state files needed to reproduce the work.

The receiver must verify the manifest against the received files before editing. A stale or incomplete handoff is blocked until reconciled.
