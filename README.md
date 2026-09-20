# Bible Adventure — Sunday School Digital Companion

A weekly, interactive Bible lesson app for children, built for **The Covenant
Nation Lekki** Sunday School. Children play age-tiered games (a Bible quiz,
word search, verse memorization, "Who am I?" and more) tied to that week's
lesson, and earn adventure points and badges. Teachers sign in to write the
week's lesson, add a picture, and publish it to every device at once.

The app is a single self-contained web page backed by
[Firebase](https://firebase.google.com/) (Firestore for data, Authentication
for teacher sign-in), so it costs nothing to run at Sunday School scale and
needs no server of your own to maintain.

## ✨ Features

- **Three age tiers** (3–5, 6–9, 10–12) — each gets a tuned set of activities and difficulty.
- **Shared, cross-device data** — the class roster, lessons, and every child's
  progress are the same on every tablet, phone or computer that opens the app.
- **Teacher dashboard** — write lessons, add a picture, manage the class,
  and see engagement reports, all gated behind a real sign-in.
- **Badges and points** that carry over week to week, without letting a
  replayed game inflate a child's score past that activity's maximum.
- **Works offline-ish** — a child's progress is cached on-device and syncs
  back to Firebase once the connection returns.

## 📂 What's in this repository

| File | Purpose |
|---|---|
| `index.html` | The whole app — open this in a browser, or host it as-is. |
| `firestore.rules` | Security rules to paste into the Firebase console. |
| `SETUP.md` | Step-by-step guide to create a free Firebase project and connect it. |
| `LICENSE.md` | The project's license. |
| `.gitignore` | Files that shouldn't be committed (local Firebase CLI artifacts, editor files, etc.). |

## 🚀 Getting started

1. Follow **[SETUP.md](./SETUP.md)** to create a free Firebase project,
   enable Firestore and Email/Password sign-in, and paste your project's
   config into `index.html`.
2. Host `index.html` (Firebase Hosting, GitHub Pages, Netlify — any static
   host works, since all the data lives in Firebase, not on the host).
3. Open the app, sign in as a teacher, and click **Load the 4 starter
   lessons** to bring in the lessons this app shipped with.

> **Note:** opening `index.html` by double-clicking it from your file system
> won't fully work — browsers block module scripts on `file://` pages. Serve
> it over `http://localhost` for local testing, or deploy it, as described
> in SETUP.md.

## 🔐 A note on privacy

Children pick their name from a shared list rather than logging in
individually, which means anyone with the app's link can see and edit any
child's profile and progress. That's a reasonable trade-off for a small,
trusted Sunday School class — just don't share the link publicly. See
SETUP.md and `firestore.rules` for the full reasoning and how to tighten
things further if needed.

## 📄 License

See [LICENSE.md](./LICENSE.md).
