---
title: Verbose mode
last_updated: 2026-05-18
---

# Verbose logging

Toggle that lets the log record extra debug-level details. Off by default
because verbose logs grow quickly.

## How to toggle

Menu → **Diagnostics** → **Verbose logs: off** (toggles to **ON**).

The label flips to **Verbose logs: ON** when active and the change takes
effect immediately. A snackbar confirms.

## What changes

With verbose ON, the app additionally logs:

- Per-row catalog match decisions (which strategy hit, score, candidates).
- Drop-in `app_config.json` scan attempts (each location it checked).
- HTTP request headers / response codes for catalog and version-info fetches.
- JoiPlay folder existence probe results.

## When to enable it

- Before reproducing a hard-to-diagnose bug (then save / upload logs).
- After getting a "please enable verbose and try again" instruction.

## Don't leave it on

Verbose logs rotate faster, so historic detail is lost sooner. Turn it back
off once you've captured what you need.
