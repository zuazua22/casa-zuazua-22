# Casa Zuazua 22 – rental listing

Static one-page site (plain HTML, CSS and JavaScript — no build step) for the rental of
Zuazua 22, San Miguel Chapultepec, CDMX.

```
index.html     the whole page (styles and scripts are inline)
images/        facade photo + 25 gallery photos
favicon.svg    browser-tab icon
og-image.jpg   1200×630 preview image for link sharing (see "Link preview")
.nojekyll      tells GitHub Pages to serve the files as-is
```

## Publish on GitHub Pages

### Option A – from the browser (no git needed)
1. On GitHub, click **New repository**. Pick a name (e.g. `casa-zuazua-22`), keep it **Public**, and create it.
2. Click **uploading an existing file** (or **Add file → Upload files**) and drag in the **contents** of this folder
   (`index.html`, `images/`, `favicon.svg`, `og-image.jpg`, `.nojekyll`, `README.md`) so that `index.html` sits at the top level of the repo. Commit.
   - If your system hides dotfiles, `.nojekyll` can be skipped; the site works without it.
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**, and **Save**.
4. After a minute or two the site is live at `https://YOUR-USER.github.io/casa-zuazua-22/` (use your own username and repo name).

### Option B – with git
```bash
cd path/to/this/folder
git init -b main
git add .
git commit -m "Publish rental listing"
git remote add origin https://github.com/YOUR-USER/YOUR-REPO.git
git push -u origin main
```
Then enable Pages as in step 3 above.

All paths in the page are relative, so it works both at `https://user.github.io/repo/` and on a custom domain.

## Link preview (WhatsApp, iMessage, etc.)
Link previews need an absolute image URL, which is only known once the site is live. After publishing, add this inside `<head>` in
`index.html` (replace the URL with yours) and commit:

```html
<meta property="og:image" content="https://YOUR-USER.github.io/YOUR-REPO/og-image.jpg">
<meta property="og:url" content="https://YOUR-USER.github.io/YOUR-REPO/">
```

## Editing later
- **Price, texts, phone number:** edit `index.html` directly (search for `70,000`, or for the WhatsApp number in the `CONTACTO` block near the bottom).
- **Photos:** put the file in `images/` and add or remove its line in the `FOTOS` block near the bottom of `index.html`. Keep photos around 1200 px on the long side so the page stays fast.
- **Accent color:** change `--accent` (and the dark-mode values) at the top of the `<style>` block.

## Good to know
- GitHub Pages sites are public, and the page shows the contact phone number. A free GitHub account needs a public repository for Pages.
- The only external resource is Google Fonts (Fraunces and Inter). If it can't load, the page falls back to Georgia and system sans-serif.


## Updating the page

- **Price / exchange rate:** edit `PRECIO` near the top of the `<script>` in `index.html` (`mxn`, `tipoCambio`, `fecha`). The USD equivalent is calculated automatically.
- **Texts (Spanish and English):** edit the `I18N` object in the same script.
- **Floor plan:** it is `images/plano.jpg`; replace that file to update it.
- **Video:** the walkthrough is embedded from YouTube (`V-9Gc14awrE`) in the Gallery section.
