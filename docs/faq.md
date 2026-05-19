---
title: FAQ & troubleshooting
last_updated: 2026-05-18
---

# FAQ & troubleshooting

## First-run scan found 0 matches

Almost always means the catalog wasn't downloaded yet when the scan started.
Fixed since v0.26.3 (the scan now waits for the catalog if needed). If you
still see this, run menu → **Refresh from catalog** manually after the
"Syncing catalog…" snackbar disappears.

## Search shows results from only the last word

Type more than one word — every word must be a prefix of some word in the
title. If they don't combine into a real title, the result list is empty
(by design — prevents misleading hits). See
[Manual search](mapping/manual-search.md).

## JoiPlay row keeps coming back after I deleted it

Two possibilities:

1. **The folder is actually still on disk.** Open the row → tap the storage
   path's folder icon to verify in your file manager.
2. **The folder is gone but the `.joiback` snapshot still lists it.** Fixed
   since v0.28.10 — on every launch, the app walks the backup list and
   checks folder existence. Missing ones are auto-marked deleted. Force a
   relaunch if it hasn't kicked in yet.

If neither applies, see [Delete a JoiPlay game](joiplay/delete-game.md).

## "Delete failed — re-grant JoiPlay games folder"

The SAF tree you granted doesn't contain the game's path. See
[Set JoiPlay games folder](joiplay/set-folder.md) — you typically need to
grant a higher-level parent that covers all your games.

## "Folder isn't on primary storage"

The folder lives on a secondary user profile (e.g. Samsung Secure Folder
where paths are `/storage/emulated/150/…` instead of `/0/…`). Fixed since
v0.28.4 — re-run with the latest version.

## The donate ☕ icon is missing

Either your build's compiled default doesn't include a donation URL, or your
[app config drop-in](backup/app-config.md) overrides it to empty. Add
`"donationUrl": "https://buymeacoffee.com/advancedappcreator"` (or your own)
to `Documents/F95Updater/app_config.json` and reopen the app.

## The catalog refresh is very slow

Should be under a minute for ~200 apps. If it takes much longer, capture
[verbose logs](diagnostics/verbose.md) and share them — we can see exactly
which step is slow.

## How do I move my data to a new phone?

1. On the old phone: menu → **Backup & config** → **Export backup**. Save
   the resulting JSON to cloud or transfer it.
2. Install F95 Updater on the new phone.
3. (Optional but recommended) Restore your `app_config.json` to
   `Documents/F95Updater/`.
4. Menu → **Backup & config** → **Import backup** and pick the JSON.
5. If you use JoiPlay, also re-grant the games folder via menu → **JoiPlay**
   → **Set JoiPlay games folder…**.

## Where do I report a bug or request a feature?

Use the F95Zone support thread linked from **About**, or open an issue at
[github.com/AdvancedAppCreator/f95updater-releases/issues](https://github.com/AdvancedAppCreator/f95updater-releases/issues).
