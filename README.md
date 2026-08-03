<p align="center">
  <img src="logo.png" width="140" alt="Autolycus">
</p>

<h1 align="center">Autolycus</h1>

<p align="center"><em>Part of the Atavistic Concept apps</em></p>

A duress-unlock lock screen for Android. One lock screen - a PIN pad or a slide
pattern - with three secrets:

- **Real code** - unlocks the phone normally.
- **Duress 1** - shows a harmless-looking loading screen while it quietly turns on
  location (for Google Find My Device) and captures the surroundings from the front
  and back cameras to the gallery.
- **Duress 2** - shows a fake "System error" and factory-resets the device, so the
  wipe reads as a crash rather than a deliberate reset.

Everything runs on-device. There is no account, no server, and no network egress
except the location toggle the OS itself performs.

## Download

Grab the latest **[Autolycus.apk](../../releases/latest)** (or the `Autolycus.apk`
in this repo), enable "install unknown apps" for your browser/files app, and open it.

## Setup (once)

1. Open **Autolycus**, set your Real / Duress-1 / Duress-2 codes (PIN or pattern).
2. Grant camera + microphone, enable the accessibility service and (for the wipe)
   device admin, and set the phone's own screen lock to **Swipe** so Autolycus is the
   lock you see. Keep secure-startup / encryption on.
3. One permission needs a USB grant (silent location toggle):
   `adb shell pm grant com.algoz.guard android.permission.WRITE_SECURE_SETTINGS`

## Notes

- Android 12+ shows a green camera/mic dot while capturing; that is an OS privacy
  indicator and cannot be hidden by an app.
- The duress-2 wipe is irreversible. Make sure you know which code is which.

Source: private repo `atavistic-concept/autolycus-app-files`.
