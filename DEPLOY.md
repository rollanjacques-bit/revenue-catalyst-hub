Cloudflare Pages deploy instructions

This adds a GitHub Actions workflow that deploys the repository root to Cloudflare Pages using the official pages-action.

Required repository secrets (Settings → Secrets and variables → Actions):

CLOUDFLARE_API_TOKEN — Cloudflare API Token with Pages:Edit and Account:Read permissions.
CLOUDFLARE_ACCOUNT_ID — your Cloudflare account ID (from Cloudflare dashboard).
CLOUDFLARE_PROJECT_NAME — the Pages project name in Cloudflare.

Notes:

The workflow currently publishes the repository root (directory: ./). If your site build output is in a subfolder (e.g., public or dist), update the 'directory' value in .github/workflows/deploy-cloudflare-pages.yml or add a build step before the publish step.
The workflow triggers on pushes to main and can be run manually via the Actions tab (workflow_dispatch).

How to create a Cloudflare API token:

Go to Cloudflare dashboard → My Profile → API Tokens → Create Token.
Use the "Edit Cloudflare Pages" template or set minimal permissions:
Account: Read
Pages: Edit (or Pages: Edit + Pages: Deploy)
Copy the generated token and save it to the GitHub secret CLOUDFLARE_API_TOKEN.

How to find account ID:

Cloudflare dashboard → Overview → Account Home shows the Account ID.

How to find/create Pages project name:

In Cloudflare Pages console, the project appears with a name (use that exact name for CLOUDFLARE_PROJECT_NAME). If you haven't created a Pages project, create one first and note the project name.

When you finish and open the PR, send me the PR URL and I will review immediately.

Thanks,
