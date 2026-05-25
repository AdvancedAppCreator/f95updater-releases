---
title: FAQ & troubleshooting
last_updated: 2026-05-24
---

# FAQ & troubleshooting

## First-run scan found 0 matches

Almost always means the catalog wasn't downloaded yet when the scan started.
The scan now waits for the catalog if needed; if you still see this, open the **Catalog** tab and tap the **Refresh** icon, then return to **Apps** and run **Refresh from catalog** from the menu.

## Search shows results from only the last word

Type more than one word — every word must be a prefix of some word in the
title. If they don't combine into a real title, the result list is empty
(by design — prevents misleading hits). See
[Manual search](mapping/manual-search.md).

## Tag autocomplete chips aren't showing

The autocomplete activates only while the cursor is right after a `tag:`
token with no trailing space. Type `tag:har` and chips for `harem`, `hardcore`, etc. should appear below the search field. Once you tap a chip or hit space, the chips go away.

## JoiPlay row keeps coming back after I deleted it

Two possibilities:

1. **The folder is actually still on disk.** Open the row → tap the storage
   path's folder icon to verify in your file manager.
2. **The folder is gone but the `.joiback` snapshot still lists it.** On every
   launch the app walks the backup list and checks folder existence. Missing
   ones are auto-marked deleted when permissions allow it. Force a relaunch if
   it hasn't kicked in yet.

If neither applies, see [Delete a JoiPlay game](joiplay/delete-game.md).

### Special case: ghost JoiPlay row right after importing a backup

If you do a fresh install, import a backup that contains a JoiPlay snapshot,
and you see a row for a game whose folder is no longer on disk, that row may
*persist* until you either:

- Tap the row's **🗑** icon — the delete handler treats a confirmed-missing
  folder as success and removes the row, **or**
- Open **Menu → Install → JoiPlay settings…** and grant **All files access**. On the next app launch the
  startup prune can definitively verify which folders are gone and will
  auto-remove the orphans, **or**
- Use the row's **Edit** dialog → **Hide** to remove it from the list manually.

**Why does this happen?** Android 11+ removed the ability to check "does this
folder exist" without a permission grant. We could distinguish "folder is
missing" from "folder is here but we can't see it" via your previously
granted full-storage permission, but on a fresh install that grant doesn't exist yet —
so the app conservatively shows the row. Tapping delete or granting access
once resolves it.

## "Delete failed — folder no longer accessible"

The All-files-access permission has been revoked, or the path lies under a profile our app can't see (e.g. Samsung Secure Folder). Re-grant **All files access** via **Menu → Install → JoiPlay settings…** and retry.

## "Folder isn't on primary storage"

The folder lives on a secondary user profile (e.g. Samsung Secure Folder
where paths are `/storage/emulated/150/…` instead of `/0/…`). Resolved in modern
versions — re-run with the latest version.

## The donate ☕ icon is missing

Donate links are configured in the app build. If your build was compiled
with empty donation URLs, the icon stays hidden — this is intentional.

## The catalog refresh is very slow

Should be under a minute for ~200 apps. If it takes much longer, re-run when you're not on a heavily-throttled network. The catalog itself is ~8 MB gzipped; the per-app matching is local.

## Import backup asks for folder access again

The app remembers the scoped backup folder grant across restarts, but Android
can revoke it or the folder can move. If the grant is gone, the app shows the
disclaimer and asks you to choose the folder again.

## How do I send useful logs?

Open **Menu -> Help**. Use **Copy diagnostics summary** for a quick report or
**Save local diagnostics** to write logs/crashes to Documents. If diagnostics
upload is configured, **Upload app logs + screenshots** sends the log plus any
diagnostic screenshots you captured.

## How do I move my data to a new phone?

1. On the old phone: menu → **Backup & config** → **Export backup**. Save
   the resulting JSON to cloud or transfer it.
2. Install F95 Updater on the new phone.
3. Menu → **Backup & config** → **Import backup** and pick the JSON.
4. If you use JoiPlay, the JoiPlay rows come back when you re-import your
   `.joiback` file via menu → **Backup & config → Import JoiPlay backup**.

## Where do I report a bug or request a feature?

Open an issue at
[github.com/AdvancedAppCreator/f95updater-releases/issues](https://github.com/AdvancedAppCreator/f95updater-releases/issues).
