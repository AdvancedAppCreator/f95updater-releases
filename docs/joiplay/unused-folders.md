---
title: Probably unused JoiPlay folders
last_updated: 2026-05-24
---

# Probably unused JoiPlay folders

This tool compares your JoiPlay folders against a `.joiback` backup and reports
folders that probably are not referenced by JoiPlay anymore.

## Where to find it

Menu -> **Backup & config** -> **Probably unused JoiPlay folders...**

## What it does

1. You choose the JoiPlay games root folder.
2. You choose a `.joiback` backup.
3. The app reads the backup and compares the game paths inside it with sibling
   folders on disk.
4. A progress dialog is shown while the scan runs.
5. The report can be copied or saved.

The scan is review-only. It does not delete folders.

## Permissions

This feature needs **All files access** so it can list game folders on disk.
If access is missing, the app explains why and opens Android settings.

## Tips

Re-export your JoiPlay backup before running this report. A fresh backup gives
the most accurate view of what JoiPlay currently knows about.
