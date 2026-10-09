# English Adventure – Android (Capacitor)
Status: project files only. The APK has NOT been built yet.

## Build locally (Node 20+, JDK 17, Android Studio/SDK installed)
npm install
npx cap add android
npm run assets      # needs assets/icon-only.png (1024x1024)
npx cap sync android
npm run apk
Output: android/app/build/outputs/apk/debug/app-debug.apk

## Build without installing anything (GitHub)
Upload this folder to a new GitHub repo, open Actions -> "Build APK" -> Run workflow,
then download the artifact "english-adventure-debug-apk".

## Install on phone
Copy app-debug.apk to the phone, allow "install unknown apps", open it.
Debug APK is for testing; Play Store needs a signed release (AAB) build.

## Notes
- Progress is stored in WebView localStorage (kept after closing the app).
- AI tutor: relies on Claude's page runtime, so it shows "disabled" in the APK.
  To enable it, add your own server endpoint that holds the API key and call it from the app. Never put keys in the APK.
- Google Fonts load online only; offline falls back to system fonts.
