# Kefka Symbol Sync

A tiny static raid tool for syncing your symbol with your partner using a free Firebase Realtime Database backend and a Picture-in-Picture overlay.

## What it does

- Shows **You** on the left and **Partner** on the right.
- Has 3 buttons: **AOE**, **Cone**, **Stack**.
- Has a **Clear** button.
- Opens a mini always-on-top overlay using Document Picture-in-Picture in Chrome/Edge.
- Uses room links like `?room=kefka123&player=A` and `?room=kefka123&player=B`.

## Files

- `index.html` — the app
- `firebase-config.js` — paste your Firebase config here
- `assets/Aoe.svg`
- `assets/Cone.svg`
- `assets/Stack.svg`

## Free setup

1. Create a free Firebase project.
2. Add a Web App in Firebase.
3. Create a Realtime Database.
4. Copy the Firebase web config into `firebase-config.js`.
5. Host the folder free on GitHub Pages or Cloudflare Pages.
6. Open the page, create/copy a room link, and give your partner the matching partner link.

## Firebase database rules for testing

For private usage/testing, you can start with this in Realtime Database rules:

```json
{
  "rules": {
    "rooms": {
      "$room": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

This is open, so do not store private info in the tool. The app only stores room symbols and a timestamp.

## Browser support

Document Picture-in-Picture works best in Chrome/Edge. If unsupported, open the app in a small browser window and pin it with Microsoft PowerToys Always On Top.
