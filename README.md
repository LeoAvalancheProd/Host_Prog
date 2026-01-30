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

Admin access

- **Admin UI is now a dedicated page:** open `/admin.html` to log in and manage the lineup. The main site pages (`index.html` and `festival-lineup-wordpress-fixed.html`) are read-only public views; they no longer contain the inline CMS to prevent accidental access.
- **Password (client-side):** `M4M2026` (note: client-side password is not secure for production — consider server-side auth for real deployments).
- **Local file support:** You can open `festival-lineup-wordpress-fixed.html` and `admin.html` directly from the same folder using `file://` (e.g., `file:///Users/you/Downloads/festival-lineup-wordpress-fixed.html`). The admin button and redirects are relative and login stores auth in `localStorage` so both files will work when opened locally.

Simple protections implemented on `admin.html`:
- 3s cooldown after each failed attempt to slow guessing attacks.
- Lockout after 5 failed attempts for 10 minutes. Failed attempts are tracked in `localStorage`.
- Attempt/lockout status is shown on the login page.

Audit log (timestamped):
- All admin actions are recorded to a timestamped audit log in `localStorage` under `festival_lineup_audit` (add/update/delete/import/export/clear/login/logout).
- Audit is visible in the admin UI and can be exported or cleared.
- Audit entries are capped to the most recent 500 events.

- If you want to use a custom domain, add a `CNAME` file at the repo root or configure in the Pages settings.
- A `.nojekyll` file is included to prevent GitHub Pages from using Jekyll processing.

If you'd like, I can add a GitHub Action to auto-deploy or create a `gh-pages` branch for you.
