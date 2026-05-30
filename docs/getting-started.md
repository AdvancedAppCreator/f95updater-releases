---
title: Getting started
last_updated: 2026-05-29
---

# Getting started

F95 Updater is now the legacy F95-only app. New multi-source development has
moved to Adult Game Manager, and recent F95 Updater builds show a one-time
startup notice with links to the AGM thread and APK download.

When you launch F95 Updater for the first time, three things happen
automatically after you continue past that notice.

## 1. Welcome dialog

You'll see a short welcome dialog with two options:

- **Continue** – proceeds with a catalog match on every Android app installed
  on your phone.
- **Import JoiPlay backup…** – if you also use JoiPlay, the app explains why it
  needs scoped access to your backup folder, then lets you pick the `.joiback`
  file. After import, the catalog match runs over both your Android apps **and**
  your JoiPlay games together.

<!-- screenshot: getting-started-welcome.png -->

> If you don't use JoiPlay, just tap **Continue**.

## 2. Catalog download

The app fetches the latest F95Zone catalog (~8 MB) in the background. If you
already have a recent copy cached, it does a quick HTTP 304 check instead and
keeps the cached version.

The catalog is a single JSON file listing every known F95Zone game and its
latest version. It powers the auto-match and the search inside
[Edit mapping](mapping/manual-search.md).

## 3. First-run catalog match

Once the welcome flow is done and the catalog is ready, the app walks every
installed app + JoiPlay game and tries to match it to a catalog entry by:

1. Thread ID (if you already had a mapping).
2. Exact normalized title (lowercase, alphanumerics only).
3. Word-prefix fuzzy match (so "MyGame v0.1.2 pc" matches "My Game").

A progress dialog shows scan progress with ETA. When it completes, every
matched row gets its F95Zone thread, latest version, and color status set.

## What to do next

- Open any row to see details, or tap the **🌐 globe** icon to open the F95
  thread.
- For unmatched rows, tap the **✏️ pencil** to open
  [Edit mapping](mapping/manual-search.md) and search the catalog by hand.
- Long-press a row to enter **multi-select** mode (great for bulk-hiding
  non-game apps) — see [Main screen tour](main-screen.md).
- Run [Auto-hide non-games](catalog/auto-hide.md) to clean up the list.
- If Android asks for a permission, see [Permissions](permissions.md) for what
  each one is used for.
