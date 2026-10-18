# Usman Studio secure update channel

This public folder is separate from Usman App Hub's update checks. Studio's private
source and signing credentials stay in its private repository or offline backup.

The native Studio update checker reads [latest.json](latest.json). This manifest
must stay in the "unpublished" state until all release gates pass.

To publish a verified Studio APK:
1. Rebuild v2.5 from its reviewed private source and the existing private baseline
   and Studio signing certificate. Never upload a key, password, or baseline APK.
2. Run all local package checks and device tests, including upgrade preservation.
3. Create a GitHub **prerelease** in this repository with tag `studio-v2.5.0`
   and upload `Usman-Studio-v2.5.apk`. Pre-releases are deliberate: App
   Hub's own /releases/latest channel continues to refer to App Hub releases.
4. Independently calculate the signed APK's exact byte length and SHA-256.
5. Update latest.json to include the following exact fields:

```json
{
  "schema": 1,
  "status": "published",
  "package": "com.usman.videodownloader.studio",
  "versionName": "2.5",
  "versionCode": 25,
  "tag": "studio-v2.5.0",
  "filename": "Usman-Studio-v2.5.apk",
  "bytes": 60900000,
  "sha256": "replace-with-the-real-64-character-sha256-of-the-signed-apk",
  "notes": "Secure update checks and quality-selection refinements"
}
```

Do not publish the example byte length or hash: they are placeholders.
Studio checks the exact repository asset URL, SHA-256, byte length, APK package,
versionCode, and the currently installed signing certificate before it opens
the system installer with explicit user confirmation. Source CI alone is not
a release gate.
