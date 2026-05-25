---
title: Manual catalog search
last_updated: 2026-05-24
---

# Manually map an app via catalog search

When auto-match doesn't find the right F95 thread — or finds the wrong one —
use the catalog search inside **Edit mapping**.

## Open the Edit mapping dialog

Tap the **✏️ pencil** icon on any row.

<!-- screenshot: mapping-edit-dialog.png -->

The dialog shows:

- The app's package name, install dates, sizes.
- Current mapping (F95 latest version, acknowledged version).
- **Search catalog** box — pre-filled with the app's label.
- **Fuzzy find** — tries a relaxed catalog search when the normal search is too
  strict.
- **Search external sources** — searches configured external mirrors and saves
  picked results as manual/external matches.
- **Paste a thread URL** field below, for when search can't find it.

## Search behavior

The search runs over the local catalog (30,000+ titles) with these priorities:

| Score | Match type |
|------:|------------|
| 1000  | Exact normalized title (lowercase, alphanumerics only) |
| 950   | Title **starts with** your query |
| 900   | Title **contains** your query as a substring |
| 850   | Every word in your query is a prefix of some word in the title |

Results are case-insensitive and **sorted alphabetically** by title. Up to 25
hits are shown.

> If you type multiple words and **none of them** combine into a real title,
> the list is empty rather than dropping back to single-word matches. This
> keeps "Sis Lus" from showing every game with "Lust" in the name.

## Tap a result

Tapping any result instantly:

- Sets `f95Url` to `https://f95zone.to/threads/<thread_id>/`
- Sets `threadId`
- Updates `lastSeenVersion` from the catalog
- Clears the **Not on F95** flag (if set)
- Closes the dialog with a "Mapped to '<title>'" snackbar.

## Other dialog options

- **Save URL** – saves whatever you've pasted in the URL field.
- **Mark installed** – sets `acknowledgedVersion = lastSeenVersion`, clearing
  the red "update available" status.
- **Hide / Unhide** – hide this row from the main list.
- **[Not on F95](not-on-f95.md)** – mark the app as not present on F95Zone so
  auto-match leaves it alone forever.
- **Clear URL** – remove the mapping entirely.
- **Cancel** – close without saving.

On wide/landscape/unfolded screens, the dialog uses a split layout: app details
and search inputs stay on the left, while search results appear on the right.
The action buttons use one horizontally scrollable row to keep more vertical
space for results.
