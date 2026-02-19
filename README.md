# Futur4IsHere Mobile AI Academy

Ground-up rebuild of the mobile-first academy page.

## What works

- Premium mobile-friendly UI with clear "V4 Rebuild Active" marker.
- Module progression with in-depth Module 1 lesson + Module 1 check, then final auto-graded quiz (pass threshold: 3/4).
- Starter prompt unlocks only after passing the Module 1 check.
- Live preview lab remains locked until the final test is passed.
- Copy prompt and HTML preview tools unlock automatically after pass.
- **No localhost or backend server required** (single static HTML file).

## Run (No localhost required)

1. Download or clone the repo.
2. Open `index.html` directly in your browser (or mobile file browser).
3. If deploying to GitHub Pages, upload as-is; no server code needed.

## Deploy to GitHub

- Commit `index.html` and `README.md`.
- Push to GitHub.
- Optional: enable GitHub Pages to host the static file.

## Automatic PR Preview Deployments (Vercel)

This repo is now configured for automatic Vercel preview deployments on every pull request via GitHub Actions.

### Files added

- `.github/workflows/vercel-preview.yml`
- `vercel.json`

### One-time setup required in GitHub

Add these repository secrets (Settings → Secrets and variables → Actions):

- `VERCEL_TOKEN` (from Vercel account token)
- `VERCEL_PROJECT_ID` (project id from Vercel project settings)

`VERCEL_ORG_ID` and `VERCEL_SCOPE_ID` are already wired in the workflow file.

> Note: `vercel pull` writes `.vercel/project.json` using those IDs during CI; no local server is required.


### Integrated Vercel values

The workflow is now preconfigured with:

- `VERCEL_ORG_ID = pri_MX3VOXUoHB8MYPuV7yFWg0xXLwoL`
- `VERCEL_SCOPE_ID = team_KNQkAsVXMrmHLG6ob6CIbSUA`

For security, the token is **not** hardcoded in the repo.

Set this GitHub secret:

- `VERCEL_TOKEN` = your provided token

Also set:

- `VERCEL_PROJECT_ID` = your Vercel project id

### Result

Every future PR (including Codex PRs) will:

1. Build a Vercel preview deployment.
2. Deploy it automatically.
3. Post the live preview URL as a PR comment.
