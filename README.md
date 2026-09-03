# prajwal.ak — portfolio (preview)

A single-page portfolio for Prajwal Arun Kumar, Data Engineer with applied AI fluency.

Dark, pipeline-themed design: the hero shows an animated DAG (raw sources → Spark/PySpark → dbt → warehouse → BI/LLM layer) representing the actual shape of the work, and the Experience section is styled like a pipeline "run history" — task IDs, success status pills, run durations.

## Structure

```
index.html   — all content/markup
style.css    — design system (colors, type, layout, animation)
script.js    — scroll-reveal + active nav highlighting
og-image.png — social share preview image (LinkedIn, Twitter, etc.)
og-image.svg — source for the above, editable if you want to tweak it
```

No build step, no dependencies beyond two Google Fonts (IBM Plex Mono, IBM Plex Sans) loaded via CDN. Nothing to install.

## Step 1 — Preview in a separate repo

This keeps your live `prajwal2k.github.io` site untouched while you look this over.

1. On GitHub, create a **new repository** — any name works, e.g. `portfolio-preview`. Keep it public (GitHub Pages needs that on the free tier, unless you're on GitHub Pro/Enterprise).
2. Clone it locally, then copy `index.html`, `style.css`, and `script.js` into the repo root.
3. Commit and push:
   ```bash
   git add .
   git commit -m "Add pipeline-themed portfolio preview"
   git push origin main
   ```
4. In the repo's **Settings → Pages**, set the source to "Deploy from a branch," branch `main`, folder `/root`. Save.
5. GitHub will publish it at `https://prajwal2k.github.io/portfolio-preview/` within a minute or two.

Check it out there, on both desktop and a phone. Once you're happy with it:

## Step 2 — Promote it to your main site

1. In your existing `prajwal2k/prajwal2k.github.io` repo, delete or move aside `index.html`, `styles.css`, `script.js`, and the `images/`, `dist/`, `package.json`, `tailwind.config.js`, `postcss.config.js` files from the old build (you already have those backed up).
2. Copy this preview's `index.html`, `style.css`, and `script.js` into the repo root instead.
3. Commit and push. It'll go live at `https://prajwal2k.github.io/` on the next Pages build (usually under a minute).
4. Optional: delete the `portfolio-preview` repo once you're confident, or leave it as a staging ground for future tweaks.

## Content notes

- Resume link points to your Google Drive PDF. Swap the URL in `index.html` (search for `drive.google.com`) if you update the file.
- Certification cards link out to your real Databricks and Credly verification pages.
- All experience, project, and metric details are pulled directly from your LaTeX resume — nothing fabricated.
- No photo is included. If you want your headshot in the hero, share the image and I'll wire it in.
- **OG/social preview image**: the `<head>` tags reference `https://prajwal2k.github.io/og-image.png` — this only resolves correctly once the site is live at your root domain. While previewing in a separate repo, social share previews won't show the image (not a bug, just expected). Once you promote to `prajwal2k.github.io`, copy `og-image.png` into the repo root alongside `index.html` and it'll work.
- Project cards don't link to GitHub repos yet since none are public. Add `href` links to each `<h3>` in the Projects section whenever you publish the code — even a short line like "code available on request" is a reasonable placeholder in the meantime if you're not ready to make a repo public.
