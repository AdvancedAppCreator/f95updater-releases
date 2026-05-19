# Docs maintenance rules

These rules are read by AI coding agents (and humans!) that modify the app. They
exist to keep this help site in sync with the shipping app.

## Hard rules

1. **Any UI change requires a docs change in the same release.** If you add,
   rename, remove, or change the behavior of any menu item, dialog, screen, or
   row icon, update the matching page under `docs/`.
2. **Each menu item / feature has exactly one canonical page.** Use the
   navigation map in `mkdocs.yml` to find it.
3. **Update `docs/changelog.md`** with one line per user-visible change, linking
   to the affected docs page(s).
4. **Bump the `last_updated:` front matter** at the top of every page you touch
   to today's date (YYYY-MM-DD).
5. **Screenshots live in `docs/screenshots/`.** Reference with
   `![alt](screenshots/filename.png)`. Filenames follow the pattern
   `<feature>-<state>.png` (e.g. `mapping-edit-dialog.png`).
6. **Help is published from `main`.** A push to `docs/**` or `mkdocs.yml` runs
   `.github/workflows/docs.yml`, which deploys to GitHub Pages.

## Page conventions

- Front matter:
  ```yaml
  ---
  title: <Page title>
  last_updated: 2026-05-18
  ---
  ```
- Open with a one-sentence summary of what this feature does.
- "Where to find it" section: exact menu path or row interaction.
- "What it does" section: concrete behavior.
- "Tips" / "Troubleshooting" sections only if useful.

## Feature → page map (cross-reference)

When changing code in `MainActivity.kt`, look up the affected feature here:

| Code location                                       | Page                                       |
| --------------------------------------------------- | ------------------------------------------ |
| First-run welcome dialog                            | `docs/getting-started.md`                  |
| Row card icons / status colors                      | `docs/main-screen.md`                      |
| Multi-select toolbar                                | `docs/main-screen.md` (Multi-select)       |
| `EditMappingDialog` (search + URL + flags)          | `docs/mapping/manual-search.md`            |
| `notOnF95` flag                                     | `docs/mapping/not-on-f95.md`               |
| `refreshFromCatalog` button                         | `docs/catalog/refresh.md`                  |
| Catalog → Sync catalog now                          | `docs/catalog/sync.md`                     |
| Catalog → Auto-hide non-games                       | `docs/catalog/auto-hide.md`                |
| JoiPlay submenu                                     | `docs/joiplay/*.md`                        |
| `JoiPlayScanner.deleteFolder`                       | `docs/joiplay/delete-game.md`              |
| `AutoBackupManager`                                 | `docs/backup/auto-backup.md`               |
| `AppConfigStore` (drop-in + import/export)          | `docs/backup/app-config.md`                |
| `AppLog` / `CrashReporter` upload UI                | `docs/diagnostics/*.md`                    |
| `AppUpdater.check`/`install`                        | `docs/self-update.md`                      |

If you add a new menu item, add a row to this table and create the page.

## Local preview

```sh
pip install mkdocs-material pymdown-extensions
mkdocs serve  # http://127.0.0.1:8000
```
