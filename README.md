# Usman App Hub — Official APK Releases

This public repository distributes **signed Android APKs** and version-specific checksums for **Usman App Hub**. The app's development source and signing credentials are kept outside this release repository.

## Current stable release

**Usman App Hub 4.0.0** · Android version code **50** · published **18 October 2026**

- [Download the latest official APK](https://github.com/usmanjhawri/Usman-App-Hub-Releases/releases/latest)
- [View the 4.0.0 release](https://github.com/usmanjhawri/Usman-App-Hub-Releases/releases/tag/v4.0.0)

### Installing or updating

If you already have Usman App Hub installed, open **Settings → Check for updates**. An eligible newer release can be installed **without uninstalling** when the package identity and signing certificate match. Android will ask you to approve installation.

If installing manually, download the APK from a release above and follow Android's installation prompts. Do **not** disable Android security checks to force an installation.

### Security and checksums

Each published family update is built using the existing application identity and signing certificate and has a `SHA256SUMS.txt` file alongside its APK. Verify that checksum before distributing files through other channels. APK files from unrelated third-party catalogues are **not** part of this repository's official release assets.

Earlier preview and RC releases are retained for traceability. Android generally blocks in-place downgrades, and uninstalling an app may erase its private data.

## Repository boundaries

This repository is the **public update channel only**. Development source, private release pipelines and the app's original signing key are managed separately. **Do not delete, rename, privatize or replace this repository** without first migrating the app's configured update URL and verifying the migration.

No signing keys, private CI artifacts, or account credentials should ever be committed here.
