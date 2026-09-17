# Powerus systems catalog — static site

`index.html` is the complete catalog in one self-contained file. No build step, no
dependencies. It needs network access at runtime (product photography from power.us,
three.js from unpkg).

## Publish on GitHub Pages

1. Put these two files at the root of the `main` branch of `romant-hash/repository`:
   `index.html` and `.nojekyll`.
   - Web UI: repo → Add file → Upload files → drag both in → Commit.
   - CLI:
     ```
     git clone https://github.com/romant-hash/repository.git
     cd repository
     cp /path/to/index.html /path/to/.nojekyll .
     git add index.html .nojekyll
     git commit -m "Publish systems catalog"
     git push origin main
     ```
2. Repo → Settings → Pages.
3. Source: **Deploy from a branch**. Branch: **main**, folder: **/ (root)**. Save.
4. Wait for the green check on the Pages screen (30–60s on first publish).

Live URL: `https://romant-hash.github.io/repository/`

Updating later: replace `index.html` and push — Pages redeploys automatically. If the page
looks stale, hard-reload (Pages caches aggressively for a minute or two).

## Notes

- `.nojekyll` matters: without it GitHub's Jekyll step can skip files and mangle output.
- If the repo is private, Pages requires a paid plan; make it public for a free URL.
- Custom domain: Settings → Pages → Custom domain, then a CNAME at your DNS provider.
