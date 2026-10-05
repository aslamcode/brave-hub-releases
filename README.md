# Brave Hub — Releases

Downloadable installers of the **Brave Hub**, the Brave Engine project launcher. No source lives in this repository — that stays in the main (private) `brave-engine` repo.

One release per version (`v0.1.0`, `v0.1.1`, ...). Every installer has the **same file name in every release** (no version in the name), so GitHub's own "latest release" links always reach the newest one:

| System | Link |
|---|---|
| macOS (Apple Silicon) | https://github.com/aslamcode/brave-hub-releases/releases/latest/download/Brave-Hub-mac-arm64.dmg |
| Update manifest | https://github.com/aslamcode/brave-hub-releases/releases/latest/download/latest.json |

Windows and Linux installers are not built yet.

`latest.json` is what the Hub checks to learn whether a newer version exists: `{ "version", "releasedAt", "platforms": { "<system>": { "url", "sha256", "size" } } }`. Each release carries its own copy, and its `url`s point at that release's own files. Older versions stay downloadable from their own release.

Published by `npm run deploy:hub` in `brave-engine` (the version is bumped by hand in `apps/hub/src/package.json` first). The macOS installer is signed with a Developer ID certificate and notarized by Apple.

This repo must stay **public** — GitHub release assets inherit the repository's visibility, with no per-release override.
