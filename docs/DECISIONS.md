# CMFLAC — Decision Log

This log records decisions agreed for the product. New decisions should be added with date, context, and consequences.

## D-001 — Product identity
**Status:** Accepted  
CMFLAC is an open-source Android music player centered on audio fidelity, a minimal immersive interface, local playback, playlists, and authorized online sources.

## D-002 — License
**Status:** Accepted  
GNU GPL-3.0. The repository includes the full license text in `LICENSE`.

## D-003 — Visual direction
**Status:** Accepted  
Minimal uncluttered UI, subtle album-art-derived ambient blur, compact persistent player, and immersive expanded player as the primary full player.

## D-004 — Local playback without account
**Status:** Accepted  
Local library browsing and playback work offline and without registration. Remote repository downloads require a registered account.

## D-005 — Accounts
**Status:** Accepted  
Optional account with email/password and Google sign-in. Compatible user data can synchronize across devices. Local audio files are not uploaded by default.

## D-006 — Guest privacy mode
**Status:** Accepted  
A temporary in-app guest mode hides the owner's private profile/data and requires a locally configured PIN/password to return. It is not a device-wide lock.

## D-007 — Playlist import
**Status:** Accepted  
Playlist import is metadata-only. CMFLAC imports track identity/details, searches its own authorized sources, preserves order, and reports missing/ambiguous matches. It does not download audio from the source platform.

## D-008 — Planned playlist connectors
**Status:** Planned, provider validation required  
Spotify, Apple Music, Amazon Music, YouTube Music, and Tidal. Availability depends on current official APIs, authentication, permissions, and terms. No connector is considered implemented until tested and documented.

## D-009 — Audio fidelity
**Status:** Accepted  
Never create fake lossless files by converting lossy sources. Report source, decoder, and output quality separately. Do not promise bit-perfect output on every Android device.

## D-010 — “FLAC 4K”
**Status:** Accepted clarification  
“FLAC 4K” is not a standardized audio-quality class. If encountered as a provider label, show measured technical properties rather than treating the label as proof of quality.

## D-011 — Community repositories
**Status:** Accepted direction; security design pending  
Support official, reviewed community, and external/unverified repositories as distinct trust levels. Apply least privilege and source authorization checks.

## D-012 — Android compatibility
**Status:** Provisional  
Target Android 10 / API 29 minimum and API 36 target initially. Confirm after dependency and device validation.

## D-013 — Infrastructure
**Status:** Accepted direction  
Start with managed services; retain the option to migrate to self-hosted or hybrid infrastructure as usage and costs evolve.

## D-014 — Distribution
**Status:** Accepted for initial stage  
Publish source and initial APK releases through GitHub. Consider app stores and other distribution channels later.

## D-015 — Recommendations
**Status:** Accepted direction  
Recommendations may use listening preferences, artists, genres, and tracks. Personalization should be optional and privacy-respecting. Do not unexpectedly autoplay after a playlist ends unless enabled.

## D-016 — Equalizer and themes
**Status:** Accepted  
Offer both simple and advanced 10-band equalizer modes. Provide a polished default theme plus optional visual customization.

## D-017 — Admin analytics
**Status:** Accepted direction  
Provide aggregate operational metrics (registered users, active sessions, app versions, crashes, provider health) without exposing private listening activity or collecting unnecessary location data.
