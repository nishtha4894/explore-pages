# pages-demo-private

A minimal private GitHub Pages demo repository for learning the Pages product end-to-end.

## What this repo demonstrates

- GitHub Actions-based Pages deployment
- Static site artifact packaging and deployment
- Required Pages permissions (`pages: write`, `id-token: write`)
- Typical build and deploy job split

## Repo structure

- `.github/workflows/pages.yml`: Pages deployment workflow
- `site/index.html`: Demo page content
- `site/styles.css`: Small styling file

## Prerequisites

- You can create private repositories in your org/account
- GitHub Pages is enabled for private repositories in your environment
- You have permissions to edit repository settings and Actions

## Setup steps

1. Create a new private repository in GitHub (for example: `pages-demo-private`).
2. Copy this folder contents into that repository.
3. Push to the `main` branch.
4. In repository settings:
   - Go to **Pages**
   - Set **Build and deployment** source to **GitHub Actions**
5. Open **Actions** and run the `Deploy private demo Pages site` workflow (or push a commit).
6. After deploy succeeds, open the environment URL shown in the deploy job output.

## Optional: create and push via GitHub CLI

Run these from this folder if `gh` is installed and authenticated:

```powershell
git init
git add .
git commit -m "Initial private Pages demo"
git branch -M main
gh repo create pages-demo-private --private --source . --remote origin --push
```

## Troubleshooting

- Deployment permission errors:
  - Check workflow has `pages: write` and `id-token: write`.
- No Pages URL after successful workflow:
  - Confirm repository Pages source is set to **GitHub Actions**.
- 404 right after first deploy:
  - Wait a minute for initial propagation and retry.

## Next experiments

- Add a custom domain and test DNS flow
- Add a Jekyll workflow path (`actions/jekyll-build-pages`)
- Add preview deployment experiments (if enabled in your environment)
