# atproto-source-bridge

Instructions for AI agents and human contributors working in this repository.

## Scope

- Own reusable external-source ingestion framework code here.
- Keep app UI, business decisions and deployment in consuming apps or other repos.
- Do not add volleyball, school, church or any domain-specific logic to this library — that belongs in the consuming app.

## Git and release

- Use the configured user Git identity. No co-author trailers, no push unless requested.
- Do not amend commits on `main`. Create new commits.
- Never force-push. Never skip hooks.
- Release only when requested; cut a release tag only after README checks pass.

## Code style

- TypeScript, strict mode.
- ES modules (`"type": "module"` in package.json).
- Prettier for format (`pnpm run format:check` in CI).
- Minimal API surface — expose only what consumers need.
- No `any` without a comment explaining why.

## Testing

- Unit tests with `node --test` (no external test framework).
- Synthetic fixtures only. No real credentials or personal data.
- Integration tests against [atproto-sandbox](../atproto-sandbox/) if sandbox behavior is required.

## Security

- Never commit secrets, credentials, private keys or personal data.
- Environment files, signing keys and databases stay out of Git and Docker build contexts.
- CI runs `.github/scripts/scan-secrets.sh` on every push — scans full Git history.
- Report suspected vulnerabilities per [SECURITY.md](SECURITY.md).

## What belongs elsewhere

- Login / sessions → `atproto-identity`
- PDS transport → `atproto-client`
- Signed statements → `atproto-attestations`
- Group policies → `atproto-groups`
- App UX → consuming app
- Deployment → `server-infrastructure`

## When in doubt

- Minimal change. One concern per PR.
- Ship small. A v0.1 that works beats a v1.0 that doesn't exist.
- If you catch yourself writing app-specific code, stop and move it.
