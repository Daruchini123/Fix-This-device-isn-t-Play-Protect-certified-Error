
# 📱 Google Play Certification (cmd) by Priyanshu

> **Purpose:**  
> This guide helps you attempt to resolve the **Play Protect certification error** on Android devices (especially those running custom ROMs).  
> ⚠️ *Note:* As of **June 2025**, this method does **not guarantee** full Play Store certification, but it can help with registration and basic functionality.

---

## 📸 What You Might See

<img src="https://github.com/user-attachments/assets/eeb81350-482d-4eb7-8b51-c6106b22a1c7" alt="Play Protect Error" width="300">

---

## 🛠️ Steps to Try

### 1. 🔍 Getting Your GSF Android ID

- Connect your device to your PC  
- Enable **USB debugging** and **Rooted debugging**

<img src="https://github.com/user-attachments/assets/aa7d1441-0e95-4dde-9556-057f49369dff" alt="USB Debugging" width="300">

- Open your **Terminal** (Linux/macOS) or **CMD** (Windows)

#### Linux:
```bash
adb root && adb shell 'sqlite3 /data/user/$(cmd activity get-current-user)/*/*/gservices.db "select * from main where name = \"android_id\";"'
````

#### Windows:

```cmd
adb root && adb shell "sqlite3 /data/user/$(cmd activity get-current-user)/*/*/gservices.db \"select * from main where name = 'android_id';\""
```

* Copy the number shown (Example: `4399677461041051781`)

---

### 2. ✅ Registering Your Device

* Visit: [https://www.google.com/android/uncertified](https://www.google.com/android/uncertified)
* Paste your **GSF Android ID**
* Click **Register**

---

### 3. ♻️ Resetting Play Store Services

Run this command to clear Play Store and Google Play Services data, then reboot:

```bash
adb shell pm clear com.android.vending && adb shell pm clear com.google.android.gms && adb reboot
```

---

## 💡 Final Notes

* This method is **unofficial** and may **not work** on all ROMs or devices.
* Google may revoke uncertified access at any time.
* For persistent issues, consider switching to **MicroG** or a **certified custom ROM** like LineageOS with official support.

---

## ✨ Happy Android Customizing!

```

Let me know if you'd like a downloadable `.md` file or if you'd like me to add badges, license, or repo description as well.
```
