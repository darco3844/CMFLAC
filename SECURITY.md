# Security Policy

## Project status

CMFLAC is currently in the specification / pre-implementation stage. No official production APK is published by this repository yet.

## Reporting a vulnerability

Please do not publish exploitable vulnerabilities, credentials, private user data, or working attack details in a public issue.

Use GitHub's **Report a vulnerability** feature in the Security tab if it is enabled for this repository. If it is unavailable, contact the repository owner privately through their GitHub profile and request a secure reporting channel.

Include:
- Affected commit, version, or component.
- Impact and conditions required.
- Reproduction steps or a minimal proof of concept.
- Suggested mitigation, if known.

Do not include real user data or secrets.

## Security goals

- Least-privilege Android permissions.
- Secure authentication and session handling.
- No plaintext passwords or committed secrets.
- Dependency and build scanning.
- Validation of downloaded files and repository manifests.
- Strong isolation between repository extensions and private account data.
- Transparent telemetry and data retention.
- Signed releases, checksums, and build provenance.
- Responsible disclosure and coordinated fixes.

## Release authenticity

Only trust APKs linked from the official repository's Releases page. Compare published checksums and verify release provenance when available. A public source repository alone does not prove that an arbitrary APK is safe.
