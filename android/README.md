# First Principles Studio: Android app

The studio in a WebView, so the app looks and works like the web version. The files in `app/src/main/assets/` are copies of `extension/index.html` and `extension/app.js`. If you change the studio, copy those two files again.

## Build the APK

You need Android Studio, or the Android SDK with JDK 17+ and Gradle.

```
cd android
./gradlew assembleDebug      # or: gradle assembleDebug
```

The debug APK is at `app/build/outputs/apk/debug/app-debug.apk`. Copy it to your phone and install it, after allowing installs from that source.

## Brains on the phone

- **Claude or Gemini API key** works anywhere. Open Settings, pick Claude or Gemini, and paste your key. The key stays on the phone.
- **Ollama on your PC** works on the same Wi-Fi only. Set the Ollama address to your PC's LAN address, for example `http://192.168.1.20:11434`. On the PC:
  - set `OLLAMA_HOST=0.0.0.0` so Ollama listens on the network,
  - set `OLLAMA_ORIGINS="https://appassets.androidplatform.net"`,
  - allow port 11434 through the firewall.

## Known limits (v0.1)

- Voice input is not available in the WebView. Typing works.
- Links to Wikipedia and YouTube open in the phone's browser.
- The APK is debug-signed. For Play Store release, create a release key and sign with it.
