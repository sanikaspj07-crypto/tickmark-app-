# Tickmark (Android)

Editable weekly timetable, daily targets, reminders that fire when the app is closed,
and live sharing with friends.

## Features
- Timetable tab: add, edit, delete slots per weekday, pick colour, set a reminder per slot, copy one day to all days.
- Today tab: tick off slots, add daily targets (optional reminder time), streak, weekly bars.
- Friends tab: swap friend codes, then see each other's targets, timetable and ticks live.

## 1. Firebase (only for friends)
1. console.firebase.google.com > Add project.
2. Build > Authentication > Sign-in method > enable **Anonymous**.
3. Build > Firestore Database > Create database.
4. Firestore > Rules > paste `firestore.rules` > Publish.
5. Project settings > Your apps > Web (</>) > copy the config into `www/config.js`.

## 2A. Get an APK without Android Studio (GitHub)
1. Install Git (git-scm.com) and make a free GitHub account.
2. Create an empty repository on GitHub (private is fine).
3. In this folder open a terminal and run:
```
git init
git add .
git commit -m "tickmark"
git branch -M main
git remote add origin https://github.com/YOURNAME/YOURREPO.git
git push -u origin main
```
4. On GitHub open the **Actions** tab, wait for "Build APK" to turn green (about 5 minutes).
5. Open that run, download **tickmark-apk** under Artifacts, unzip it, and send `app-debug.apk` to your phone.
6. Open the APK on the phone and allow install from unknown sources.

## 2B. Build with Android Studio
```
npm install
npx cap sync android
npx cap open android
```
Then press Run with your phone plugged in, or Build > Build APK(s).

## 3. On the phone
Timetable tab > Allow notifications > Allow exact alarms. On Xiaomi, Oppo, Vivo or Samsung
set Battery > Tickmark > Unrestricted, or alerts can be late.

## Notes
- Your identity is an anonymous Firebase login. Uninstalling gives a new friend code.
- Slot reminders repeat weekly until you change or delete the slot.
- If you edit `www/`, run `npx cap sync android` again (the GitHub build does this for you).
- Untested on a real device.
