# Hosting & Domain Setup

This site is hosted on **GitHub Pages** (free) with a custom domain managed through **Squarespace Domains**.

## Architecture

```
Squarespace Domains (DNS)  →  GitHub Pages (hosting)  →  Astro (static build)
     derekarcher.com            jtbricker.github.io         HTML/CSS/JS files
```

- **Hosting**: GitHub Pages (free tier — 1 GB storage, 100 GB bandwidth/month)
- **SSL/HTTPS**: Automatically provisioned by GitHub via Let's Encrypt
- **Build & Deploy**: GitHub Actions on every push to `main` (see `.github/workflows/deploy.yml`)
- **Domain Registrar**: Squarespace Domains

## DNS Configuration (Squarespace)

These records are configured in **Squarespace Domains → DNS Settings → Custom Records**:

### CNAME Record (www subdomain)

| Host | Type  | TTL  | Data                    |
|------|-------|------|-------------------------|
| www  | CNAME | 1 hr | `jtbricker.github.io.`  |

### A Records (apex domain)

| Host | Type | TTL  | Data              |
|------|------|------|-------------------|
| @    | A    | 1 hr | `185.199.108.153` |
| @    | A    | 1 hr | `185.199.109.153` |
| @    | A    | 1 hr | `185.199.110.153` |
| @    | A    | 1 hr | `185.199.111.153` |

The `@` records handle `derekarcher.com` (no www). The CNAME handles `www.derekarcher.com`. Both resolve to GitHub Pages.

## GitHub Pages Configuration

1. **Repository**: Must be public (GitHub Pages requires public repos on the free plan)
2. **Settings → Pages → Source**: GitHub Actions
3. **Settings → Pages → Custom domain**: `www.derekarcher.com`
4. **Enforce HTTPS**: Enabled (available after DNS verification passes)

## Deployment Pipeline

The file `.github/workflows/deploy.yml` handles deployment:

1. Triggered on push to `main`
2. Installs dependencies and builds the Astro site (`npm run build`)
3. Deploys the built `dist/` folder to GitHub Pages via `actions/deploy-pages@v4`

The custom domain is set via `public/CNAME` (contains `www.derekarcher.com`).

## Why GitHub Pages?

Since Astro generates a **static site** (just HTML, CSS, and JS files), there's no need for server-side compute. All interactive components (3D brain viewer, citation charts, network graph) run client-side in the visitor's browser. This means:

- No cloud computing costs (AWS, GCP, etc.)
- No server maintenance
- Free hosting with GitHub Pages is more than sufficient

## Troubleshooting

- **DNS check failing**: DNS propagation can take up to 1 hour after adding records. Click "Check again" in GitHub Pages settings.
- **HTTPS unavailable**: This becomes available only after DNS verification passes. Wait for DNS propagation.
- **Site not updating**: Check the Actions tab in GitHub for build errors. Run `npm run build` locally to debug.
- **GitHub's Pages IPs change**: Check [GitHub's official docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) for current IP addresses.
