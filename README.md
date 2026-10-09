# Chloe Chan — Marketing Portfolio

A single-page personal portfolio / online CV, built with plain HTML, CSS and vanilla JavaScript.
No build step, no dependencies — drop the files into a GitHub repository and publish with GitHub Pages.

## Files

```
/
├── index.html                  # the whole site (one page, all sections)
├── assets/
│   ├── css/style.css           # styling, dark mode + print stylesheet
│   ├── js/main.js              # theme toggle, mobile menu, scroll-spy, reveal, print
│   ├── img/chloe-chan.jpg      # profile photo (640×640)
│   └── Chloe_Chan_CV.pdf       # downloadable / printable CV
├── .nojekyll                   # tells GitHub Pages to skip Jekyll processing
└── README.md
```

Everything is self-contained: **no npm, no CDN, no build**. Opening `index.html` locally works too.

## Deploy by dragging files into GitHub

1. **Create the repo** — go to <https://github.com/new>, name it `chloe-chan` (or `<your-username>.github.io`
   if you want the site at the root domain), keep it **Public**, tick *Add a README* or leave it empty, then
   **Create repository**.
2. **Open the upload page** — on the empty repo you'll see the *"…or upload an existing file"* link; click it
   (or go directly to `https://github.com/<you>/<repo>/upload`).
3. **Drag the files in** — drag `index.html`, `README.md`, `.nojekyll` and the whole `assets/` folder onto
   the drop zone. GitHub preserves folder structure when you drag a folder, so `assets/` arrives intact.
   > Hidden files starting with a dot (`.nojekyll`) are uploaded fine by drag & drop. If your OS hides them,
   just skip it — the site still works; only Jekyll processing may kick in.
4. **Commit** — add a message like `Add portfolio site`, choose *Commit directly to the main branch*,
   click **Commit changes**.
5. **Turn on Pages** — repo page → **Settings** → **Pages** → under *Build and deployment*,
   Source: **Deploy from a branch**; Branch: **main**, folder: **/ (root)** → **Save**.
6. **Wait ~30–60 seconds**, then refresh the Pages screen — GitHub shows the live URL:
   `https://<you>.github.io/<repo>/` (or `https://<you>.github.io/` for a `<user>.github.io` repo).

Tip: after the first upload you can edit any file in place — click the file → pencil icon → edit → *Commit changes*.

## Custom domain (optional)

Add a `CNAME` file at the repo root containing just your domain (e.g. `chloechan.com`), point a
**CNAME DNS record** at `<you>.github.io`, then set the same domain in *Settings → Pages → Custom domain*
and enable *Enforce HTTPS*.

## Editing the content

All content lives in `index.html`, in clearly commented sections (`<!-- ============ HERO ============ -->` etc.).
Common tweaks:

| What | Where |
| --- | --- |
| Name, title, contact details | `<section class="hero">` and `#contact` |
| Photo | replace `assets/img/chloe-chan.jpg` (keep the filename, square image ~640×640) |
| Accent colour | `--accent` in `assets/css/style.css` `:root` (plus the `[data-theme="dark"]` block) |
| Sections / order | move the `<section>` blocks in `index.html`; update the links in `<nav>` |
| PDF for download | replace `assets/Chloe_Chan_CV.pdf` |

To regenerate the PDF after edits: open the site in a browser and press **⌘/Ctrl + P** → *Save as PDF*
(the print stylesheet produces a clean, link-friendly CV).

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Or just double-click `index.html`.

## Features

- Responsive layout (desktop / tablet / phone), sticky nav with scroll-spy
- Light / dark mode with `localStorage` memory and `prefers-color-scheme` default
- Print-optimised stylesheet — the page prints as a clean CV
- Accessible: skip link, semantic landmarks, `aria` labels, keyboard-friendly controls
