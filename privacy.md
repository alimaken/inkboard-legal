---
title: Inkboard privacy policy
permalink: /privacy/
---

# Inkboard privacy policy

**Effective date:** 16 October 2026
**App:** Inkboard (`com.alimaken.inkboard`) for Android, and the Inkboard web client it serves to browsers on your local network.
**Developer:** Ali Kamran Maken · **Contact:** [ali.maken.1987@gmail.com](mailto:ali.maken.1987@gmail.com)

## Summary

Inkboard does not collect, sell or share any personal data. It has no accounts, no ads, no analytics and no crash reporting of its own, and it never sends your boards or drawings to the developer or to any third party. Everything you create stays on your device unless you choose to share it with your own devices on your local Wi-Fi.

## Data the app handles

- **Your boards and drawings** are stored only on your device, in the app's private storage. The developer cannot access them. Uninstalling the app or clearing its data deletes them.
- **Share on Wi-Fi.** When you tap *Start sharing*, the app runs a small web server on your phone so that a browser on another device on the **same local network** (for example your laptop) can open your board. The server:
  - only answers devices with local network addresses, and refuses connections from the internet;
  - is not connected to any server of the developer or a third party: data travels directly between your phone and the browser on your network;
  - uses an unencrypted (HTTP) connection on your local network, as the app tells you before you share; only use it on networks you trust;
  - stops when you tap *Stop*, or after 15 minutes without any connected device.
- **No data is collected** in the sense of Google Play's *Data safety* section: no information leaves your device to the developer or to third parties.

## Permissions

| Permission | Why Inkboard needs it |
|---|---|
| Internet (`INTERNET`) | To run the local web server for *Share on Wi-Fi*. The app does not contact any internet service. |
| View network connections (`ACCESS_NETWORK_STATE`) | To find your phone's Wi-Fi address and show it to you, so you know what to open in the browser. |
| Foreground service, connected device (`FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_CONNECTED_DEVICE`) | To keep sharing running while the screen is off or you use another app. It runs only while you are sharing, with a visible notification. |
| Wi-Fi multicast (`CHANGE_WIFI_MULTICAST_STATE`) | Required by Android for the connected-device service type. A later version will also use it to let devices on your network find the phone by name. |
| Notifications (`POST_NOTIFICATIONS`) | To show the notification that sharing is active, with a *Stop* button. You can decline it; sharing still works and can be stopped in the app. |

Inkboard does not request access to your location, contacts, camera, microphone, photos or files.

## Third-party libraries

Inkboard is built with open-source libraries that run entirely on your device. **None of them collect or transmit data:**

- **Android Jetpack (AndroidX)** by Google: app framework, Compose user interface, lifecycle, navigation and startup libraries.
- **Compose Multiplatform** and **Kotlin** libraries by JetBrains: user interface, coroutines and serialization.
- **Ktor** by JetBrains: the local web server used by *Share on Wi-Fi*.
- **Koin**: dependency injection inside the app.

The app does not include Google Play services, Firebase, advertising or analytics SDKs.

## Google Play

If you install Inkboard from Google Play, Google may collect information under its own privacy policy, for example installs and, if you have allowed it in your device settings, crash and performance reports that Google shares with developers in anonymous, aggregated form. See [Google's privacy policy](https://policies.google.com/privacy).

## Children

Inkboard is not directed at children under 13 and does not knowingly collect any data from anyone, including children.

## Changes

If a future version changes how data is handled (for example an optional download of a handwriting-recognition model), this policy will be updated before that version is released, and the effective date above will change.

## Contact

Questions about this policy: [ali.maken.1987@gmail.com](mailto:ali.maken.1987@gmail.com)
