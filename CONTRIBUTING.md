# Contributing to CMFLAC

Thank you for considering a contribution.

CMFLAC is in the specification / pre-implementation stage. Before substantial code is written, please discuss major architectural changes in an issue so the project can agree on the direction.

## Ways to contribute

- Report reproducible bugs.
- Suggest features and improvements.
- Improve documentation and translations.
- Review accessibility and usability.
- Test builds on different Android devices.
- Submit code through pull requests.

## Before opening an issue

- Search existing issues to avoid duplicates.
- Use the relevant issue template.
- Include Android version, device model, app version/commit, and reproducible steps when relevant.
- Remove personal data, access tokens, credentials, and private music files from logs/screenshots.

## Pull request process

1. Open or reference an issue for non-trivial work.
2. Fork the repository and create a focused branch.
3. Keep changes small and explain the reason.
4. Add or update tests where applicable.
5. Update documentation and changelog when behavior changes.
6. Ensure builds/tests pass.
7. Submit a pull request describing behavior, testing, risks, and screenshots for UI changes.

## Code expectations

- Prefer readable, maintainable code over clever shortcuts.
- Avoid unnecessary permissions and network requests.
- Do not add telemetry without documenting purpose, retention, and user controls.
- Do not add provider integrations that bypass DRM, authentication, or access controls.
- Do not claim lossless/Hi-Res quality without verifiable source information.
- Treat community repository content as untrusted input.
- Never commit API keys, passwords, signing keys, tokens, or personal data.

## Licensing

By submitting a contribution, you agree that it is provided under the repository's GNU GPL-3.0 license, unless a different compatible arrangement is explicitly agreed before contribution. Do not submit code or assets you do not have the right to license.

## Communication

Be respectful and constructive. See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
