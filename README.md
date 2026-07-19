# Dataflow ULOD

**Automatic data refills for Lidl Connect Unlimited (ULOD).**
The app books your next gigabyte *before* you get throttled — no more typing
"Refill" into an SMS every time the data runs out.

> **Deutsch:** Dataflow ULOD bucht dein Lidl Connect Unlimited-Datenvolumen
> automatisch nach — auf Wunsch schon *bevor* gedrosselt wird, ohne auf die
> Status-SMS zu warten. Einmal einrichten, nie wieder dran denken.
> Mehr auf der [Website](https://dataflow-ulod-auto-refill.lovable.app).

---

## Download

**[⬇ Download the latest APK](https://github.com/Bashar101Kh/dataflow-ulod-releases/releases/latest/download/dataflow-ulod.apk)**

This link always points at the newest release. All versions and their release
notes are on the [Releases page](https://github.com/Bashar101Kh/dataflow-ulod-releases/releases).

### Install

1. Download the APK on your phone.
2. Open it — Android will ask you to allow installs from your browser
   ("Install unknown apps"). Allow it once.
3. Open Dataflow ULOD and follow the guided setup: sign in, grant SMS and
   notification permissions, set **Premium SMS access** for short codes to
   *Always allow*, and exclude the app from battery optimization.

Updating later is easier: the app checks this repo and shows an update banner —
installing a new APK over the old one keeps all your data.

## What it does

Lidl Connect Unlimited ("ULOD") gives you 1 GB of full-speed data at a time;
when it's used up you're throttled until you text `Refill` to `80808`.
Dataflow ULOD automates that — with three trigger modes:

- **SMS** — reacts to Lidl's status SMS the moment it arrives.
- **DATA** — the app counts your own mobile data and books the next gigabyte
  *just before* the ~1 GB cliff, so the throttled moment never happens
  (Lidl's SMS is often minutes late — this doesn't wait for it).
- **BOTH** *(default)* — the data counter leads, the SMS stays on as backstop.

Plus: a live usage gauge, one-tap instant refill, a full activity log, and
statistics (data booked, refill history, busiest times of day).

## Requirements

- Android 7.0 or newer
- A **Lidl Connect Unlimited** tariff (the 1 GB refill option) on an active SIM
- The app is free during the public beta

## Permissions, and why

| Permission | Why the app needs it |
|---|---|
| Receive / read SMS | To see Lidl's status SMS ("your 1 GB is used up") and confirmations |
| Send SMS | To send the `Refill` text to 80808 for you — this is the whole point |
| Notifications | Refill confirmations, failure alerts, and the monitoring status |
| Run in background | The data counter runs as a foreground service so refills happen even with the app closed |

Everything SMS-related stays **on your phone**. Message contents are never
uploaded; only your account sign-in and plan status talk to our backend.

## Why isn't this on the Play Store?

Google Play doesn't allow apps that automatically send SMS to short codes,
regardless of intent. Direct APK distribution from this repository is the
official and only channel — if you found this APK anywhere else, don't
install it.

### Verifying your download (optional but smart)

Every release's notes include the APK's SHA-256 checksum. Compare with:

```
certutil -hashfile dataflow-ulod.apk SHA256   # Windows
sha256sum dataflow-ulod.apk                   # Linux/Mac
```

## Support

Found a bug or have a question? [Open an issue](https://github.com/Bashar101Kh/dataflow-ulod-releases/issues)
or use **Settings → About → Share diagnostics** in the app to attach a report
(it's generated on-device; nothing is uploaded automatically).

---

*Dataflow ULOD is an independent project and is not affiliated with, endorsed
by, or connected to Lidl, Lidl Connect, or Schwarz Gruppe. "Lidl Connect" is a
trademark of its respective owner.*
