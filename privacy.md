---
title: Inkboard privacy policy
permalink: /privacy/
---

# Inkboard privacy policy

**Effective date:** 21 October 2026
**App:** Inkboard (`com.alimaken.inkboard`) for Android, and the Inkboard web client it serves to browsers on your local network.
**Developer:** Ali Kamran Maken · **Contact:** [ali.maken.1987@gmail.com](mailto:ali.maken.1987@gmail.com)

## Summary

Inkboard does not collect, sell or share any personal data. It has no accounts, no ads, no analytics and no crash reporting of its own, and it never sends your boards or drawings to the developer or to any third party. Everything you create stays on your device unless you choose to share it with your own devices on your local Wi-Fi, or to save or send a file to a place or app you pick. The app contacts an internet service only when you start something yourself: you buy the Premium unlock (Google Play), you turn on Drive backups (Google Drive), or you agree to download Google's handwriting-recognition model. Each is described below.

## Data the app handles

- **Your boards and drawings** are stored only on your device, in the app's private storage. The developer cannot access them. Uninstalling the app or clearing its data deletes them.
- **Share on Wi-Fi.** When you tap *Start sharing*, the app runs a small web server on your phone so that a browser on another device on the **same local network** (for example your laptop) can open your board. The server:
  - only answers devices with local network addresses, and refuses connections from the internet;
  - makes every browser enter a 4-digit PIN, new for each sharing session and shown only on your phone, and then asks you to **Allow** that browser on the phone. You can make a browser *View only*, or remove it, at any time. The PIN and the browser's session token are kept in memory only and end when sharing stops;
  - is not connected to any server of the developer or a third party: data travels directly between your phone and the browser on your network;
  - uses an unencrypted (HTTP) connection on your local network, as the app tells you before you share; only use it on networks you trust;
  - stops when you tap *Stop*, or after the idle time you chose (15 minutes by default) without any connected device;
  - **announces itself on your local network** so that `inkboard.local` opens it: the phone answers multicast DNS (mDNS) questions for that one name, and registers a service with Android's network service discovery. Both stay on the local network and carry the phone's local address, not your boards. A browser that connects is shown the board you share, and that browser's name and cursor position are shown to the other browsers;
  - is a **Premium** feature.
- **Purchases (Premium).** Premium is a one-time purchase handled entirely by **Google Play**: Google takes the payment and keeps the purchase records under [Google's privacy policy](https://policies.google.com/privacy). Inkboard asks the Play app on your phone what you have bought and checks the signed answer on your device with the app's public licence key. It has no server and never receives your payment details, name or email address. A copy of "Premium is unlocked" is kept on your device so the app works offline, and is checked again whenever the phone is online.
- **Drive backups (Premium, optional, off by default).** If you turn them on, you sign in with a Google account that you pick, and allow Inkboard to create and read **only the files it creates itself** in your Google Drive (Google's `drive.file` permission; it cannot see your other files).
  - A backup is a `.inkboard` file with all your boards except the trash. It is sent from your phone directly to your Google Drive, into a folder named *Inkboard backups*, over an encrypted connection. It does not pass through the developer or any other server.
  - The backups belong to you and live in your Drive, under [Google's privacy policy](https://policies.google.com/privacy). Inkboard keeps only the newest 3, 5 or 10 (your choice). To delete them, delete the folder in Drive.
  - The account's email address is kept on your device to show you which account is used. It is not sent to the developer.
  - Backups run on the schedule you choose (daily or weekly, on Wi-Fi and while charging) or when you tap *Back up now*. *Sign out* in Settings stops them, revokes Inkboard's access to your Drive and removes the account from the app. You can also revoke access in your [Google Account](https://myaccount.google.com/permissions).
- **Export and files.** You can save a board as a `.inkboard` file or as a PNG image, and save extracted text as `.txt` or `.md`. The file goes only where you choose, through Android's file picker or share sheet, and Inkboard never uploads it. A `.inkboard` file opened from another app is read only to import it as a new board. Inkboard needs no file or storage permission for any of this.
- **Handwriting recognition.** Turning handwriting into text, and searching your handwriting, use Google's **ML Kit** library, which recognises handwriting on your device. It first needs Google's English handwriting model, about 11 MB:
  - the model is downloaded from Google's servers (`dl.google.com`) only after you agree to it, the first time you convert ink or turn on handwriting search;
  - like any download, the request lets Google see your device's IP address, under [Google's privacy policy](https://policies.google.com/privacy); it carries none of your boards, ink or text;
  - after the download, handwriting is recognised entirely on your device, even without a connection, and your ink and the text read from it never leave it;
  - ML Kit would normally send usage statistics to Google (device and app information, an identifier for the installation, performance figures and the languages used). Inkboard switches this off, and we have checked with a capture of the device's network traffic that nothing is sent;
  - *Search handwriting* is off unless you turn it on in Settings. What it reads is kept with your boards on your device, and turning it off deletes it;
  - you can delete the model at any time in *Settings → Handwriting*.
- **No data is collected** in the sense of Google Play's *Data safety* section: no information about you or your boards leaves your device for the developer or any third party. The developer receives nothing. The requests the app makes are the ones you start: the Play purchase check, Drive backups to your own Drive, and the handwriting model's download.

## Permissions

| Permission | Why Inkboard needs it |
|---|---|
| Internet (`INTERNET`) | To run the local web server for *Share on Wi-Fi*, to talk to Google Play for purchases, to send backups to your Google Drive when you turn them on, and to download the handwriting model when you agree to it. The app contacts no other internet service. |
| View network connections (`ACCESS_NETWORK_STATE`) | To find your phone's Wi-Fi address and show it to you, so you know what to open in the browser. |
| Foreground service, connected device (`FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_CONNECTED_DEVICE`) | To keep sharing running while the screen is off or you use another app. It runs only while you are sharing, with a visible notification. |
| Wi-Fi multicast (`CHANGE_WIFI_MULTICAST_STATE`) | Required by Android for the connected-device service type, and used to answer `inkboard.local` on your network while sharing. |
| Nearby devices on the local network (`ACCESS_LOCAL_NETWORK`) | Android 17 and later require it to accept connections from other devices on your network. Inkboard asks for it before sharing starts; without it, sharing can't work. |
| Purchases (`com.android.vending.BILLING`) | Added by Google Play Billing, to offer and check the Premium purchase. |
| Biometrics (`USE_BIOMETRIC`, `USE_FINGERPRINT`) | Added by an Android library that Google's sign-in components include. Inkboard never asks for your fingerprint or face. |
| Keep the device awake (`WAKE_LOCK`) and run at startup (`RECEIVE_BOOT_COMPLETED`) | Added by Android's WorkManager library, which Inkboard and ML Kit use for background work: the handwriting model's download and, if you turn them on, scheduled Drive backups. WorkManager uses them to finish that work, and to keep your backup schedule after the phone restarts. Inkboard does nothing else at startup. |
| Notifications (`POST_NOTIFICATIONS`) | To show the notification that sharing is active, with a *Stop* button. You can decline it; sharing still works and can be stopped in the app. |

Inkboard does not request access to your location, contacts, camera, microphone, photos or files.

## Third-party libraries

Inkboard is built with these libraries. Except for what is described above (the model download, Play purchases and Drive backups, each started by you), **none of them transmit data:**

- **Android Jetpack (AndroidX)** by Google: app framework, Compose user interface, lifecycle, navigation and startup libraries.
- **Compose Multiplatform** and **Kotlin** libraries by JetBrains: user interface, coroutines and serialization.
- **Ktor** by JetBrains: the local web server used by *Share on Wi-Fi*.
- **Koin**: dependency injection inside the app.
- **Google Play Billing**: the Premium purchase, through the Play app on your phone.
- **Android Credential Manager and Google Identity (Authorization API)**: choosing the Google account and granting Drive access, only if you turn on Drive backups.
- **ML Kit Digital Ink Recognition** by Google: handwriting recognition on the device. It includes some Google Play services and Firebase client libraries that it is built on; Inkboard uses no Google Play services or Firebase service through them.

The app does not include advertising or analytics SDKs, and ML Kit's own usage statistics are switched off.

## Google Play

If you install Inkboard from Google Play, Google may collect information under its own privacy policy, for example installs and, if you have allowed it in your device settings, crash and performance reports that Google shares with developers in anonymous, aggregated form. See [Google's privacy policy](https://policies.google.com/privacy).

## Children

Inkboard is not directed at children under 13 and does not knowingly collect any data from anyone, including children.

## Changes

If a future version changes how data is handled, this policy will be updated before that version is released, and the effective date above will change.

## Contact

Questions about this policy: [ali.maken.1987@gmail.com](mailto:ali.maken.1987@gmail.com)
