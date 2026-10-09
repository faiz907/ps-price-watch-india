# PS Price Watch India

A dark, installable web app prototype for tracking PlayStation Store India game prices.

## What works
- Add/edit/remove PS4 and PS5 games.
- Store current price, user-entered historical low, and target price in INR.
- Record a local price history whenever you update a price.
- Flag target-price hits and show browser notifications when permission is granted and a price is updated while the app is open.
- Search wishlist and export/import JSON backups.
- Install as a PWA from a secure HTTPS host using your Android browser's **Add to Home screen / Install app** menu.

## Important limitations
This prototype does **not** fetch live prices automatically. The PlayStation Store does not offer a simple public price-history API for this use case, and scraping can break or be blocked. Historical lows are user-entered and are not independently verified. Local notifications only happen when you update a price in the app; true background alerts need a trusted price data provider plus a hosted backend/scheduled checker and push notifications.

## Run locally
Serve this directory over HTTP (service workers require localhost or HTTPS):
```bash
python3 -m http.server 8080
```
Then open `http://localhost:8080` on your computer. For installation on your phone, deploy the folder to any HTTPS static host and open that URL in Chrome on Android.

## Can this zip directly install as an APK?
No. It is a PWA source project, not a compiled APK. The current build environment has Java but no Android SDK/Gradle installation, so a native APK cannot be compiled and verified here. This project is designed as a working first version; it can later be wrapped in a native Android WebView/Capacitor project and built with Android SDK tooling.
