# Security and maintenance

This library is part of the AT Protocol toolkit used by civic apps. Tests use synthetic data. A passing audit is not a guarantee of security.

Do not put personal data or real credentials in fixtures. Private GitHub visibility does not make committed secrets safe.

## Reporting a vulnerability

Report suspected vulnerabilities privately to an organisation maintainer. Do not include tokens, passwords, private keys, database contents or personal information in an issue or pull request.

## Keeping the repository safe

- Keep environment files, runtime accounts, signing keys and databases out of Git and Docker build contexts. Back up persistent data together with its keys.
- Run the README checks before merging. CI tests changes and scans the full Git history for secrets. Dependencies and GitHub Actions are checked weekly by Dependabot.
- Authentication and identity links from `atproto-identity` do not grant membership, publishing or any other permission. Check authorization at the point of access and fail closed on upstream failure.
- Deployment belongs in `server-infrastructure`, not in this repository. Never deploy or reset a shared environment as part of library tests.

See the README for this library's specific trust and integration boundaries.
