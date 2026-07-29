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
source must first pass the private repository's required CI on `main`. The
production environment then validates the pinned source, signing key,
issue-report contract, package, release assets, and both update feeds without
rerunning the complete Mac suite.

The workflow keeps the Sparkle seed in GitHub Actions secrets, imports it into
an ephemeral Keychain, uploads release assets first, and pushes both feeds
last. The source repo's `scripts/release.sh` and `docs/UPDATES.md` remain the
plan of record.
