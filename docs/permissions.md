---
title: Permissions
last_updated: 2026-05-25
---

# Permissions

F95 Updater asks for advanced Android access only when a feature needs it.

## All files access

Menu -> **Grant all files access** opens Android settings for the
`MANAGE_EXTERNAL_STORAGE` permission. Grant it if you want to:

- Browse your storage with the in-app file picker.
- Install APKs or JoiPlay games from archives.
- Delete JoiPlay game folders.
- Scan for probably-unused JoiPlay folders.

When access is already granted, the menu item changes to **Revoke all files
access** and opens the same Android settings page.

## Usage data access

Menu -> **Grant usage data access** opens Android usage-access settings. This is
optional and only lets the app show **Last used** dates and sort/filter by them.

When access is already granted, the menu item changes to **Revoke usage data
access**.

## Scoped backup-folder access

Backup imports use Android's folder picker instead of broad storage access. The
first time you import a regular backup or a JoiPlay `.joiback`, the app explains
why it needs folder access and asks you to choose the folder containing the file.

Android persists that folder grant. F95 Updater remembers it across restarts and
reuses it for both **Import backup** and **Import JoiPlay backup (.joiback)** as
long as Android still reports the grant.

## Install unknown apps

The **Install APK** and self-update flows hand an APK to Android's package
installer. Android may ask you once to allow F95 Updater to install unknown apps.

## No analytics permission

The app has no analytics SDK and does not request contacts, location, camera, or
microphone access.

## Local-first trust model

F95 Updater does not require an F95Zone login, hosted account, or account sync.
It opens public F95 threads and GitHub-hosted app releases, but your mappings,
personal notes, ratings, hidden list, and JoiPlay data stay on your device unless
you export a backup or manually attach diagnostics to a report.
