# JoiPlay settings

Open the menu → **Install › → JoiPlay settings…**

This dialog controls the file-system locations the app uses for the install / extract flows, and the storage permissions that gate them.

## Settings

### All-files access (MANAGE_EXTERNAL_STORAGE)

The app's file pickers (used for **Install game in JoiPlay** and **Install APK**) browse the full filesystem directly. This needs the **All files access** permission, which is granted via a system Settings page — not a regular runtime prompt.

The settings dialog shows whether access is currently granted (green) or missing (red) and provides an **Open settings** button. After granting, return to the app — the indicator updates automatically.

To **revoke** the permission later: Android **Settings → Apps → F95 Updater → Permissions → All files access → Don't allow**.

### Source folder

The folder the file pickers default to the first time you open them. (After your first pick, the picker just remembers wherever you last navigated to.) Typically your Downloads or Games folder.

### Destination folder

Where archives get extracted to when you install a compressed game (zip/rar/7z). The app creates a subfolder named after the archive (or the archive's common root folder) here.

### Install warning

The first time you use **Install game in JoiPlay** or **Install APK**, a warning explains what JoiPlay does on its side (or what the system installer will ask). If you tick *"Don't show again"* the warning is suppressed; you can re-enable it by clearing this option in JoiPlay settings.

## Notes

- The app uses standard File API (not SAF/DocumentFile) for both Source and Destination — much faster for big game folders, and lets it extract directly into game-folder structures JoiPlay can scan.
- If you ever need to use a SAF tree (e.g. a folder on a removable SD card that the File API can't reach), the picker will let you grant tree access on-demand. This is rare.
