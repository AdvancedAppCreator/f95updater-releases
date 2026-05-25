---
title: Refresh from catalog
last_updated: 2026-05-24
---

# Refresh from catalog

Re-matches **every** app and JoiPlay game against the local catalog. Use this
after:

- Importing a `.joiback` (auto-runs).
- A catalog sync brought in new entries that didn't exist when you last
  refreshed.
- You manually changed many mappings and want versions reconciled.

## How to run it

Menu → **Refresh from catalog**.

A non-dismissible progress dialog shows the current row, the running matched
count, and an estimated time remaining. You can **Cancel** at any time — work
done so far is kept.

Performance: ~200 apps complete in well under a minute. Each app uses indexed
catalog lookups instead of scanning the full 30,000+ game list linearly.

## What gets touched

For each row:

- Matched → mapping is updated with the new thread ID, URL, and latest
  catalog version.
- Unmatched → mapping is **not** cleared; whatever you had before is kept.
- Marked [Not on F95](../mapping/not-on-f95.md) → skipped entirely.
- `acknowledgedVersion` is **preserved** (so "I've already installed this
  update" status survives).

## Submenu options

The full **Catalog…** submenu also includes:

- [Sync catalog now](sync.md) — download a fresh catalog.
- [Review unmapped games](review-unmapped.md) — manually resolve rows that did
  not get a safe match.
- **Overwrite manual matches on refresh** — let future refreshes replace
  manual/external matches. Leave this off if you want manual choices protected.
- [Auto-hide non-games](auto-hide.md) — hide system utilities and obvious
  non-games in one tap.
- **Reset all acknowledgements** — clear the "I installed this version"
  acknowledgement on every row, so red "update available" dots reappear for
  anything you haven't actually updated.
