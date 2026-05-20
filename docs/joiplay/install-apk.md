# Install APK

The **Install APK** flow lets you sideload any `.apk` file you have on your phone — including ones inside ZIP / RAR / 7Z archives — without having to dig through file managers manually.

Open the menu (top-right **⋮**) → **Install ›** → **Install APK…**

## How it works

1. You're presented with a custom folder tree starting at internal storage. Navigate to your archive or APK.
2. Tap the file you want to install:
    - **`.apk`** → confirm dialog opens immediately.
    - **`.zip` / `.rar` / `.7z`** → the archive is extracted into your destination folder (the same one configured in **JoiPlay settings**), and then a file browser is shown so you can pick the APK inside.
3. The confirm dialog shows the APK's full path. If the app can write to the source file, you'll see a **Delete the APK after a successful install** checkbox — leave it off if you want to keep the file, tick it to clean up automatically.
4. Tap **Install**. The system installer opens; confirm there.
5. After the installer returns, the app verifies the package was actually installed (via Package Manager) before deleting the source if you opted in.

## Permissions required

- **All-files access** (MANAGE_EXTERNAL_STORAGE) — so the picker can browse your full storage.
- **Install unknown apps** (REQUEST_INSTALL_PACKAGES) — granted via the system prompt on first install attempt.

The first time you tap **Install APK…** the app may show *"Grant All-files access first (JoiPlay settings)"* — open the **Install › JoiPlay settings** entry to grant it, then come back.

## After install

The app rescans your installed packages and re-runs **Refresh from catalog** automatically, so the newly installed game appears linked to its F95 thread without you having to tap Refresh manually.

## Tips

- The picker remembers the last folder you browsed across all installer flows.
- If you keep all your game archives in one Downloads folder, the second-and-onwards visit lands you right there.
- Archive extraction supports password-protected archives; you'll be prompted if the archive is encrypted.
- RAR5 archives are supported on arm64 devices (most modern phones); RAR4 works everywhere.
