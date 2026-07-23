# Hibiscus releases

The public update feed for [Hibiscus](https://github.com/RUGUX/Hibiscus)
(the app repo stays private — only this manifest and the release zips
are public).

- `appcast.json` — the manifest installed apps poll (once a day, and on
  Check for Updates…). One entry per channel (`stable`, `rc`).
- Release zips attach to GitHub Releases here (`v<version>` tags).

Publishing is `scripts/release.sh <version> <channel>` in the app repo —
`docs/UPDATES.md` there is the plan of record. An empty `{}` manifest
honestly means "nothing published yet"; installed apps report Up to date.
