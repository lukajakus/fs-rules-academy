# FS Rules Academy

Bilingual Croatian/English mobile-first PWA for studying Formula Student concepts.

## Features
- EV and T concept lessons, bilingual search and filters
- 5-question quiz with explanations
- Learning progress and quiz history stored locally
- Offline support with a service worker
- JSON lesson import and progress export
- iPhone home-screen installation via Safari

## Important accuracy notice
The included starter lessons are **educational paraphrases, not official Formula Student Rules text**. This version does not include a verified full translation of Formula Student Rules 2026 v1.1. Do not use the educational content as a compliance reference. Verify requirements against the official competition rulebook.

## Run locally
Serve the directory over HTTP (service workers require localhost or HTTPS):

```bash
python3 -m http.server 8000
```

Open http://localhost:8000. For iPhone installation, deploy to HTTPS hosting (for example GitHub Pages), open in Safari, choose Share → Add to Home Screen.

## GitHub upload
Create or open a repository and upload **all files at the root**. Enable GitHub Pages in Settings → Pages → Deploy from a branch → main → /(root). The published HTTPS URL will be displayed there.

## JSON lesson format
See the downloadable template under Progress. The imported JSON must be an array of objects with unique `id`, `section` (EV or T), and bilingual `title`, `text`, and `explain` objects containing `hr` and `en` strings. Imported lessons are stored locally in the browser.

## Technical details
Vanilla JavaScript, CSS, HTML; no server, account, or external dependencies. Progress stays in localStorage on the current device/browser. The service worker caches application files for offline use after the first successful online load.
