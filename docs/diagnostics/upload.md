---
title: Uploading logs
last_updated: 2026-05-18
---

# Uploading logs

If your build is configured with a `crashUploadBaseUrl` (via the
[app config drop-in](../backup/app-config.md)), two extra menu items become
available.

## Upload crash logs

Menu → **Diagnostics** → **Upload crash logs (N)**.

The number in parentheses is how many pending crash reports the app has
queued. Tapping it PUTs each crash file to
`<crashUploadBaseUrl>/crash-<timestamp>.txt?<crashUploadAuthQuery>`.

Snackbar: `Crash logs: <ok> sent, <fail> still queued`.

## Upload app logs

Menu → **Diagnostics** → **Upload app logs (NN KB)**.

Uploads the current rolling log file and (if present) the rotated previous
one to:

- `<base>/log-<ts>-current.txt`
- `<base>/log-<ts>-prev.txt`

Snackbar: `Logs: <ok> sent, <fail> failed`. On success, the local log buffer
is cleared.

## When the upload UI is hidden

If `crashUploadBaseUrl` is blank or null in your effective app config, both
upload items are hidden. Use **Save logs to Documents** instead and share
the file manually.

The defaults shipped with the public APK have upload disabled. Dev builds
with an app-config drop-in pointing at a private blob store enable it.
