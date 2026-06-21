# Argho Dey — Academic Homepage

A lightweight, dependency-free personal website (plain HTML + one CSS file)
for hosting on **GitHub Pages** at `https://<username>.github.io`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Home — bio, contact, news |
| `research.html` | Research interests + selected projects |
| `publications.html` | Full publication list (CV + Google Scholar) |
| `style.css` | Shared styling for all pages |
| `public/` | Put `profile.jpg` and any other images here |

## Quick start: publish to GitHub Pages

1. **Create the repository.** On GitHub, make a new **public** repo named exactly
   `<your-username>.github.io` (e.g. `arghodey.github.io`). The name must match
   your username for a user site.

2. **Add these files** to the root of that repo. Either:
   - drag-and-drop them in the GitHub web UI ("Add file → Upload files"), **or**
   - use git:
     ```bash
     git clone https://github.com/<username>/<username>.github.io.git
     cd <username>.github.io
     # copy index.html, research.html, publications.html, style.css, public/ in here
     git add .
     git commit -m "Initial site"
     git push origin main
     ```

3. **Enable Pages.** Repo → **Settings → Pages** → Source: *Deploy from a branch* →
   Branch: `main`, folder: `/ (root)` → Save.

4. Wait ~1 minute, then visit **`https://<username>.github.io`**. Done.

## Add your photo

Place a square image at `public/profile.jpg`, then in `index.html`:
- delete the `<div class="photo-fallback">AD</div>` line, and
- uncomment the `<img class="photo" ...>` line just above it.

Until then, an "AD" initials block shows as a placeholder.

## Things to fill in before launch

- [ ] **GitHub link** in `index.html` (currently a placeholder `https://github.com/`).
- [ ] **LinkedIn URL** — I used `https://www.linkedin.com/in/argho-dey`. Confirm this
      is your public profile; the `linkedin.cn/incareer/...` link you gave is an
      internal redirect and won't work for visitors.
- [ ] Verify the **paper/code links** on the Publications and Research pages.
- [ ] Add links to PDFs/arXiv as papers become available.

## Customizing the look

All colors and fonts live in the `:root` block at the top of `style.css`.
Change `--accent` (currently a warm sienna) to recolor the whole site.

## Notes on the publication list

Publications were combined from your CV and confirmed against your published work.
"Accepted" / "Under review" badges reflect the status in your CV — update these
in `publications.html` as papers progress. Names in **bold** mark you as an author.
