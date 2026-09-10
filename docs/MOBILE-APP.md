# Mobile packaging

The game is prepared for a Capacitor wrapper. The native project has not been compiled or signed here.

## Prepare

Install Node 22+. For iOS, use macOS and Xcode 26+; for Android use a compatible Android Studio installation. See [Capacitor environment setup](https://capacitorjs.com/docs/getting-started/environment-setup).

From the project root:

```sh
npm run build
npm run native:prepare
cd native
npm install
```

Change `appId` in `capacitor.config.json` from `com.example.brinkmanship` to your own unique bundle identifier. Keep the resulting package lockfile in your repository.

## iOS

```sh
npx cap add ios
npx cap sync ios
npx cap open ios
```

In Xcode select your development team, add production icons/launch assets, test on actual iPhone/iPad devices, and archive a signed release. Use TestFlight before submission. Capacitor apps follow Apple's normal native submission process: [Capacitor deployment](https://capacitorjs.com/docs/ios/deploying-to-app-store).

## Android

```sh
npx cap add android
npx cap sync android
npx cap open android
```

Set the release signing configuration and build an app bundle using Android Studio.

## Before store submission

Test long campaigns, restore/import/export, memory pressure, interrupted app sessions, notches, landscape/portrait, large text and screen readers. Browser download links may require a native file/share integration in WKWebView; the original JSON export is not claimed to be a verified native sharing flow. Remove or adapt web-only source-download and edition links for your release if needed. No native plugins for cloud storage, file sharing, purchases, notifications, or tracking are enabled.

Prepare accurate age-rating answers for simulated warfare, privacy disclosures matching the shipped app, a support URL, screenshots, and any required rights information. Store acceptance is determined by [Apple's review guidelines](https://developer.apple.com/app-store/review/guidelines/).

The included web manifest and service worker cache the shell and previously visited artwork on a supported hosted origin. They are not a substitute for native packaging. Countries whose artwork has not been viewed online may lack artwork when offline. The native bundle includes all local artwork.
