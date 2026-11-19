# UDM stable update channel

This folder is dedicated to the Android download manager **UDM** by **Usman** and is separate from the Studio and App Hub release channels.

- Installed Android package: `com.udm.beta` (retained for seamless upgrades from the tested beta).
- Private development and engineering source remain in the separate, access-controlled `usmanjhawri/UDM` repository.
- Public binary releases use tags `udm-vX.Y.Z` and APK filenames `UDM-X.Y.Z.apk`.
- Active signed feed: `latest.txt` (only present **after** a reviewed, manually authorized publication).
- Feed includes Base64-encoded properties (`package`, `channel`, `versionName`, `versionCode`, `url`, `sha256`, `notes`) and a detached RSA SHA-256 signature. The app verifies it with the signing certificate already installed on the device.
- Updates require increasing Android `versionCode`; Android must separately approve and validate installation. UDM does **not** download and silently install packages.
- Do not add signing keys, secret tokens, private engineering sources or user media to this repository.

Publishing a new UDM release must not change `studio/latest.json` or the App Hub `releases/latest` pointer.
