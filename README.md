# Brinkmanship: National Council

100 playable nations. 17 gameplay sections. Separate desktop and mobile interfaces using the newest supplied framework.

## Play

**Live:** https://grandbigb.github.io/brinkmanship-game-alpha/

- `/` (index.html) picks desktop or mobile from the opening viewport.
- `/desktop.html` forces the desktop edition; `/mobile.html` forces the mobile edition.
- Older links (`brinkmanship-desktop.html`, `brinkmanship-mobile.html`) redirect to the new editions.

To play locally, keep every file and the `assets/` folder together and serve the folder (e.g. `python3 -m http.server 8080`). Safari's Files preview is not a full game browser; use the hosted URL or native build.

## GitHub

This repository holds the built site (the `dist/` output of the full project) at the root and publishes with GitHub Pages from the `main` branch, root folder. Any upload to `main` redeploys within a minute or two. `.nojekyll` tells Pages to serve the files as-is.

No API keys, paid service, backend, or account system are required by the game.

## Preserve the simulation

- `source/desktop.html` and `source/mobile.html`: original latest supplied framework.
- `dist/council.js` and `dist/council.css`: presentation layer and UI preferences.
- `dist/national-art.js`: country-to-art mapping.
- `dist/assets/nations/`: generated national council portraits, grouped as atlases.
- `tools/build.mjs`: adds the presentation layer without editing game logic.
- `tools/verify.mjs`: engine parity, screen coverage, country coverage, and seeded simulation checks.
- `native/`: optional Capacitor mobile wrapper configuration.

```sh
npm run build
npm test
npm run package
```

The web build and tests need Node 22+, with no npm dependencies. The final command creates the complete `releases/brinkmanship-github.zip`. For hosted downloads it also creates separate code and country-artwork ZIPs below the host’s file-size limit. Download both from Settings and extract into the same folder, or use the single complete ZIP supplied in chat. Run the package command after extracting to restore the downloadable ZIPs.

## Saves

Original campaign JSON export/import and per-turn autosave remain. Saves belong to the current browser origin and device. Export before moving between local files, GitHub, Sites, or the native app. No cloud saves are provided. Existing saves retain the framework's own compatibility rules; no claim is made that older 45-nation saves can supply missing 100-nation state.

## Mobile and App Store

The mobile edition uses touch controls, safe-area spacing, compact art, department navigation, and full-screen decision panels. The optional wrapper packages the same local game for iOS/Android. See [MOBILE-APP.md](docs/MOBILE-APP.md). This is source and configuration, not a signed IPA/APK or an App Store-approved app.

## Country identity and artwork

Institutions are driven by the supplied framework's per-country `DEPTS` / `DEPTS2` tables. US defence is displayed as **Department of Defense**, as requested. Russia's overseas intelligence displays **Foreign Intelligence Service (SVR)**; its domestic screen also identifies **FSB**. Equivalent labels are used in navigation, headings, and the department menu.

All playable countries receive a national council portrait. These are fictional advisers and imagined interiors with country-related architecture, not actual officials or verified headquarters. Each nation has its own council portrait and country context. Six separate department environments restore the first edition’s scene-based military, diplomacy, trade, intelligence, research and economic settings. Those nationality-neutral department interiors appear beside the national adviser scene; they are not claimed to be real government facilities. Department labels, briefings, and controls vary with the active function. Motion is ambient lighting and transitions, not character performance animation.

Some institution names and fallback department names are inherited approximations. They have not all been independently verified as current official English names. See [IDENTITY-NOTES.md](docs/IDENTITY-NOTES.md).

## Validation limits

Automated checks cover game preservation and generated screen output. Full browser layout testing, VoiceOver/TalkBack, native builds, and device performance testing remain outstanding. AAA-inspired presentation is a design direction, not a claim of AAA production or certification.

No new license is imposed on the user-supplied framework. Review original asset/code rights before a public commercial release.
