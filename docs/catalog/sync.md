---
title: Catalog sync
last_updated: 2026-05-18
---

# Catalog sync

The **catalog** is a single JSON file (gzipped, ~8 MB) listing every known
F95Zone game with title, thread ID, latest version, creator, tags, cover URL,
rating, and views. Everything the app does — search, auto-match, version
status — runs against this local file.

## Where the catalog comes from

A crawler runs on a backend server, fetches the latest data, and uploads the
resulting `catalog.json.gz` and `labels.json` to a fixed GitHub Release
(`catalog` tag) on the `f95updater-releases` repository.

The app fetches from:

- `catalog.json.gz` — the full game list
- `labels.json` — human-readable names for tag/prefix IDs

Both use HTTP `ETag` / `If-None-Match`, so subsequent syncs return **HTTP
304** (no download) when nothing has changed.

## When the catalog syncs

- **On every app launch** — automatically, in the background.
- **Manually** — menu → **Catalog** → **Sync catalog now**.

You'll see a snackbar:

- `Catalog updated: 25760 games (8 MB)` — fresh data downloaded.
- `Catalog already up-to-date` — server returned 304.
- `Catalog sync failed: <reason>` — see [Diagnostics](../diagnostics/logs.md).

## How fresh is "fresh"?

The crawler runs daily. Some catalog entries may lag the actual F95Zone
thread by up to a day. Use the **🔄** icon on a specific row to scrape that
single thread live if you need the absolute latest version right now.
