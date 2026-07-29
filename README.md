# Hibiscus releases

The public update feed for [Hibiscus](https://github.com/RUGUX/Hibiscus)
(the app repo stays private — only this manifest and the release zips
are public).

- `appcast.xml` — the Sparkle 2 signed update feed for current installs.
- `appcast.json` — the one-release compatibility bridge for pre-Sparkle
  installs. One entry per channel (`stable`, `rc`).
- Release ZIPs, DMGs, and signed deltas attach to GitHub Releases here
  (`v<version>` tags).

## Publishing

Repository maintainers publish from **Actions → Release Hibiscus → Run
workflow** on `main`. Enter the version, channel, and release notes. The
production environment runs the private source repo's complete Mac, Sparkle,
and issue-report gates before it builds, signs, and publishes anything.

The workflow keeps the Sparkle seed in GitHub Actions secrets, imports it into
an ephemeral Keychain, uploads release assets first, and pushes both feeds
last. The source repo's `scripts/release.sh` and `docs/UPDATES.md` remain the
plan of record.
