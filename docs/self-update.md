---
title: Self-update
last_updated: 2026-05-20
---

# Self-update

The app can update itself in place by pulling a new APK from GitHub Releases. No Play Store needed.

## How it works

On every launch, the app fetches `version.json` from
`github.com/AdvancedAppCreator/f95updater-releases/releases/latest/download/version.json`.

If `version.json` advertises a higher `versionCode` than the running app,
you'll see an **"Update available"** dialog.

You can also force the check manually: menu → **Check for app update**.

## Update dialog

The dialog shows:

- New version name + release notes.
- **Download & install** button.

Tapping it downloads the APK from the URL in `version.json`, then hands the file to Android's
package installer. You may need to grant "Install unknown apps" permission
once.

A progress bar updates during the download. After install, Android relaunches
the app on the new version.

## Auto-backup before update

The app version code stored in `last_seen_version_code` is bumped after
install. The next launch is the first one on the new version, and
[Auto-backup](backup/auto-backup.md) kicks in to snapshot your state — so if
the new version misbehaves, you can restore back.
