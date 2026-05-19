---
title: Auto-hide non-games
last_updated: 2026-05-18
---

# Auto-hide non-games

After your first refresh, the list will likely contain a lot of Android apps
that aren't games — system utilities, launchers, work apps, etc. This menu
item bulk-hides the obvious ones in one tap.

## How to run it

Menu → **Catalog** → **Auto-hide non-games**.

The snackbar reports how many apps were hidden, e.g. `Auto-hid 47 likely
non-games`.

## Detection rules

An app is auto-hidden when **all** of these are true:

- It's an Android app (JoiPlay games are never auto-hidden).
- It has no F95 catalog match (thread ID not set).
- It matches one or more "non-game" heuristics: known launcher / IME /
  system / OEM package prefixes, or has the `LAUNCHER` category without a
  game-like activity declaration.

This is intentionally conservative — it doesn't hide anything that has even
a tentative F95 mapping. False positives can be unhidden via **menu → Show
hidden apps**, then long-press → **Unhide**.

## See also

- [Main screen tour – multi-select](../main-screen.md#multi-select) –
  long-press to bulk hide rows that auto-hide missed.
