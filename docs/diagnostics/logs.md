---
title: Logs
last_updated: 2026-05-18
---

# Logs

The app keeps a rolling log of its own activity in private storage. Use it
when something doesn't work as expected.

## Save logs to Documents

Menu → **Diagnostics** → **Save logs to Documents**.

Writes two files to `Documents/F95Updater/logs/`:

- `applog-<timestamp>.txt` — the rolling log (the last few MB of activity).
- `crashes-<timestamp>.txt` — any pending crash reports, if present.

These files are plain text. You can share them via any app that reads
Documents (email, cloud upload, file manager).

## What the log contains

- App launch and onResume events.
- Catalog sync results (size, count, HTTP status).
- Auto-match progress and per-row decisions.
- JoiPlay backup parsing and folder existence checks.
- Errors and stack traces.

No personal data, no F95Zone credentials. The log records app/game labels
and package names since those are necessary to diagnose mapping issues.

## Where they're stored on disk

Inside the app:

- `<filesDir>/applog.txt` — current rolling log.
- `<filesDir>/applog.prev.txt` — previous rotation.

These are rotated when they reach a size cap, so the app doesn't eat disk.

## See also

- [Verbose mode](verbose.md) — capture more detail for hard-to-reproduce
  issues.
- [Uploading logs](upload.md) — send logs to a configured endpoint, if your
  build has one set.
