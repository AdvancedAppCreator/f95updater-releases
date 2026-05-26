---
title: Changelog
last_updated: 2026-05-25
---

# Changelog

Major user-visible changes per version. Bugfixes and internal refactors are
intentionally summarized.

## v1.1.13

- Trust/privacy positioning was made clearer in About/share copy, README, help
  home, and permissions docs: local-first, no F95 login, no hosted account, no
  analytics, no automatic game downloader, and public GitHub releases/docs.

## v1.1.12

- Rows now support private personal tracking fields: status labels
  (`Playing`, `Waiting for update`, `Completed`, `Archived`), a 1-5 rating, and
  notes. These show on the main row/details panel and are included in backups.

## v1.1.11

- Advanced app configs can now include multiple self-update feeds. The app
  checks every configured `version.json` URL and uses the feed with the highest
  `versionCode`, so public and private/dev update feeds can coexist in one
  config.

## v1.1.8

- **About dialog sharing/support polish**: About now includes quick actions to
  share the app, open the official F95 thread, and report bugs or request
  features through GitHub Issues. The share text uses the Android APK + JoiPlay
  games positioning. See [Support the project](support.md).
- **JoiPlay archive upgrade flow**: when you pick a `.zip`, `.rar`, or `.7z`
  through [Install game in JoiPlay](joiplay/install-game.md), the app analyzes
  it first and offers to replace a matching imported JoiPlay game instead of
  always installing as new.
- Upgrades keep a rollback backup of the old game folder, preserve/copy saves
  where possible, show progress immediately after your choice, and keep the
  progress dialog visible while cancellation cleanup finishes.
- [Import .joiback backup](joiplay/import-backup.md) no longer forces Android's
  folder picker on first import when All files access is already granted.
- Direct JoiPlay launches after upgrade/import now match JoiPlay's runtime
  intent contract more closely, fixing Ren'Py runtime launch errors seen when
  launching from F95 Updater even though launching from JoiPlay worked.
- Catalog data was refreshed.

## v1.0

- Public release updated from the foldable-tested v0.50 series.
- Compact and landscape layouts were improved across the main list, catalog
  filters, bottom navigation, diagnostics button, and game-settings dialog.
- The game-settings dialog now uses a wide-screen split layout with search
  results on the right, and keeps its action buttons on one row when there is
  enough width. See [Manual search](mapping/manual-search.md).
- Dialogs and in-progress operations are preserved across rotation/fold state
  changes where Android allows it.
- Diagnostics gained screenshot capture, local save/copy actions, and optional
  log/screenshot upload. See [Diagnostics and logs](diagnostics/logs.md).
- Regular backup import and JoiPlay `.joiback` import now use scoped folder
  access and remember the granted backup folder across restarts. See
  [Export & import backup](backup/export-import.md) and
  [Import .joiback backup](joiplay/import-backup.md).
- Permission menu items now clearly separate all-files access from usage-data
  access. See [Permissions](permissions.md).
- Catalog review tools now include [Review unmapped games](catalog/review-unmapped.md)
  and the **Overwrite manual matches on refresh** setting.
- Added [Probably unused JoiPlay folders](joiplay/unused-folders.md), a
  review-only report for folders not referenced by a fresh `.joiback` backup.
- The SWF-to-video converter experiment was removed.

## v0.45.x

- Public-readiness cleanup: clearer permission rationale dialogs, README privacy
  notes, diagnostics export without requiring upload config, and scoped backup
  imports.
- Backup/config flows were reorganized so regular JSON import and JoiPlay
  `.joiback` import share scoped folder grants when possible.
- Public v1.0 was briefly released, then public testing was paused while
  foldable/narrow-screen layout issues were fixed in the v0.50 private series.

## v0.42.0

- **Catalog filters persist** across app restarts (status / engine / category / min-rating / installed-only / sort / search query).
- **Tag autocomplete chips** appear below the catalog search field while typing `tag:<prefix>`; tap to insert the full tag.
- Closing the catalog game-detail dialog no longer auto-focuses the search field (no more keyboard popping up unexpectedly).
- **Auto-link after APK install** — newly installed apps are rescanned and matched against the catalog immediately, no manual Refresh needed.
- File pickers remember the last folder you browsed; subsequent picks reopen at the same place.
- **Menu reorganized**:
    - New **Install** submenu (APK + game-in-JoiPlay + JoiPlay settings) and **Backup & config** submenu (app backup + JoiPlay backup import).
    - **Help** submenu now contains documentation, about, support, and all diagnostics in one place.

## v0.41.0

- **RAR5 support** via vendored RARLAB unrar (arm64 devices). Tries native first; falls back to junrar (RAR4-only) on other architectures or when extracting via SAF.
- APK gained ~900 KB for the native library.

## v0.40.x

- v0.40.1 — Catalog "Rating" sort now uses views as a tie-breaker so popular games rank above obscure ones with the same rating.
- v0.40.0 — Catalog tab gains a **Refresh** button and "Updated Xh ago" subtitle in the top bar. Removed the now-obsolete "Extract & install" and "Set JoiPlay games folder" menu entries.

## v0.39.0

- **Install APK** flow: pick an `.apk` directly or pick an archive (zip/rar/7z) → app extracts → file browser highlights `.apk` candidates → system installer opens. Optional "Delete after install" checkbox verifies via Package Manager before deleting.
- JoiPlay now receives raw `file://` URIs so it can scan game folders (fixes "path not found" after extract).
- Extraction progress reports on a 200 ms heartbeat in addition to the byte threshold — no more 15 s freezes during slow flushes.
- Extract confirm dialog gains an optional **Delete archive after extraction** checkbox.

## v0.38.x

- v0.38.2 — Confirm-before-extract dialog showing source/dest. Finer progress reporting. Better RAR5 error message (now historical — see v0.41 for full RAR5 support).
- v0.38.1 — File-picker for "Install game in JoiPlay" now lists archives too; archives route through the extract flow.
- v0.38.0 — Custom tree picker for the install flow (previously SAF-based).

## v0.37.x

- v0.37.1 — Removed obsolete "storage strategy" section; added **+ New folder** button in the tree picker.
- v0.37.0 — Both source and destination pickers use a custom file-tree (works on devices where SAF refuses to grant the Downloads folder).

## v0.36.x

- v0.36.1 — Phase-labelled progress dialog (Preparing / Extracting).
- v0.36.0 — Custom **folder picker** with lazy-expand tree, "Use this folder" + Cancel.

## v0.35.x

- v0.35.1 — Reactive permission status (red banner clears as soon as you grant access).
- v0.35.0 — **Extract & install** flow (later folded into the standard Install in v0.39).

## v0.34.x

- v0.34.1 — Show home-screen (launcher) name in row title and expansion when it differs from the app's manifest label.
- v0.34.0 — Fix version-comparison: `0.4` is no longer treated as equivalent to `0.4.7b`. Replaced "F95 latest" with "Installed version" in the row expansion. Internal cleanup.

## v0.31.0

- **Stripe donations** added alongside Buy Me a Coffee. The ☕ icon and menu
  now open a chooser when both options are configured. See
  [Support the project](support.md).

## v0.30.0

- **Help link** in the menu and About dialog pointing at the online docs
  (this site).

## v0.29.0

- **Donate URL** baked into the default app config — fresh installs now show
  the ☕ icon.
- **Auto-backup safety net** added. Every app upgrade triggers a snapshot of
  your state; **Backup & config → Restore auto-backup…** lets you list and
  restore. See [Auto-backups](backup/auto-backup.md).

## v0.28 series

- v0.28.10 – Startup prune of JoiPlay backup entries whose folders no
  longer exist. See [Delete a JoiPlay game](joiplay/delete-game.md).
- v0.28.9 – Progress dialog while a JoiPlay folder is being deleted;
  deletion now persists across launches.
- v0.28.8 – JoiPlay delete walks the granted SAF tree relative to the
  game's `storagePath`, so games nested in sub-folders work.
- v0.28.7 – Menu **JoiPlay → Set JoiPlay games folder…** added. Submenus
  use visual nesting (left accent bar + tinted background, expand/collapse
  chevron).
- v0.28.5 – Open Folder targets Samsung **My Files** directly when present.
- v0.28.4 – Open Folder accepts paths in Samsung Secure Folder / non-zero
  user-ID emulated storage.
- v0.28.3 – Catalog search requires **all** query tokens to match (drops
  partial-token tier).
- v0.28.2 – Open Folder uses proper SAF tree URI for the fallback picker.
- v0.28.0 – **Multi-select**: long-press a row to enter selection mode,
  then bulk Hide / Unhide. See [Main screen](main-screen.md).

## v0.27 series

- v0.27.1 – Catalog search precomputes per-game lowercase / normalized /
  tokens, dropping per-keystroke cost to <10 ms. Catalog title shown
  under the local label when they differ.
- v0.27.0 – Edit dialog gains a **Search catalog** box with live results
  and a **Not on F95** button. See
  [Manual search](mapping/manual-search.md) and
  [Not on F95](mapping/not-on-f95.md).

## v0.26 series

- v0.26.3 – Catalog search results sorted alphabetically.
- v0.26.2 – First-run refresh detached from `LaunchedEffect` (no more
  self-cancellation mid-scan).
- v0.26.1 – First-run waits for the catalog if it's still downloading.

## How to read this changelog

Each change ideally links to its docs page. Bug fixes that don't add or
remove user-visible behavior are kept short.
