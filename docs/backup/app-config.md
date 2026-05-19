---
title: App config drop-in
last_updated: 2026-05-18
---

# App config drop-in file

A JSON file that overrides the app's compiled defaults at runtime — catalog
URL, donation URL, support thread URL, optional crash/log upload endpoint,
and so on.

## Why it exists

The shipping APK has sensible defaults (catalog hosted on GitHub Releases,
donate at Buy Me a Coffee, etc.). The drop-in file lets you change those
without rebuilding the app — useful for:

- Pointing the app at a different catalog host.
- Setting a private crash-upload endpoint while developing.
- Customizing the donation / support links for forked builds.

## Where the file goes

Place a file named **`app_config.json`** at one of these locations, in
priority order:

1. `Android/data/<package>/files/app_config.json` *(app's external dir)*
2. **`Documents/F95Updater/app_config.json`** *(easiest — survives uninstall)*
3. `Download/F95Updater/app_config.json`
4. `Download/app_config.json`

When the app starts, it scans these locations and — if it finds a newer
drop-in than its private copy — auto-imports it. You'll see this in the
logs:

```
AppConfig: Auto-imported drop-in config from /storage/.../app_config.json
```

## Sample file

```json
{
  "catalogUrl": "https://github.com/AdvancedAppCreator/f95updater-releases/releases/download/catalog/catalog.json.gz",
  "labelsUrl": "https://github.com/AdvancedAppCreator/f95updater-releases/releases/download/catalog/labels.json",
  "versionInfoUrl": "https://github.com/AdvancedAppCreator/f95updater-releases/releases/latest/download/version.json",
  "crashUploadBaseUrl": null,
  "crashUploadAuthQuery": null,
  "supportThreadUrl": "https://f95zone.to/threads/f95updater-android-companion-app.TBD/",
  "donationUrl": "https://buymeacoffee.com/advancedappcreator"
}
```

Any field you omit falls back to the compiled default.

## Menu actions

- **Backup & config → Export app config** — writes the *current effective*
  config to both your private storage and `Documents/F95Updater/app_config.json`
  (so you can edit and re-import).
- **Backup & config → Import app config…** — opens a file picker; the
  selected file becomes the new override. UI updates immediately (no
  restart).
