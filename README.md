# VacationTracker (Android)

**VacationTracker** is an Android app for planning trips and the excursions that happen during those trips. Create vacations, add date-bound excursions, enable optional reminders, search itineraries, and export a consolidated CSV report—everything stored locally on the device.

**Submission links**
- `GitHub Pages`: https://tegetzer01.github.io/vacationtracker/
- `Direct APK download (signed)`: https://github.com/tegetzer01/vacationtracker/releases/download/v6.0/app-release.apk

**Quick links**
- `Project homepage`: https://tegetzer01.github.io/vacationtracker/
- `Latest release`: https://github.com/tegetzer01/vacationtracker/releases/tag/v6.0
- `Source code`: https://github.com/tegetzer01/vacationtracker

**What the app does**
- Plan vacations with title, hotel, start/end dates (validated).
- Manage excursions tied to a vacation; excursion dates must fall within the vacation window.
- Optional reminders for vacation start/end and excursion dates (AlarmManager + notification channel).
- Search vacations by title or hotel (reactive after two characters).
- Report & export a consolidated view of vacations and excursions to CSV via Android’s share sheet.
- Local-first & private: data is on-device via Room; session state uses EncryptedSharedPreferences.

**System requirements**
- `Device`: Android phone or tablet
- `OS`: Android 8.0 (API 26) or newer
- `Storage/Network`: A few MB local storage; no network required for core features

**Install the APK**
1. Download the signed APK:
   https://github.com/tegetzer01/vacationtracker/releases/download/v6.0/app-release.apk
2. On your Android device, open the file from Downloads (or transfer via USB/Drive).
3. When prompted, allow installs from this source (one-time setting).
4. Follow on-screen prompts to complete installation.
5. Open VacationTracker from your app drawer.
   *On Android 13+, the app will request Notifications permission the first time you enable reminders.*

**Privacy & data**
- All data is stored locally in a Room database (no cloud sync).
- Passwords are salted and hashed; plaintext credentials are never stored.
- CSV exports are shared via FileProvider.
- Cleartext network traffic is disabled by default.

**Tech stack**
- `Language/Build`: Java (Android), Gradle (Kotlin DSL)
- `UI`: Material, AppCompat, RecyclerView, ConstraintLayout
- `Architecture`: MVVM (Activities + ViewModel + LiveData)
- `Persistence`: Room (with migrations)
- `Security`: Android Security Crypto (EncryptedSharedPreferences)
- `System`: AlarmManager + Notification Channel, FileProvider
- `Testing`: JUnit; Robolectric available for JVM tests

**Repo structure**
- app/ — Android app module (source, resources)
- docs/ — Static site for GitHub Pages (index.html with Download button)

**Maintaining the public download page**
- The GitHub Pages site lives in docs/index.html. When you publish a new release:
- Create a GitHub Release such as v7.0 or v6.1 and upload the signed APK as an Asset.
- Right-click → Copy link address on the APK under Assets. The URL will look like: https://github.com/tegetzer01/vacationtracker/releases/download/v7.0/apk-release.apk
- Update the Download button in docs/index.html to that “/releases/download/…” link.
- Commit to main. GitHub Pages updates automatically.

**Troubleshooting**
- Download button 404: Release may still be processing—refresh, or open the Release page and click the APK under Assets.
- Install blocked: Enable Allow from this source for the Files/Browser app during install.
- No reminders: On Android 13+, ensure Notifications are allowed for VacationTracker in system settings.

**License / usage**
- This repository and APK are provided for academic evaluation and demonstration purposes. All rights reserved unless a license file is provided.
