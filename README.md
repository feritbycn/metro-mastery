# Metro Mastery — Bus Puzzle

Modern, mobile-first bus/passenger sorting puzzle prototype. Gameplay is inspired by the uploaded game's visible bus-and-passenger matching structure, but all UI/code in this project is independently implemented.

## Current features
- Passenger queue grouped by color; choose the matching bus for the front passenger group.
- Three front parking positions; buses behind move forward as the front row clears.
- Level progression with Easy / Medium / Hard / Expert / Legendary difficulty labels.
- Bus capacity increases as levels advance; additional colors and locked parking spaces appear later.
- Undo, hint, extra-chance controls, coins, score, daily reward, garage, level map, and player profile.
- Responsive mobile UI with CSS-drawn buses, passengers, city skyline and road.
- Progress saved locally in the browser/WebView.
- Capacitor wrapper and GitHub Actions workflow to produce a debug APK and release AAB artifact.

## Run locally
Requires Node.js 20+.

```bash
npm install
npm run build
```

For a browser preview, serve the project directory with any static web server, or deploy it to GitHub Pages.

## Android builds via GitHub Actions
1. Create a GitHub repository and upload the contents of this ZIP to its root.
2. Open **Actions** and enable workflows if GitHub prompts you.
3. Run **Build Android APK and AAB** with **Run workflow**, or push a commit to `main`/`master`.
4. Open the completed run and download the `metro-mastery-android` artifact. It contains a debug APK for device testing and a release AAB build output.

The AAB build output is not a production-ready signed release. Configure a release keystore/signing secrets before publishing to Google Play. Use a unique application ID before publishing if `com.metromastery.game` is already in use.

## Ads and in-app purchases
The project includes demo screens and clearly marked integration points only. It does **not** show real ads or charge money yet.

Before release:
- Add Google Mobile Ads / AdMob SDK and your real app/ad-unit IDs. Grant rewards only from the SDK's earned-reward callback.
- Add Google Play Billing and product IDs for `remove_ads`, `metro_pro`, and any coin packs; verify purchases and acknowledge them correctly.
- Add privacy policy, consent flow (where required), app signing, target SDK review, and store assets.
- Test all level-generation edge cases on real Android devices.

## Important note about the reference
The provided `1.zip` is an Android package archive containing Unity asset bundles, not the original Unity source project. Therefore this repo recreates the bus/passenger matching gameplay concept; it does not patch the original Unity game's compiled code or copy its proprietary assets.
