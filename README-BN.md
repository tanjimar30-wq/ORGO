# ORGO CUNNECT — Android Studio Project

এটি `https://cangroup.gt.tc/` PHP Backend-এর জন্য একটি Android WebView Native Wrapper Project।

## APK Build করার নিয়ম

1. PC-তে Android Studio (JDK 17 সহ) ইনস্টল করুন।
2. Android Studio দিয়ে এই ফোল্ডার Open করুন।
3. Gradle Sync সম্পন্ন হতে দিন।
4. **Build > Build Bundle(s) / APK(s) > Build APK(s)** নির্বাচন করুন।
5. Debug APK পাবেন `app/build/outputs/apk/debug/app-debug.apk` এ।

## অন্তর্ভুক্ত
- App ID: `com.orgobd.cunnect`
- HTTPS-only backend
- Android microphone/camera permission callback for browser WebRTC
- File chooser support for image/video upload
- Session cookies and DOM storage
- Back navigation and dark system bars

## সীমাবদ্ধতা ও প্রয়োজনীয় পরীক্ষা
- এটি Android Studio project; এই ডেলিভারিতে compiled APK নেই।
- এই build environment-এ Android SDK, Gradle, adb নেই; তাই APK compile করা সম্ভব হয়নি।
- PHP source-এ WebRTC browser signaling আছে, তাই foreground call UI কাজ করতে পারে; বাস্তব ডিভাইসে যাচাই আবশ্যক।
- PHP-এর VAPID Web Push নিজে থেকে Firebase Cloud Messaging নয়। App বন্ধ/force-stop থাকলে নির্ভরযোগ্য incoming call notification পেতে আলাদা FCM backend + Android native notification/foreground call service তৈরি করতে হবে।
- `targetSdk 35` অনুযায়ী Android permission ও background execution আচরণ Android Studio/device-এ পরীক্ষা করুন।
- Admin default PIN 1234 source-এ আছে—public deployment-এর আগে বদলান।
- Server-side PHP/SQLite database এই অ্যাপে কপি করা হয়নি; আগের hosting-এই থাকবে।
