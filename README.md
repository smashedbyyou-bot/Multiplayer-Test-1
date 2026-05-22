# FPS Shooter Web Deployment

This repo is prepared for Cloudflare Pages deployment.

## What is included
- `index.html` — root entry point for the web game
- `fps-shooter.js` — Godot engine shell script
- `fps-shooter.wasm` — WebAssembly runtime
- `fps-shooter.pck` — exported game data
- `fps-shooter.icon.png` and `fps-shooter.apple-touch-icon.png`

## Cloudflare Pages setup

### Option 1: Deploy using the Cloudflare Pages dashboard
1. Push this repository to GitHub.
2. In Cloudflare Pages, create a new site and connect your GitHub repo.
3. For "Build command" leave it blank.
4. Set "Build output directory" to `/`.
5. Set "Root directory" to `/` if prompted.
6. Deploy.

### Option 2: Deploy using GitHub Actions
1. Add the following repository secrets in GitHub:
   - `CLOUDFLARE_API_TOKEN`
   - `CLOUDFLARE_ACCOUNT_ID`
   - `CLOUDFLARE_PROJECT_NAME`
2. Push the repo with the workflow file in `.github/workflows/cloudflare-pages.yml`.
3. On every push to `main`, GitHub Actions will deploy the site.

## Notes
- `index.html` is required by Cloudflare Pages as the default entry point.
- Filenames were changed to `fps-shooter.*` to avoid URL encoding issues with spaces.
- If the page still fails to load, open the browser console and look for missing file or `.wasm` errors.
- If you want, I can also help you create the Cloudflare Pages project and set secrets in the browser with exact steps.
