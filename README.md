# FitTrack — personal iPhone PWA

A static, light-theme, offline-first fitness tracker. No build tools, npm, account, server database or API keys needed.

## Windows: test locally
1. Extract FitTrack.zip.
2. Open a terminal in the FitTrack folder (the folder containing index.html).
3. With Python 3 installed, run `python -m http.server 8000` (or `py -m http.server 8000`).
4. Visit http://localhost:8000 in Edge or Chrome. Do not open index.html by double-clicking: service workers require localhost or HTTPS.

## Install on iPhone
1. Deploy the contents of this folder to any static HTTPS host. For example, create a GitHub repository, upload the files at the repository root, then enable GitHub Pages from Settings > Pages, Deploy from a branch, main / (root). Use the HTTPS address Pages provides. Public hosting exposes the source files, not your locally logged data. Do not upload backup files or photos to the repository.
2. Open the HTTPS URL in Safari on your iPhone. Wait for the first page load while online.
3. Tap Share > Add to Home Screen (on newer iOS versions enable Open as Web App if shown) > Add.
4. Launch FitTrack from your home screen. Test logging a workout and opening it in airplane mode after the first successful online load.

A plain HTTP address on your Windows PC's LAN is not enough for offline PWA support. Use HTTPS hosting for iPhone. No Apple Developer account or App Store submission is necessary.

## Features and usage
- Home: weekly session count, latest weight, daily protein, next A/B/C workout and elapsed-time recovery indicators.
- Workout: A/B/C core routines, D/E lighter optional routines, per-set weight/reps/completion, last performance, rest countdown, workout history and progression cues. The suggested load increase is conditional on good technique and 1–3 reps in reserve. Use rest days between demanding full-body sessions. Optional sessions are not required and should be skipped when sore.
- Diet: Indian veg days Tue/Thu/Sat, nonveg Sun/Mon/Wed/Fri, suggested meals, custom protein and optional calorie logging. Portions/protein estimates are not individualized medical advice.
- Body: starting weight 74.5 kg, optional waist/chest/arm/thigh, weight trend and history.
- Photos: choose front/side/back progress pictures, stored as compressed JPEG locally.
- Backup: export/import JSON, including photos and current draft. Import replaces all data. Keep backups private.

## Privacy and limitations
No analytics or network data upload by the app. Local storage is device/browser/origin-specific, not encrypted by the app, and may be cleared by iOS or the user. It has limited capacity; export backups frequently, especially with photos. The installed home-screen app may have separate storage from Safari depending on iOS version. No account sync, Apple Health, native notification, App Store binary or hosted URL is included. Rest timer may not alert when the screen is locked; it recalculates remaining time on return. Recovery is a simple 48-hour elapsed-time heuristic, not a physiological measurement. Starting loads are deliberately unspecified.

## Files
index.html (shell), style.css (responsive light theme), app.js (data and UI), manifest.webmanifest (installation metadata), sw.js (offline caching), icon PNG files.

## Verification
JavaScript syntax checked with Node. Actual iPhone installation and browser interactions require testing on your device. To update deployed source, bump CACHE in sw.js to a new version so the offline cache refreshes.
