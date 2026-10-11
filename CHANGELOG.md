# Changelog

## 1.1.0 - 2026-10-10
### Added
- App version (`v1.1.0`) is now shown unobtrusively in a footer at the bottom of every screen.
  - index.html: added a footer element (id `ver`) below `#app`, styled with the existing `--mu` color variable.
  - sw.js: cache name changed from strength-log-v2 to strength-log-v3 so installed apps load the updated index.html.
  - app.js, style.css and the database structure are unchanged; no workout data is touched.
- Version is kept in sync manually: update the footer text in index.html together with this changelog on each approved release.

### Test results
Verified (headless Chromium, 390 px wide phone-size window, project served over localhost):
- `node --check` passes for sw.js and app.js.
- Footer shows `v1.1.0` and is visible on Home, Squat entry, History, Settings and the "Workout saved" screen.
- Saving a one-set test workout still works ("Workout saved" appears) and no page errors were logged.
- After load, the only cache present is `strength-log-v3`.
- Screenshot of the saved screen checked: footer is small, muted and centered below the buttons.
- app.js, style.css, icon-192.png and icon-512.png are byte-identical to the uploaded 1.0.1 files (checksums match).

Not verified:
- Appearance on the real Samsung phone, and in dark theme.
- That an already-installed app upgrades from v2 to v3 and shows v1.1.0 after deployment.
- Edit, delete, import/export, kg mode and rest timer after the update (no code involved changed, but not run).

## 1.0.1 - 2026-10-10
### Fixed
- Individual sets can now be saved, so you can alternate between Squat and Deadlift.
  - app.js: blank unsaved trailing sets are skipped on save; opening an exercise resumes today's workout if it has fewer than 4 sets.
  - sw.js: cache name changed from strength-log-v1 to strength-log-v2 so installed apps load the new app.js.

## 1.0.0 - initial version
- First release.
