# Stock Issue – Android APK

## Easiest: build the APK with GitHub (no Android Studio needed)
1. Create a new GitHub repository and upload everything in this folder
   (keep the `.github/workflows/build.yml` file).
2. Open the repo > Actions > "Build APK" > wait ~5 minutes for the green tick.
3. Open the finished run > Artifacts > download `stock-issue-apk` (a zip holding app-debug.apk).
4. Copy app-debug.apk to the phone, open it, and allow "Install unknown apps" when asked.

## Or build on a computer (Node 20, Java 17, Android Studio/SDK installed)
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

## Notes
- Works fully offline (Excel library is bundled in www/).
- Export to Excel opens the phone's share sheet: save to Files/Drive or send via WhatsApp/email.
- Data is stored inside the app on that phone. Uninstalling the app erases it, so export regularly.
- The app is a debug-signed build, which is fine for installing directly on your own devices.
