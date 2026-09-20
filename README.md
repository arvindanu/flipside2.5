# Flipside for Android

A ready-to-build Android app that wraps the Flipside game. The game runs fully
offline inside the app. Your best score is saved on the phone.

## Option A: build in the cloud (nothing to install)

1. Make a free account at github.com and create a new repository.
2. Choose "uploading an existing file" and drag in the CONTENTS of this folder
   (app, gradle, build.gradle, settings.gradle, gradle.properties, .github, ...).
   If the `.github` folder doesn't come along (some computers hide it):
   Add file > Create new file, name it `.github/workflows/build-apk.yml`, and
   paste in the contents of `build-apk.yml` from this folder.
3. Commit. Open the Actions tab. "Build Flipside APK" starts on its own and
   takes about 3-5 minutes.
4. Open the finished run, scroll to Artifacts, download "Flipside-apk".
   Unzip it to get `app-debug.apk`.
5. Send the APK to your phone, open it, and allow "Install unknown apps" when asked.

## Option B: build with Android Studio

1. Install Android Studio and use File > Open on this folder.
2. Let Gradle sync (accept the default Gradle wrapper if it asks).
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. The file appears at `app/build/outputs/apk/debug/app-debug.apk`.

## Notes

- This makes a debug-signed APK. That's fine for your own phone, but it is not
  what you would upload to the Play Store.
- Needs Android 8.0 or newer.
- The INTERNET permission is only used to load the game's web font when you're
  online. Offline, the game falls back to your phone's default font.
- The game itself lives in `app/src/main/assets/index.html`.
