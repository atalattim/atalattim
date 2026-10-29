# Install the atalattim profile pack

## 1. Copy the pack into the profile repository

Open <https://github.com/atalattim/atalattim> and upload/commit these files while preserving the folder structure:

- `README.md`
- `assets/profile-banner.svg`
- `github-metrics.svg`
- `.github/workflows/update-metrics.yml`

Do not upload only `README.md`: the banner and metrics image are local assets referenced by relative paths.

## 2. Run the live metrics workflow

1. Open the repository's **Actions** tab.
2. Select **Update profile metrics**.
3. Choose **Run workflow** on the `main` branch.
4. Wait for the run to finish and check that it commits an updated `github-metrics.svg`.

The workflow uses the repository-provided `GITHUB_TOKEN`; no personal token or external secret is needed. The workflow requests `contents: write`. If GitHub blocks the commit, open **Settings → Actions → General → Workflow permissions** and allow read/write permissions for the workflow token.

It also refreshes on a daily schedule. The public profile README uses GitHub-compatible Markdown and HTML; it does not run arbitrary JavaScript, so its interactions are links and externally rendered images rather than a custom app.
