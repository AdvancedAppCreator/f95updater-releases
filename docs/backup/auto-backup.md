---
title: Auto-backups
last_updated: 2026-05-20
---

# Auto-backups

The app keeps an automatic safety net: on every successful upgrade, it
snapshots your current mappings, hidden list, JoiPlay backup, version
overrides, and deleted-game IDs to a JSON file inside the app's private
storage.

## When auto-backups are created

- **First launch on every new version code.** Compared against a stored
  "last seen" value in DataStore. The snapshot is tagged with the
  **previous** version (the state you'd want to recover).
- **Manually** via the **Snapshot now** button in the restore dialog (see below).
- **Before every restore.** When you restore one auto-backup, a fresh
  "prerestore" snapshot is taken first so you can roll back the rollback.

The first-ever launch is skipped (nothing meaningful to back up yet).

## Where they live

`<app private files dir>/auto_backups/auto-vNN-yyyyMMdd-HHmmss.json`

The 5 newest are kept. Older ones are pruned automatically.

> Auto-backups survive app upgrades but **NOT uninstall**. For
> uninstall-proof backups, periodically use
> [Export backup](export-import.md) to a SAF location.

## Restore dialog

Menu → **Backup & config** → **Restore auto-backup…**.

You'll see:

- An entry per backup with **from version**, **date**, **size**, and the filename.
- **Restore** — opens a confirmation dialog. On confirm, the app takes a
  prerestore snapshot, applies the backup, and rescans.
- **🗑** — delete a specific backup file.
- **Snapshot now** — create a new backup right now (useful before risky manual changes).
- **Close** — leave the dialog.

## What gets replaced on restore

Restore uses the same import path as
[Import backup](export-import.md): mappings, hidden, JoiPlay snapshot,
version overrides, and JoiPlay deleted-IDs are all replaced.

Things **not** touched:

- Permission grants.
- The catalog file itself.
