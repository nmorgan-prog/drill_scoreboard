# Drill Scoreboard

Offline practice-drill scoreboard for iPad, built to be mirrored to a smartboard.
The app is `index.html`; the other files only exist so it installs to the Home Screen and runs offline.

```
index.html             the whole app (HTML + CSS + JS)
manifest.webmanifest   Home Screen name, icon, landscape/standalone
sw.js                  service worker that caches the app for offline use
icons/                 app icons
```

## Host it free on GitHub Pages (about 5 minutes)

1. Create a new **public** repo on github.com, e.g. `drill-scoreboard`.
2. Upload every file in this folder, keeping the `icons/` folder (the offline cache breaks if the icons sit at the top level) (Add file → Upload files → drag them in → Commit).
3. In the repo, open **Settings → Pages**. Under *Build and deployment*, set Source = **Deploy from a branch**, Branch = **main**, folder = **/ (root)**, then Save.
4. Wait a minute or two. Your app is at `https://<your-username>.github.io/drill-scoreboard/`.

## Put it on the iPad Home Screen

1. Open that URL in **Safari** on the iPad. It has to be Safari; other browsers can't install web apps on iPadOS.
2. Tap **Share** (the square with the up arrow) → **Add to Home Screen** → **Add**.
3. Launch it from the Home Screen icon once **while you're on Wi-Fi** so it caches itself. After that it runs with no internet.
4. Recommended: **Settings → Display & Brightness → Auto-Lock → Never** during practice. The app asks the iPad to stay awake, but older iPadOS versions don't always honor that for Home Screen apps.
5. For mirroring, use **Control Center → Screen Mirroring**, or the HDMI adapter (it mirrors automatically). Lock rotation in landscape.

## Updating the app later

Edit the files, then change `VERSION` at the top of `sw.js` (e.g. `v1` → `v2`) and upload again.
The iPad picks up the new version the **second** time you open the app while online. The first launch downloads it in the background.

## Data

Everything is saved in the iPad's local storage for this site: the roster, presets, setup, and any drill in progress.
- Refreshing or closing the app mid-drill resumes it exactly where you left off. A running clock keeps counting while the app is closed, like a real game clock.
- Data lives only on this iPad. **The Safari Home Screen app and a regular Safari tab keep separate data**, so always use the Home Screen icon.
- Clearing Safari website data will erase it.
