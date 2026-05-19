---
title: Mark "Not on F95"
last_updated: 2026-05-18
---

# Mark an app as "Not on F95"

Some Android apps look like games but aren't on F95Zone — system utilities,
non-F95 games, work apps, etc. Without action, every **Refresh from catalog**
keeps trying to match them and may pick up false positives.

The **Not on F95** flag fixes that.

## How to set it

1. Tap **✏️** on the row.
2. In the bottom button row, tap **Not on F95**.

<!-- screenshot: mapping-not-on-f95.png -->

The dialog closes and the app is now:

- Skipped on every future auto-match.
- Shown in the list with a red "Marked as not on F95" note in the Edit dialog.

## How to undo it

Open the same dialog again — the button now reads **On F95 after all**. Tap
it to clear the flag. Auto-match will re-evaluate this row on the next
refresh.

## When to use this vs Hide

| | Hide | Not on F95 |
|---|---|---|
| Row appears in main list | No (unless "Show hidden apps") | Yes |
| Auto-match re-runs on this row | Yes | **No** |
| Catalog match might overwrite your settings | Yes | No |
| Use it for | Apps you don't care about at all | Apps you want to keep tracking but aren't on F95 |

Tip: for system / utility apps you don't care about, **Hide** is easier
(especially in bulk via long-press). For games that genuinely aren't on
F95Zone, **Not on F95** is the right choice.
