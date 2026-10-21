# DMoneyTest — Google Drive Backup Test

This repository is an isolated test copy of DMoney 2.2. The original `DMoneyApp/DMoney` repository has not been changed.

## Test website

https://dmoneyapp.github.io/DMoneyTest/

If Pages is not publishing, open **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/(root)`, then save.

## Google OAuth

Use the same Google Cloud project as the DMoney Android APK where possible. Enable **Google Drive API** and use a **Web application** OAuth client with this Authorized JavaScript origin:

`https://dmoneyapp.github.io`

Enter only the Web Client ID in the website. Never paste a client secret into the static website.

## Backup and restore compatibility

The test UI includes:
- **Back up now** and dated Drive backup history.
- **Restore from Google Drive (APK backup)** to restore the latest available valid backup.
- **Restore APK backup JSON (.json)** to import a JSON backup file exported by the Android app.
- Compatibility with DMoney profile-based JSON backups and Android `dmoney-web-storage` snapshots. Android snapshots with a SHA-256 checksum are checked before restore.

Restoring replaces website data, after confirmation. The website's current OAuth Client ID and automatic-backup setting are retained. Use disposable test data until actual Google Drive backup/restore has been accepted on the website and the APK.

## Current verification status

The updated HTML is committed to `main`. The restore paths have been checked structurally, but end-to-end Drive visibility, real APK backup restore, and the latest GitHub Pages deployment still require a live test. Do not use this test site as the only copy of real financial data.
