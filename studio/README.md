# Usman Studio — independent verified APK updates

This is the dedicated public update channel for **Usman Studio**, distinct from the **Usman App Hub** release channel.

The Studio app uses [latest.json](./latest.json) for its opt-in updater:
- Android package: `com.usman.videodownloader.studio`
- Public Studio tags: `studio-v2.13.0` for app version `2.13` (the extra `.0` is required by the in-app release validator)
- Public signed APK filename: `Usman-Studio-v2.13.apk`
- APK updater verifies the published SHA-256, exact size, package name, increasing Android versionCode, and original Studio signing certificate before asking Android to install.

## Safe publishing

Studio's **private source repository** has a separately approved release process:
1. Build, test and sign the Android APK **privately using the original Studio signing key**.
2. Stage the *signed APK only* in a **private** Studio candidate release. Keep JKS/passwords and media data offline.
3. Use **Actions → Publish verified Studio update (manual)** from the private Studio source repo, supplying the exact version, Android code, reviewed source commit, and signed APK checksum, with explicit `PUBLISH-STUDIO` approval.
4. The workflow rechecks source CI, APK integrity, original Studio certificate and no-downgrade policy; publishes an immutable Studio-specific release, passing `--latest=false`; **only after that** moves this folder's `latest.json` to `published`.

The workflow deliberately **does not change** App Hub's own `v4.0.0` tag or `/releases/latest` pointer.

## Current state

Until a signed and device-verified release has passed the public approval gate, [latest.json](./latest.json) remains **`unpublished`**. No sample checksum, unsigned APK, or test build should be presented as an official update.

Never store private source, signing keys, passwords, authentication cookies or user-downloaded media in this public distribution repository.
