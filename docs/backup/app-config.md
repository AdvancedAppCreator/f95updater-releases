---
title: App config
last_updated: 2026-05-25
---

# App config

The app config controls optional links and private diagnostics behavior.

## Where to find it

Menu -> **Backup & config** handles normal backups. Advanced users can also
drop an `app_config.json` file into one of these public locations:

- `Documents/F95Updater/app_config.json`
- `Documents/app_config.json`

The app checks those locations on launch and when you return from Android
settings. If the drop-in file differs from the private copy, it is imported even
when timestamps are unreliable.

## What it can configure

Depending on the build, app config may include:

- Donation/support URLs.
- Diagnostics upload settings.
- Private updater settings for test builds.

Public builds work without any app config file.

## Multiple update feeds

Advanced/dev configs can keep the normal public updater feed and add private
feeds:

```json
{
  "versionInfoUrl": "https://github.com/AdvancedAppCreator/f95updater-releases/releases/latest/download/version.json",
  "versionInfoUrls": [
    "https://example.blob.core.windows.net/app/version.json"
  ]
}
```

The app checks every non-empty URL from `versionInfoUrl` and `versionInfoUrls`,
deduplicates exact repeats, and offers the update with the highest
`versionCode`. Existing configs that only use `versionInfoUrl` keep working.

## Troubleshooting

If the app does not pick up a new config file, use **Help -> Save local
diagnostics** and check the log. It records which candidate folders and files
were checked.
