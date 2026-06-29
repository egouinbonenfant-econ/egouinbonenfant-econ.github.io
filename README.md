# Personal website — Émilien Gouin-Bonenfant

Static site (plain HTML/CSS, no build step) ready to host on GitHub Pages.

## Contents

```
index.html                 the whole site (one file)
assets/photo.jpg           headshot
assets/papers/             CV + bundled paper PDFs
README.md                  this file
.nojekyll                  tells GitHub Pages to serve files as-is
```

All papers that were on your Google Drive are now bundled in `assets/papers/`. Co-authored
papers hosted on a co-author's site (Inelastic Capital, Producing Tangible and Intangible
Capital) still link out to those sites, exactly as before. Publisher and code links are unchanged.

## Publish it on GitHub Pages

You need a free GitHub account. Two ways — the web upload is easiest if you don't use git.

### Option A — upload in the browser (no command line)

1. Go to https://github.com/new and create a repository.
   - To get a URL like `https://<username>.github.io`, name the repo exactly
     `<username>.github.io` (e.g. `emgbgo.github.io`).
   - Otherwise pick any name (e.g. `website`); the URL will be
     `https://<username>.github.io/<repo>/`.
   - Set it to **Public**. Don't add a README (you already have one).
2. On the new repo page, click **uploading an existing file**.
3. Drag in `index.html`, `README.md`, `.nojekyll`, and the whole `assets` folder
   (keep the folder structure). Click **Commit changes**.
4. Go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch **main**, folder **/ (root)**, and Save.
5. Wait ~1 minute, then reload. The Pages section shows your live URL.

### Option B — command line (git)

```bash
cd path/to/site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

Then do step 4 above (Settings → Pages).

## Custom domain (optional)

If you want a custom domain (e.g. `emiliengb.com`): buy the domain, add a file named
`CNAME` at the repo root containing just the domain, then point your domain's DNS at
GitHub Pages per https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site

## Editing later

Everything is in `index.html`. To add a paper, copy one of the `<div class="paper">`
blocks and edit the text and link. Drop new PDFs into `assets/papers/`.
