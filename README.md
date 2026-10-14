# EditifyPDF

Private PDF tools that run entirely in your browser. Nothing is uploaded.

## Deploy on GitHub Pages
1. Put every file from this folder in the root of your repository (`index.html`, `sw.js`, `manifest.webmanifest`, the `icon-*` files and `icon.svg`).
2. Repository **Settings → Pages → Build and deployment → Deploy from a branch → main / (root)**.
3. Open `https://<your-username>.github.io/<repo-name>/` and use your browser's **Install app** option.

`index.html` also works on its own: without `sw.js` and the manifest it simply skips the install and offline features.

## Offline use
* After the first online visit the service worker (`sw.js`) caches the app and its CDN libraries, so the tools keep working offline.
* The OCR tool downloads the OCR engine and the language data once, then caches them as well.

## Optional: host the libraries yourself (no CDN)
Download these four files into a `libs/` folder next to `index.html`. They are used automatically when the CDN cannot be reached.

| File to create | Download from |
|---|---|
| `libs/pdf-lib.min.js` | https://cdnjs.cloudflare.com/ajax/libs/pdf-lib/1.17.1/pdf-lib.min.js |
| `libs/pdf.min.js` | https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js |
| `libs/pdf.worker.min.js` | https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js |
| `libs/jszip.min.js` | https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js |

## Keyboard shortcuts
* **Ctrl/Cmd + Enter**: run the current tool
* **Arrow keys, Home, End** (with the tool list focused): switch tools
* **Esc**: close the preview panel

## Notes
* Password protection uses AES-128 (PDF standard security handler). Copy and print restrictions are advisory: some PDF software ignores them.
* OCR needs an internet connection the first time it runs.
