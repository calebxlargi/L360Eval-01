# Leadership Practices Assessment

A static, single-page assessment and report. `index.html` contains the application; there is no build step, backend, package manager, or secret to configure. `_headers` adds basic security headers on Cloudflare Pages.

## Publish with GitHub and Cloudflare Pages

1. Create a new empty GitHub repository. Do not initialize it with another README or license.
2. From this folder, replace `YOUR_USERNAME` and `YOUR_REPOSITORY` in these commands:

   ```bash
   git init
   git add .
   git commit -m "Add leadership assessment site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
   git push -u origin main
   ```

   Alternatively, upload `index.html`, `_headers`, `.gitignore`, and `README.md` using GitHub's web interface. GitHub's file uploader may hide `.gitignore`; it is optional for hosting.

3. In Cloudflare, create a **Pages** project using **Import an existing Git repository**. Connect the GitHub repository and select `main` as the production branch.
4. Select **None** for framework preset. Use `exit 0` as the build command and `.` as the build output directory. Leave the root directory at the repository root. No environment variables are needed.
5. Deploy. Cloudflare supplies a `pages.dev` URL. Later pushes to `main` deploy updated versions through the Git integration.

For a local preview, run `python3 -m http.server 8000` in this folder and visit `http://localhost:8000/`.

## Operational notes

- Ratings are saved in the visitor's browser using `localStorage`, not in GitHub or Cloudflare. Clearing browser data or changing browsers can remove them. Export CSV if you need a copy.
- The page loads Tailwind CSS, Chart.js, and the Inter font from third-party CDNs, so visitors need access to those services. The print window also loads Tailwind from a CDN.
- This package does not provide logins, shared responses, a database, or centralized reporting.
- The page identifies the Leadership Practices Inventory® and includes assessment content. Check that you have the rights needed before making the repository or deployed site public.
