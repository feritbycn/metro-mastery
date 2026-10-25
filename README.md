# Metro Mastery 🚍

Modern, Turkish-language bus-and-passenger color-matching puzzle game. Original UI and implementation; inspired by the broad bus-jam puzzle genre, not a copy of the uploaded APK's assets or source.

## What's included
- Responsive mobile-first web game; playable in browser and GitHub Pages.
- Progressive levels: easy, medium, hard, expert, legendary difficulty labels.
- Bus/passenger color matching, increasing passenger capacity, locked buses, undo, hints, reset, daily reward, coin shop and Pro/remove-ads demo screens.
- Capacitor Android wrapper and GitHub Actions workflow to build a debug APK and release AAB.
- Monetization integration points are deliberately safe demo placeholders. No real ads or charges are made by this starter.

## Run locally
Requires Node.js 20+.
```bash
npm install
npm run build
npx cap add android
npx cap sync android
npx cap open android
```
For browser preview, serve the project root with any static web server, or deploy the repository root to GitHub Pages.

## Build APK/AAB on GitHub
1. Create a new GitHub repository and upload the contents of this ZIP (the files inside `metro-mastery/`, not the outer folder if you prefer root deployment).
2. Push to `main` or `master`, or go to **Actions → Build Android APK and AAB → Run workflow**.
3. Open the completed workflow run and download the `metro-mastery-android` artifact.
4. The artifact contains a debug APK for testing and a release AAB bundle. The AAB produced here is **unsigned/unconfigured for Play release** until you set up signing in Gradle/CI. For Google Play, configure a protected upload keystore and signing secrets; never commit the keystore or passwords.
5. GitHub Pages: **Settings → Pages → Deploy from a branch**, select `main` and `/ (root)`.

## Real ads and purchases — required before publishing
- **AdMob:** add the official Google Mobile Ads SDK to the native Android project and configure the app ID + rewarded/interstitial ad unit IDs. Use test ad IDs while developing. Only award coins after the SDK's earned-reward callback; never reward on button click alone.
- **Google Play Billing:** use Play Billing for consumables (coins), one-time products (remove ads / Pro unlock), acknowledge and verify purchases, and restore entitlements. Create product IDs in Play Console and map them to the shop. Current shop interactions are clearly labeled demo-only and do not charge money.
- Add a privacy policy, consent flow where required, data safety declaration, age/target-audience settings and appropriate ad personalization controls.
- Before release, configure signing, app icon, screenshots, content rating, and test on real Android devices.

## Game mechanics
Tap a bus to board the next waiting passenger of the matching color. Each bus has limited seats; a bus leaves when full. The challenge grows with more colors/passengers and occasional locked buses. Undo lets the player recover from a mistake. Hint costs 40 coins.

## Known starter limitations
This is a polished playable prototype, not a finished commercial game. Difficulty is currently a simple progression; there is no server save, audio engine, analytics, live ad SDK, or real billing yet. Purchases and ads are demo-only. Review gameplay balance and accessibility before release.
