# VOZLO — Official Android Updates

**Public APK distribution only.** The Android application source code lives in a separate private repository.

## Status

The official signed-release channel is **being configured**. No production APK has been published yet.

When activated, the VOZLO Android app will check for an available update, show download progress, verify the package, then open the Android installer for the user's confirmation.

## Releases

Only publish:
- Stable APK files signed using VOZLO's **same long-term release signing key**.
- `latest.json` with version, download URL, SHA-256 checksum, file size and release notes.
- Public release notes.

Never publish signing keys, passwords, tokens, customer data or private source code.

## Update manifest

The Android app reads `https://raw.githubusercontent.com/vozlo/vozlo-updates/main/latest.json`.

**Do not create a placeholder `latest.json` pointing to a nonexistent APK.** Publish it only once a signed, downloadable release has been verified.

Required manifest fields: `versionCode`, `versionName`, `apkUrl`, `sha256`, `bytes`, `notes`, `required`.

The updater checks HTTPS, package name, release version, APK checksum and matching signing certificate before opening the installer. Android can still require an installation confirmation.

## Operational security

Limit publishing permissions to this repository; retain encrypted offline signing-key backups separately from GitHub. This repository contains *no* application source code and must stay public for customers to download releases.
