# Daily Briefing

A single-page dashboard for weather, stock quotes, top deals, and headlines. Settings and the watchlist sync to Firestore.

## Setup

1. In the Firebase console, create a Firestore database, enable **Anonymous** sign-in under Authentication, and set the Firestore security rules so each user can only access `users/{uid}/...`.
2. In the repo, go to **Settings → Secrets and variables → Actions** and add:
   - `FIREBASE_API_KEY`
   - `FIREBASE_SENDER_ID`
   - `FIREBASE_APP_ID`
3. Go to **Settings → Pages** and set **Source** to **GitHub Actions**.
4. Push to `main`. The workflow fills in the Firebase values at deploy time, so the keys never appear in the repo.

The Firebase web config is visible to anyone who opens the site, as with any Firebase web app. Security comes from the Firestore rules, not from hiding the key.

## Local use

Open `index.html` in a browser. Until the placeholders are replaced, Firestore sync is disabled and the app uses browser storage only.
