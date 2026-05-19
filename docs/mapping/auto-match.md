---
title: Auto-match
last_updated: 2026-05-18
---

# Auto-match (Refresh from catalog)

The app matches every installed app and JoiPlay game to its F95Zone thread
using the local catalog — no network round-trip per app, no scraping.

## When auto-match runs

- **First launch** – right after the welcome flow finishes.
- **Manually** – menu → **Refresh from catalog**.
- **After importing a `.joiback`** – just on the newly-imported JoiPlay games.

## How the match is decided

For each row, the app tries these strategies in order, stopping at the first
hit:

1. **Thread ID from existing mapping** – if you mapped it before, the existing
   thread ID is preserved across refreshes.
2. **Thread ID parsed from the saved URL** – e.g. `f95zone.to/threads/53058/`.
3. **Exact title match** – lowercase + alphanumerics-only equality.
4. **Word-prefix fuzzy match** – the app label and the catalog title are
   broken into words (stripping platform/version suffixes like `pc`, `v1.2`).
   The shorter word list must be a prefix of the longer one. Short
   single-token labels (under 5 chars) are rejected to avoid false positives
   like "ADM" → "The Headmaster".

Rows you've marked [Not on F95](not-on-f95.md) are skipped entirely.

## Progress UI

While the refresh runs, a non-dismissible dialog shows:

- progress bar with `current / total`
- live "matched" count
- estimated time remaining (after the first few rows complete)
- a **Cancel** button — your existing mappings are preserved even if you
  cancel midway.

## What it writes

For every matched row, the mapping is updated with:

- canonical URL `https://f95zone.to/threads/<thread_id>/`
- `lastSeenVersion` from the catalog
- `threadId` and `lastChecked` timestamp
- your existing `acknowledgedVersion` is preserved (so "you've seen this
  update already" status survives refreshes).
