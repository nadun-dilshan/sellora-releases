# Sellora Android app

The Sellora app for shop owners and staff. Manage orders, reply to WhatsApp
chats, check stock and get push notifications from your phone. It works with
the same account you use on the Sellora web dashboard.

## Download

**[Download the latest Android app (APK)](https://github.com/nadun-dilshan/sellora-releases/releases/latest/download/sellora-android.apk)**

This link always points to the newest build. Older builds are listed under
[Releases](https://github.com/nadun-dilshan/sellora-releases/releases).

The app is not on Google Play. It is shared directly by Sellora from this page.

## Install on Android

1. Open the download link above on your Android phone.
2. When asked, allow your browser to install apps ("Install unknown apps").
3. Open the downloaded file and tap **Install**.
4. Play Protect may show a warning the first time because the app did not come
   from Google Play. Choose **Install anyway**. The app is published only here,
   by Sellora.
5. Open Sellora and sign in with your tenant admin or staff account.

Requirements: Android 8.0 or newer and an internet connection.

## Install කරන හැටි (සිංහල)

1. උඩ තියෙන download link එක Android phone එකෙන් open කරන්න.
2. ඇහුවොත් browser එකට app install කරන්න ඉඩ දෙන්න ("Install unknown apps").
3. Download වුණ file එක open කරලා **Install** tap කරන්න.
4. App එක Google Play එකෙන් නෙවෙයි Sellora එකෙන් කෙලින්ම දෙන නිසා පළවෙනි
   වතාවේ Play Protect warning එකක් පෙන්නන්න පුළුවන්. **Install anyway** තෝරන්න.
5. Sellora app එක open කරලා ඔයාගේ tenant admin හෝ staff account එකෙන් sign in
   වෙන්න.

## Updates

You rarely need to download the app again. Most improvements install
themselves the next time you open the app.

A new download is only needed when a release note says so, or when the app
tells you a newer version is required. In that case install the new APK over
the existing one. Your sign-in and settings are kept.

## Push notifications

The app notifies you about new orders, cancellations, low stock, customers
asking for a person, and billing reminders. If notifications do not arrive,
open **More → Notifications** in the app and check that notifications are
allowed for Sellora in your phone's settings.

## Need help?

Use the Help & manual page in the Sellora web dashboard, or contact Sellora
support at support@botcalm.com.

---

## For maintainers

Releases here are created automatically by the Mobile CI workflow in the main
Sellora repository. Every merge to `main` that touches the mobile app builds a
sideloadable APK on Expo (EAS, profile `production-apk`) and publishes it as a
release in this repository, marked as the latest.

- Tag format: `android-v<app version>-b<workflow run number>`, for example
  `android-v1.0.1-b42`.
- Asset name: `sellora-android.apk`. The "latest" download link above depends
  on that exact name.
- Release notes carry the source commit the build came from.
- JavaScript-only changes ship to installed apps over the air through EAS
  Update and do not create a release here. Native changes (new packages,
  `app.json` native settings, Expo SDK upgrades) require a version bump in
  `apps/mobile/app.json` and produce a new release.

To publish manually, download the APK from expo.dev → Builds and run:

```bash
gh release create android-v<version>-b<n> sellora-android.apk \
  --repo nadun-dilshan/sellora-releases \
  --title "Sellora Android v<version> (build <n>)" \
  --notes "Built from <commit>." \
  --latest
```

The workflow needs the repository variable `RELEASES_REPO` set to
`nadun-dilshan/sellora-releases` and the secret `RELEASES_TOKEN` with
**Contents: read and write** on this repository. Keep this repository public,
otherwise the download link will not work without a GitHub account.
