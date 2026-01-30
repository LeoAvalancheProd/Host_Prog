# Host_Prog

Festival Lineup static site

This repository contains a single-page interactive festival lineup that includes an admin panel stored in the browser (LocalStorage). It can be hosted as a static site using GitHub Pages.

Quick setup (publish on GitHub Pages) ✅

1. Ensure `index.html` is at the repository root (this repo already contains it).
2. Commit and push to the `main` branch.
3. On GitHub, open the repository → **Settings** → **Pages**.
4. Under "Source", select **main** branch and **/ (root)** folder, then click **Save**.
5. After a minute, your site will be available at `https://<your-github-username>.github.io/<repository-name>/`.

Notes & tips:

- This site is fully static. Artist data is stored in your browser's LocalStorage when using the admin panel.
- If you want to use a custom domain, add a `CNAME` file at the repo root or configure in the Pages settings.
- A `.nojekyll` file is included to prevent GitHub Pages from using Jekyll processing.

If you'd like, I can add a GitHub Action to auto-deploy or create a `gh-pages` branch for you.
