# audioanchor-site

Source for [audioanchor.io](https://audioanchor.io) — the download/landing page for
[AudioAnchor](https://github.com/rm968211/audio-anchor), kept in its own repo so README/site tweaks
never force a version bump on the app repo (which requires one on every PR).

A single static `index.html` (no build step). Download buttons fetch
`api.github.com/repos/rm968211/audio-anchor/releases/latest` client-side and point at that
release's `-Setup.exe`/`-Portable.zip` assets, falling back to the GitHub releases page if the
request fails or is rate-limited — so this page never needs updating when the app ships a new
version.

## Deploy

Pushes to `main` publish automatically via GitHub Pages. `CNAME` pins the custom domain
(`audioanchor.io`); `.nojekyll` skips Jekyll processing since this is plain static HTML.

## Updating assets

`assets/logo.png`, `assets/favicon.ico` (built from `assets/icon.ico`), and
`assets/screenshot-app.png` are copied from the app repo's `assets/` folder and demo mode
(screenshot edited to remove the "Demo" title-bar/banner text). Re-copy and re-edit them there if
the app's branding changes.
