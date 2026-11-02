# CMFLAC

**Open-source, high-fidelity music player for Android.**

CMFLAC aims to combine a clean, immersive music-player experience with a local music library, accurate FLAC playback, playlist management, community repositories, and transparent audio-quality reporting.

> **Project status: specification / pre-implementation.** This repository currently documents the product and its development process. It is not yet a finished application, and no APK is published here.

## Product principles

- **Audio fidelity first.** Never label an audio file as lossless or Hi-Res unless its actual properties support that claim.
- **No fake FLAC.** Converting MP3/AAC to FLAC does not restore lost audio information.
- **Local music works offline.** Browsing and playing music already on the device must not require an account.
- **Honest signal reporting.** Distinguish source-file properties, decoder output, and the actual device/output path when measurable.
- **Privacy by design.** Collect the minimum data needed and prefer aggregated analytics.
- **Open development.** Public source, decisions, issue tracking, contribution guidelines, and verifiable releases.
- **Authorized sources only.** Provider integrations must respect their APIs, permissions, licenses, and terms. CMFLAC will not bypass DRM or access controls.

## Planned features

- Minimal, adaptive interface with a blurred ambient background derived from album artwork.
- Compact player and immersive expanded player.
- Local device library and offline playback.
- FLAC playback with source/decoder/output quality information.
- Queue management, shuffle, repeat, play-next, and optional recommendations.
- Synchronized lyrics where timestamp data is available; tap-to-seek where timing precision permits.
- Playlists, favorites, history, statistics, sleep timer, equalizer, ReplayGain, and gapless playback.
- Playlist metadata import from supported services, preserving order and matching tracks against authorized CMFLAC sources.
- Download manager for compatible, authorized sources, available to registered users.
- Optional account with email/password and Google sign-in; optional synchronization.
- Guest mode protected by a local PIN/password.
- Community repositories with trust labels and permission boundaries.
- Public issue tracking, feature proposals, and community contributions.

## Playlist import is metadata-only

Importing a playlist from Spotify, Apple Music, Amazon Music, YouTube Music, Tidal, or another supported platform means importing track metadata (title, artists, album, version, duration, identifiers where available). CMFLAC then searches its own configured sources and builds a playlist in the original order. It does **not** download music from the source platform. Provider access and availability must be validated individually; unsupported links or inaccessible playlists must be reported clearly.

## Android compatibility

The current product target is Android 10 (API 29) and newer, subject to dependency and device validation. The initial target SDK is planned to be API 36. The minimum supported version is provisional until the playback, storage, and audio stack is tested.

## Repository map

- `docs/REQUIREMENTS.md` — product requirements and acceptance criteria.
- `docs/DECISIONS.md` — important product and technical decisions.
- `CONTRIBUTING.md` — how to propose and contribute changes.
- `CODE_OF_CONDUCT.md` — community expectations.
- `SECURITY.md` — responsible vulnerability reporting.
- `LICENSE` — GNU GPL v3.0.

## Getting involved

Use [GitHub Issues](../../issues) for bug reports and feature proposals. Read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request. Early feedback is welcome, but implementation proposals should distinguish confirmed facts from assumptions.

## License

CMFLAC is licensed under the **GNU General Public License v3.0**. See [LICENSE](LICENSE).

The CMFLAC name, logo, and visual identity are project branding and are not automatically granted by the software license. Third-party names and trademarks belong to their respective owners.
