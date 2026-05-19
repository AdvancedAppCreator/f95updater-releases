---
title: Paste a thread URL
last_updated: 2026-05-18
---

# Paste a thread URL manually

If a game isn't in the local catalog yet (e.g. a brand-new release the
catalog crawler hasn't picked up), you can map it directly by URL.

## Steps

1. In a browser, search F95Zone for the game and open its thread.
2. Copy the URL from the address bar. Anything containing
   `f95zone.to/threads/<digits>/` works.
3. Back in the app, tap **✏️** on the row → paste into the
   **F95Zone thread URL** field → tap **Save URL**.

<!-- screenshot: mapping-paste-url.png -->

## What the app extracts

The thread ID is parsed from the URL with the regex
`f95zone\.to/threads/(?:[^/]*\.)?(\d+)`. Both these forms work:

- `https://f95zone.to/threads/53058/`
- `https://f95zone.to/threads/my-game-name.53058/`

The app then stores the canonical form `https://f95zone.to/threads/53058/`.

## What happens after saving

- The `notOnF95` flag is cleared automatically.
- Tap **🔄** on the row to fetch the latest version from F95Zone (via
  scraping), or wait for the next **Refresh from catalog** to pick up the
  version once the catalog includes this thread.
