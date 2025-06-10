## 📱 Google Play Certification (Termux) Credit Tim Parker (TG)

---

### ⚠️ Disclaimer

This script involves root access. **Only proceed if your device is rooted.** Any misuse is your responsibility.

---

### 🚀 Steps
https://github.com/Daruchini123/system-tweaks/blob/main/Screenshot%202025-05-24%20163000.png

#### 1. Installing SQLite in Termux

```bash
pkg install sqlite
```

#### 2. Getting Your Android ID

```bash
su -c "sqlite3 /data/data/com.google.android.gms/databases/gservices.db \"SELECT value FROM main WHERE name = 'android_id';\""
```

> 📋 Copy the result. This is your `android_id`.

---

#### 3. Registering on Google

* Go to: [https://www.google.com/android/uncertified](https://www.google.com/android/uncertified)
* Sign in with your Google account.
* Paste your `android_id` and register.

---

#### 4. Clearing Google Play & Play Services Cache

```bash
su -c "pm clear com.android.vending && pm clear com.google.android.gms && reboot"
```

---

### ✅ You're Done

Once your device reboots, give Google a few minutes to process the certification. You can verify Play certification in:

> Google Play Store → Settings → Play Protect certification

---

### 💡 Tip

If you still see "Device is not certified," try re-adding your Google account after a few hours.
