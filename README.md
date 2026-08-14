# Jay Hall — Portfolio

Static site, no build step. Plain HTML/CSS/JS so it's easy to edit and host on GitHub Pages.

```
index.html          → homepage
resume.html          → readable résumé page (add resume.pdf here for the download button)
projects/honeybees.html  → example project case-study page — duplicate this for ThermoBloom, Perovskites, etc.
css/style.css         → the whole design system (colors, type, layout)
js/main.js            → scroll-reveal + active nav highlighting
```

## Design system: "Field Manual"
Earthy 3-color palette (clay / sage / mustard) on a grain-paper background, blending two references:
- **1980s technical manual** — dashed leader lines, "FIG. 0X" captions under every image, section markers, monospace labels
- **Indie-game UI** — corner-bracket frames on figures (like a camera reticle / menu selection), chunky drop-shadow buttons, a pixel font (`Press Start 2P`) used sparingly on badges and the nav mark

To reuse the figure-frame + caption pattern elsewhere, copy this block:
```html
<figure class="bracketed">
  <img src="your-image.jpg" alt="...">
  <span class="bx1"></span><span class="bx2"></span>
</figure>
<p class="fig-caption"><b>FIG. 0X</b> — your caption</p>
```

## What to swap in first
- Replace every `[placeholder-art]` box with a real `<img>` or `<video>` tag (keep the `bracketed` figure wrapper + the two `<span>` corner marks).
- Replace the placeholder email, GitHub, and LinkedIn links (search for `jay@example.com`, `github.com/`, `linkedin.com/`).
- Fill in the "Experience" section in `resume.html`.
- Add a real `resume.pdf` next to `resume.html` (or remove the download button).
- Duplicate `projects/honeybees.html` for your other case studies, and link them from `index.html`.

## Publish it on GitHub Pages

1. Create a new repository on GitHub (e.g. `jayhall.github.io` for a root-level user site, or any name like `portfolio` for a project site).

2. From inside this folder, run:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```

3. On GitHub, go to your repo → **Settings → Pages**.
   - Under "Build and deployment", set **Source** to `Deploy from a branch`.
   - Set **Branch** to `main` and folder to `/ (root)`.
   - Save.

4. GitHub will publish the site within a minute or two at:
   - `https://YOUR-USERNAME.github.io/YOUR-REPO/` (project repo), or
   - `https://YOUR-USERNAME.github.io/` (if the repo is named `YOUR-USERNAME.github.io`)

5. Every future `git push` to `main` updates the live site automatically.

## Local preview
Just open `index.html` in a browser — no server required. (For the cleanest preview with relative paths behaving exactly like production, you can also run `python3 -m http.server` from this folder and visit `http://localhost:8000`.)
