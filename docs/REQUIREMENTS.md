# CMFLAC — Product Requirements

**Version:** 0.1  
**Status:** Product specification; implementation not yet started  
**License:** GNU GPL-3.0  
**Initial platform:** Android

## 1. Vision

CMFLAC is an open-source music player focused on audio fidelity, a clean immersive interface, local music, playlist discovery/import, and authorized music sources. The application should be easy to use by default while offering advanced controls to audio enthusiasts.

### Non-negotiable principles

1. Never misrepresent a file's quality.
2. Never up-convert lossy audio and call it lossless.
3. Local library playback must work without an account or internet.
4. Explain the difference between source quality, decoded PCM, and actual output path.
5. Minimize personal data collection.
6. Do not bypass DRM, paywalls, authentication, or provider access controls.
7. Keep source, documentation, issue tracking, and release provenance public.

## 2. Account and access modes

### Guest / local mode (no account)
- Browse device folders and local library.
- Play local audio offline.
- Use local queue, playback controls, and local playlists.
- Downloads from remote repositories are disabled.
- Local playback must never be blocked by sign-in.

### Registered mode
- Email/password registration and login.
- Google sign-in.
- Email verification and account recovery.
- Remote downloads enabled only for sources that are authorized and supported.
- Synchronization of compatible user data across devices.
- Community features and account settings.
- Clear account deletion and data export paths.

### Guest privacy mode
- Owner configures a local PIN/password.
- Temporarily hides account profile, private playlists, history, and private settings.
- Guest session is isolated from the owner's account.
- Reopening the app must not bypass the guest lock.
- Clearly explain recovery before enabling the mode.
- This protects CMFLAC only; it is not a device-wide Android app lock.

## 3. Interface and navigation

### Main navigation
- Home.
- Search.
- Collection (playlists and favorites).
- Device Library.
- Downloads (active and completed).
- Settings.

Adapt the navigation for narrow phones and larger screens without removing essential functionality.

### Visual direction
- Minimal, uncluttered design inspired by the navigation simplicity of Liner, not a direct copy.
- Dark theme as initial default; optional themes and accents.
- Album-art-derived ambient background with subtle, low-saturation blur.
- Soft transitions between tracks.
- Adaptive effects for modest hardware and reduced-motion preferences.
- Minimal consistent icons, generous spacing, readable contrast.

### Players
- Persistent compact player.
- Main expanded player uses the immersive artwork/background layout.
- Track title, artist, album, progress, playback controls, favorite, queue, quality details.
- Dedicated lyrics entry point.
- Adjustable blur and visual settings.

## 4. Playback behavior

- Play, pause, previous, next.
- Reorder and remove queue items.
- “Play next” inserts a track immediately after the current track without discarding the remaining queue.
- Shuffle is an independent toggle.
- Repeat states: off, repeat current track, repeat album/playlist.
- Playback history is configurable.
- When a playlist ends with shuffle and repeat off, offer a recommendation related to the last track. Do not unexpectedly autoplay unless the user enables autoplay.
- Bluetooth/headset media buttons, Android media notification, lock-screen controls, and home-screen widget.
- Sleep timer by duration, end of track, or end of album/playlist.

## 5. Audio fidelity

### FLAC handling
- Decode FLAC without unnecessary lossy conversion or resampling inside the app.
- Preserve original file data when downloading or copying.
- Never claim that a lossy source became lossless by conversion.
- Display actual metadata: codec, bit depth, sample rate, channels, and bitrate when meaningful.
- Verify downloaded files with available checksums/hashes and validate container/decoder integrity.
- Treat “FLAC 4K” as a provider label, not a standardized audio-resolution class. Always show measured technical properties.

### Three separate quality indicators
1. **Source:** properties of the encoded file/stream.
2. **Decoder:** PCM format produced by the decoder.
3. **Output:** effective Android/device/DAC route, only when the platform exposes reliable information.

Do not promise bit-perfect output on all Android devices. Android mixers, device drivers, Bluetooth codecs, DACs, and audio effects can alter or resample output. A high-fidelity mode should minimize avoidable processing and explain when equalizer, ReplayGain, normalization, or other DSP changes the signal.

### Audio tools
- Basic EQ controls and advanced 10-band equalizer with presets.
- Bass/treble controls.
- ReplayGain or equivalent loudness management.
- Gapless playback.
- Optional high-fidelity/direct-style mode where the device route permits it.
- USB DAC compatibility to be evaluated; do not guarantee every DAC or sample rate.

## 6. Lyrics

- Prefer synchronized word-level lyrics when reliable word timestamps are available.
- Highlight the currently sung word/line.
- Tapping a timestamped word or line seeks to the corresponding position.
- Fall back to line-level synchronization or static lyrics when word timing is unavailable.
- Never fabricate word-level timing from line-level data.
- Provide text-size and accessibility controls.

## 7. Library and playlists

### Local library
- Browse folders, artists, albums, tracks, genres, and favorites.
- Scan for new files and allow manual folder scanning.
- Edit metadata/artwork where technically and legally appropriate.
- Detect duplicates.
- Exclude selected folders.
- Local playlists and import/export of playlist files.
- Keep local audio files on the device unless the user explicitly chooses otherwise.

### Playlist creation and import
- Create, edit, reorder, share, and delete playlists.
- Import playlist metadata from supported services: Spotify, Apple Music, Amazon Music, YouTube Music, Tidal, and future community connectors.
- Import metadata only: title, artists, album, version/edition, duration, ISRC or other identifiers when available.
- Search configured CMFLAC repositories for matching tracks.
- Preserve original playlist order.
- Report unavailable or ambiguous matches.
- Matching confidence: exact, high-confidence suggestion, ambiguous candidates, not found.
- Do not download music from the source streaming platform as part of playlist import.
- Each platform connector must be validated against its current API, authentication model, terms, and permitted use. Do not promise support where access is unavailable.

## 8. Search, sources, and downloads

- Search tracks, albums, and artists.
- Keep metadata/catalog providers separate from audio-stream/download providers.
- Remote download options appear only when a configured source actually supports the requested item and format.
- Use only authorized sources and permitted distribution methods.
- No DRM circumvention, credential theft, hidden scraping, or access-control bypass.
- Show source/provider identity and available format/quality before download.

### Community repositories
- Official, reviewed community, and external/unverified sources are visually distinct.
- Repositories declare version, origin, permissions, and supported capabilities.
- Enforce least privilege; extensions must not receive unrestricted access to account credentials or arbitrary app data.
- Avoid arbitrary executable code inside the main app process.
- Provide disable/remove/report controls and provenance information.
- A community repository is not automatically authorized to distribute every catalog item.

### Download manager
- Active, queued, paused, completed, failed, and cancelled states.
- Pause/resume/cancel and retry.
- Background downloads with Android-compliant foreground notifications where required.
- Download queue and per-item progress.
- Display file size, actual format, bit depth, sample rate, and destination.
- User-configurable download folder using Android storage APIs.
- Handle interrupted connections and partial files safely.
- Verify integrity before marking a download complete.
- Downloads require a registered account, but local playback does not.

## 9. Accounts, synchronization, and privacy

- Email/password and Google authentication.
- Synchronize compatible playlists, favorites, preferences, and optional history.
- Do not upload local audio files by default.
- Resolve cross-device conflicts predictably and document the rule.
- Optional and transparent analytics; prefer aggregate counters.
- No precise location collection.
- Do not collect listening history for surveillance or sell listening profiles.
- Provide account deletion, data export, and privacy policy.
- Admin dashboard: aggregate registered/active users, app versions, crash/error counts, provider availability, and service health.
- Admin dashboard must not expose private listening activity.
- Secure admin access with MFA and role-based permissions.

## 10. Community and open development

- Public GitHub repository.
- GPL-3.0.
- Issues for bugs and feature proposals.
- Pull requests and contribution guide.
- Public changelog and release notes.
- Code of conduct and security disclosure policy.
- Community voting/feedback process.
- Automated builds/tests and dependency/security checks.
- Release artifacts should include checksums and build provenance; reproducible builds are a goal.
- Maintain independent backups/mirrors of the Git repository.

## 11. Compatibility and performance

- Provisional minimum: Android 10 / API 29.
- Initial target SDK: API 36.
- Validate minimum version against Media3, storage APIs, foreground-service rules, and audio stack before declaring support.
- Adapt blur, animations, and memory usage to device capability.
- Optimize battery, data use, startup time, and background playback.
- Test on low-memory devices, different screen sizes, wired headphones, Bluetooth, and USB DACs.

## 12. Administration and observability

Admin metrics should include:
- Registered accounts.
- Approximate concurrent active sessions using short-lived heartbeats.
- Daily/monthly active users.
- App version distribution.
- Crash and playback error rates.
- Repository/provider uptime and response failures.
- Download failure rates (aggregate, not private listening contents).

Do not store unnecessary IP/location/device identifiers. Publish what telemetry is collected and why.

## 13. Suggested delivery phases

### Alpha
- Core app shell and navigation.
- Local library and local playback.
- Compact and immersive player.
- FLAC metadata and honest quality reporting.
- Basic queue and settings.

### Beta
- Online search and authorized provider adapters.
- Playlist metadata import connectors where permitted.
- Download manager and repository framework.
- Lyrics and advanced playback.
- Accounts, Google sign-in, and synchronization.
- Guest privacy mode.

### 1.0
- Security review and privacy documentation.
- Accessibility and performance testing.
- Community/admin features.
- Release automation, checksums, provenance, and backup strategy.
- Public documentation and support process.

## 14. Acceptance principles

A feature is not complete merely because a button exists. It must:
- Work on supported Android versions.
- Handle offline, error, and permission-denied states.
- Respect user privacy and source permissions.
- Have tests for important behavior.
- Be documented.
- Expose truthful status and quality information.
- Avoid regressions in local playback and battery use.

## 15. Open questions

- Confirm Android minimum after dependency/device tests.
- Select backend/auth provider and estimate operating costs.
- Validate each playlist import provider individually.
- Define repository manifest format, sandboxing, and review process.
- Decide exact recommendation/autoplay defaults.
- Determine what Android exposes for effective output sample rate/bit depth per device.
- Establish data retention periods and admin roles.
- Review third-party library licenses and GPL compatibility before shipping.
