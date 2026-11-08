CARE LIFE DASHBOARD - ANDROID WEBVIEW SOURCE

ওয়েবসাইট: https://yttrium.serv00.net/test/
Package: net.carelife.dashboard

ফিচার:
- WebView dashboard
- Android Back navigation
- Login cookies/session
- Native Android Print Preview (window.print() bridge)
- HTTP/HTTPS file download via Android DownloadManager
- File chooser/upload support
- Splash screen
- Blob save bridge (website-side JS integration প্রয়োজন)

গুরুত্বপূর্ণ:
1) এই ZIP-এ APK binary নেই; এটি source project।
2) APK build করতে Android Studio/Gradle build environment প্রয়োজন।
3) Android ফোন থেকে build করতে হলে compatible IDE বা GitHub Actions ব্যবহার করতে হবে।
4) window.print() override করা হয়েছে। ওয়েবসাইটের normal window.print() কল Android Print Preview খুলবে।
5) Blob/JavaScript-generated PDF/CSV download-এর জন্য website code-এ CareLife.saveBlob(base64, filename, mime) কল যোগ করতে হবে; সব Blob auto-capture করা হয়নি।
6) DownloadManager-এর সাধারণ HTTP(S) downloads-এ login cookie পাঠানো হয়। Signed/POST-only endpoints আলাদা integration চাইতে পারে।
7) App logo placeholder text 'CL'; res/drawable বা mipmap icon যোগ করে launcher icon বদলাতে হবে।
8) Release APK distribute করার আগে signing key নিরাপদে backup রাখবেন।

Build:
- Android Gradle Plugin 8.4.2
- Compile SDK 35
- Minimum SDK 23
- Java 8

Android Studio:
Open folder > wait for Gradle sync > Build > Build APK(s).
