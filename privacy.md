---
title: Inkboard privacy policy
permalink: /privacy/
---

# Inkboard privacy policy

**Effective date:** 19 October 2026
**App:** Inkboard (`com.alimaken.inkboard`) for Android, and the Inkboard web client it serves to browsers on your local network.
**Developer:** Ali Kamran Maken · **Contact:** [ali.maken.1987@gmail.com](mailto:ali.maken.1987@gmail.com)

## Summary

Inkboard does not collect, sell or share any personal data. It has no accounts, no ads, no analytics and no crash reporting of its own, and it never sends your boards or drawings to the developer or to any third party. Everything you create stays on your device unless you choose to share it with your own devices on your local Wi-Fi, or to save or send a file to a place or app you pick. The only time the app contacts an internet service is when you agree to download Google's handwriting-recognition model, as described below.

## Data the app handles

- **Your boards and drawings** are stored only on your device, in the app's private storage. The developer cannot access them. Uninstalling the app or clearing its data deletes them.
- **Share on Wi-Fi.** When you tap *Start sharing*, the app runs a small web server on your phone so that a browser on another device on the **same local network** (for example your laptop) can open your board. The server:
  - only answers devices with local network addresses, and refuses connections from the internet;
  - is not connected to any server of the developer or a third party: data travels directly between your phone and the browser on your network;
  - uses an unencrypted (HTTP) connection on your local network, as the app tells you before you share; only use it on networks you trust;
  - stops when you tap *Stop*, or after 15 minutes without any connected device.
- **Export and files.** You can save a board as a `.inkboard` file or as a PNG image, and save extracted text as `.txt` or `.md`. The file goes only where you choose, through Android's file picker or share sheet, and Inkboard never uploads it. A `.inkboard` file opened from another app is read only to import it as a new board. Inkboard needs no file or storage permission for any of this.
- **Handwriting recognition.** Turning handwriting into text, and searching your handwriting, use Google's **ML Kit** library, which recognises handwriting on your device. It first needs Google's English handwriting model, about 11 MB:
  - the model is downloaded from Google's servers (`dl.google.com`) only after you agree to it, the first time you convert ink or turn on handwriting search;
  - like any download, the request lets Google see your device's IP address, under [Google's privacy policy](https://policies.google.com/privacy); it carries none of your boards, ink or text;
  - after the download, handwriting is recognised entirely on your device, even without a connection, and your ink and the text read from it never leave it;
  - ML Kit would normally send usage statistics to Google (device and app information, an identifier for the installation, performance figures and the languages used). Inkboard switches this off, and we have checked with a capture of the device's network traffic that nothing is sent;
  - *Search handwriting* is off unless you turn it on in Settings. What it reads is kept with your boards on your device, and turning it off deletes it;
  - you can delete the model at any time in *Settings → Handwriting*.
- **No data is collected** in the sense of Google Play's *Data safety* section: no information about you or your boards leaves your device for the developer or any third party. The handwriting model's download, which you agree to, is the only request the app makes to an internet service.

## Permissions

| Permission | Why Inkboard needs it |
|---|---|
| Internet (`INTERNET`) | To run the local web server for *Share on Wi-Fi*, and to download the handwriting model when you agree to it. The app contacts no other internet service. |
| View network connections (`ACCESS_NETWORK_STATE`) | To find your phone's Wi-Fi address and show it to you, so you know what to open in the browser. |
| Foreground service, connected device (`FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_CONNECTED_DEVICE`) | To keep sharing running while the screen is off or you use another app. It runs only while you are sharing, with a visible notification. |
| Wi-Fi multicast (`CHANGE_WIFI_MULTICAST_STATE`) | Required by Android for the connected-device service type. A later version will also use it to let devices on your network find the phone by name. |
| Keep the device awake (`WAKE_LOCK`) and run at startup (`RECEIVE_BOOT_COMPLETED`) | Added by Android's WorkManager library, which ML Kit includes to run background work such as the handwriting model's download; WorkManager uses them to finish that work, and to keep it scheduled when the phone restarts. Inkboard itself uses neither. |
| Notifications (`POST_NOTIFICATIONS`) | To show the notification that sharing is active, with a *Stop* button. You can decline it; sharing still works and can be stopped in the app. |

Inkboard does not request access to your location, contacts, camera, microphone, photos or files.

## Third-party libraries

Inkboard is built with these libraries. Except for ML Kit's model download described above, **none of them transmit data:**

- **Android Jetpack (AndroidX)** by Google: app framework, Compose user interface, lifecycle, navigation and startup libraries.
- **Compose Multiplatform** and **Kotlin** libraries by JetBrains: user interface, coroutines and serialization.
- **Ktor** by JetBrains: the local web server used by *Share on Wi-Fi*.
- **Koin**: dependency injection inside the app.
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
