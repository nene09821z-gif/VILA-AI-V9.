# VILA AI Studio V9 — Android APK

Bản Android native WebView, chạy độc lập khỏi Chrome. Giao diện VILA V8 được đóng trong APK; app có một proxy HTTP cục bộ để chuyển `/api/*` tới Node.js VILA Server. API key vẫn nằm ở server, không nằm trong APK.

## Chạy server
Node.js >= 18:

```bash
npm install
GEMINI_API_KEY=YOUR_KEY npm start
```

Server cần có internet để gọi Gemini. Sau khi deploy, mở APK → ⚙ Server → nhập `https://domain-cua-ban`.

## Build APK
Mở thư mục này bằng Android Studio, Sync Gradle, rồi Build > Build APK(s).

Hoặc dùng Gradle 8.7+:

```bash
gradle assembleDebug
```

APK debug: `app/build/outputs/apk/debug/app-debug.apk`

## GitHub Actions
Có workflow `.github/workflows/build-apk.yml`; push project lên GitHub rồi vào Actions để build APK tự động.
