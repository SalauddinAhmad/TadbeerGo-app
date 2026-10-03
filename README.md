# TadbeerGo Cross-Platform Apps (Mobile & Desktop)

এই প্রজেক্টটি [https://tadbeergo.vercel.app/](https://tadbeergo.vercel.app/) ওয়েবসাইটের জন্য স্বয়ংক্রিয়ভাবে **Android, iOS, Windows, Apple macOS এবং Linux** অ্যাপ তৈরি করার জন্য কনফিগার করা হয়েছে।

GitHub Actions এর মাধ্যমে প্রতিবার কোড পুশ করলে বা রিলিজ ট্যাগ দিলে ক্লাউডেই স্বয়ংক্রিয়ভাবে সকল প্ল্যাটফর্মের ইনস্টলেশন ফাইল তৈরি হয়ে যাবে।

---

## 🚀 সমর্থিত প্ল্যাটফর্মসমূহ ও আউটপুট ফাইল

| প্ল্যাটফর্ম | আউটপুট ফাইল | বিবরণ |
| :--- | :--- | :--- |
| 📱 **Android** | `TadbeerGo.apk` | সরাসরি অ্যান্ড্রয়েড ফোনে ইনস্টলযোগ্য APK |
| 🍎 **Apple iOS** | `TadbeerGo-iOS-unsigned.ipa` | AltStore, Sideloadly বা TrollStore দিয়ে ইনস্টলযোগ্য |
| 🪟 **Windows** | `TadbeerGo Setup.exe` / Portable | উইন্ডোজ ইনস্টলার এবং পোর্টেবল সংস্করণ |
| 🍏 **Apple macOS** | `TadbeerGo.dmg` / `.zip` | Mac (Apple Silicon & Intel) এর জন্য ডিস্ক ইমেজ |
| 🐧 **Linux** | `TadbeerGo.AppImage` / `.deb` | সকল লিনাক্স ডিস্ট্রিবিউশনের জন্য রেডি প্যাকেজ |

---

## 🛠️ GitHub-এ আপলোড এবং অ্যাপ তৈরির নিয়ম

### ধাপ ১: গিটহাব রিপোজিটরিতে কোড পুশ করুন

প্রজেক্ট ফোল্ডারে টার্মিনাল খুলে নিচের কমান্ডগুলো চালান:

```bash
# সব ফাইল গিট-এ যোগ করুন
git add .

# কমিট করুন
git commit -m "feat: TadbeerGo multi-platform apps with GitHub Actions"

# মেইন ব্রাঞ্চ সেট করুন
git branch -M main

# আপনার গিটহাব রিপোজিটরির রিমোট লিঙ্ক যোগ করুন (আপনার রিপোজিটরি লিংক দিন)
git remote add origin https://github.com/<আপনার-ইউজারনেম>/<আপনার-রিপো-নাম>.git

# পুশ করুন
git push -u origin main
```

---

### ধাপ ২: স্বয়ংক্রিয় বিল্ড শুরু হওয়া ও অ্যাপ ডাউনলোড

1. আপনার গিটহাব রিপোজিটরিতে যান।
2. উপরের মেনু থেকে **Actions** ট্যাবে ক্লিক করুন।
3. আপনি **"Build All Apps (Android, iOS, Desktop)"** নামের ওয়ার্কফ্লো দেখতে পাবেন যা নিজে থেকেই রান শুরু হয়ে যাবে।
4. বিল্ড শেষ হলে (সবগুলোতে সবুজ টিকচিহ্ন আসবে):
   - সেই রানটির ভেতরে ঢুকলে নিচে **Artifacts** সেকশনে পাবেন:
     - `TadbeerGo-Android-APK` (অ্যান্ড্রয়েড APK)
     - `TadbeerGo-iOS-IPA` (আইওএস IPA)
     - `TadbeerGo-Desktop-Windows (exe)`
     - `TadbeerGo-Desktop-macOS (dmg & zip)`
     - `TadbeerGo-Desktop-Linux (AppImage & deb)`
   - সেখানে ক্লিক করলেই সরাসরি ডাউনলোড হয়ে যাবে!

---

### ধাপ ৩: রিলিজ (Release) তৈরি করে সরাসরি ডাউনলোড লিংক তৈরি করা

আপনি যদি চান আপনার গিটহাবের **Releases** সেকশনে স্থায়ী ডাউনলোড লিংক তৈরি হোক:

1. **Actions** ট্যাবে গিয়ে **Build All Apps** সিলেক্ট করুন।
2. ডানপাশে **Run workflow** বাটনে ক্লিক করুন।
3. **"Publish a GitHub Release with all built apps?"** চেকবক্সে টিক দিয়ে **Run workflow** চাপুন।

অথবা একটি গিট ট্যাগ পুশ করুন:
```bash
git tag v1.0.0
git push origin v1.0.0
```
স্বয়ংক্রিয়ভাবে গিটহাব রিলিজে সব প্ল্যাটফর্মের অ্যাপ আপলোড হয়ে যাবে।

---

## 💻 লোকাল মেশিনে টেস্ট করার নিয়ম

### ডেস্কটপ অ্যাপ রান করতে:
```bash
npm start
```

### লোকালি ডেস্কটপ ইনস্টলার বিল্ড করতে:
```bash
# Mac এর জন্য:
npm run desktop:dist:mac

# Windows এর জন্য:
npm run desktop:dist:win

# Linux এর জন্য:
npm run desktop:dist:linux
```

### মোবাইল প্রজেক্ট সিঙ্ক করতে:
```bash
npm run cap:sync
```
