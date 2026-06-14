# Opportunity Tracker — update channel

This public repo is the **auto-update channel** for the Opportunity Tracker app. It holds
only what the app needs to update itself:

- **`update.json`** — the release manifest (revision, SHA-256, changelog notes).
- **`Frontend/index.html`** — the app's user interface (HTML/CSS/JS). This is the same file
  that already runs in every user's browser; nothing here is private.
- **Releases** — packaged installers (Windows/macOS) are attached as Release assets.

The application's source code (backend server, database, discovery/ranking logic) is **not**
here — it lives in a separate private repository and ships only as a compiled binary.

## How it works

On launch the app fetches `update.json`. If its `frontend_rev` is newer than the local copy,
the app downloads the new `index.html`, verifies the SHA-256, and swaps it in — so users get
UI updates automatically, offline-safe.

Update source URL:

```
https://raw.githubusercontent.com/caddaman/Opportunity-Tracker/main/update.json
```
