# Deployment

Status of the deploy path for the BLKSHEEP OS coming-soon page.

## Current state

**The hosting / deploy path is TBD and unconfirmed.** No deploy
configuration is committed to this repository:

- No `CNAME` file (no custom-domain binding in source control).
- No `netlify.toml`, `vercel.json`, or other host config.
- No CI/CD workflow (no `.github/workflows/`).
- No `package.json` or build step — the site is static and served as-is.

Because none of these exist, the deployment mechanism is external to this
repo and has **not been verified from repository evidence**. Confirm the
actual host with the maintainer before changing anything that depends on it
(for example, adding a `CNAME` or a domain binding).

## GitHub Pages (plausible, not proven)

The repository lives under a GitHub organization, so GitHub Pages is a
**plausible** host. This is not proven by anything in the repo — there is no
`CNAME`, no Pages workflow, and no other committed signal that Pages is in
use.

If GitHub Pages is later confirmed as the host:

- The custom domain `blksheepos.com` would typically require a `CNAME` file
  at the repo root containing the domain.
- A `CNAME` has **not** been added here, to avoid binding or breaking a
  domain on an unconfirmed host.

## Local preview

There is no build or test toolchain. To preview locally, serve the
directory with any static server:

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

Or simply open `index.html` in a browser.
