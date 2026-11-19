# Lane — training log (offline PWA)

Runs fully on your phone. No account, no server, works offline after the first visit.

## Deploy to GitHub Pages

1. Create a repo (e.g. `lane`), or a `lane/` folder inside the repo that serves samielsabri.me.
2. Upload these files, keeping the structure:
   ```
   index.html
   manifest.webmanifest
   sw.js
   icons/icon-192.png
   icons/icon-512.png
   icons/icon-maskable-512.png
   icons/apple-touch-icon.png
   ```
3. Separate repo: Settings → Pages → Deploy from branch → `main` / root.
   It will be live at `https://<username>.github.io/lane/` (or `samielsabri.me/lane/` if your custom domain covers it).
   Folder in your site repo: it's live at `samielsabri.me/lane/` on the next deploy.

HTTPS is required for offline mode; GitHub Pages provides it.

## Install on your phone

- iPhone: open the URL in **Safari** → Share → Add to Home Screen.
- Android: open in **Chrome** → ⋮ → Install app.

Open it once while online. After that it works with no connection.

## Move your data over from the Claude version

1. In the Claude tracker: More → Export JSON.
2. In Lane: More → Restore or import a backup → pick that file.

## Backups

Data lives only on the phone. More → Back up now opens the share sheet; save to Files / iCloud Drive or email it to yourself.
The header turns amber when your last backup is over 14 days old.

## Updating the app

After editing `index.html`, change `VERSION` in `sw.js` (e.g. `lane-v2`) so phones fetch the new version.
Your data is not affected by updates.
