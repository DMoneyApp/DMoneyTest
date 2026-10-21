# DMoneyTest — Google Drive Backup Test

This repository is an isolated test copy of the DMoney 2.2 Google Drive backup/restore candidate. The original `DMoneyApp/DMoney` repository has not been changed.

## Enable the test website

In GitHub, open **Settings → Pages**:
1. Under **Build and deployment**, choose **Deploy from a branch**.
2. Select branch **main** and folder **/(root)**.
3. Click **Save** and wait for GitHub Pages to publish.

Expected site URL: https://dmoneyapp.github.io/DMoneyTest/

## Configure Google OAuth for Drive testing

In Google Cloud Console, enable **Google Drive API** and create an OAuth client of type **Web application**. Add this Authorized JavaScript origin:

`https://dmoneyapp.github.io`

Paste the **OAuth Web Client ID** into DMoney's Google Drive Backup dialog. Do not put a client secret in this static website.

## Test safely

Use disposable test transactions/profile data first. Verify:
- Drive connection completes.
- Manual backup creates a dated JSON file in Drive.
- Backup history lists the created backup.
- Restore loads the selected backup correctly.
- Automatic backup works while the app remains open and connected.

**Status:** App uploaded; GitHub Pages and real Google Drive OAuth/API round-trip still need to be enabled and verified. Do not use this test site as the only copy of real financial data.
