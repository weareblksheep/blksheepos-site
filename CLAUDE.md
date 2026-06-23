# CLAUDE.md

Guidance for working in this repository.

## Project Architecture

`blksheepos-site` is the **static "coming soon" landing page** for BLKSHEEP OS
(domain: `blksheepos.com`). It is intentionally minimal.

- **Type:** Static site. No framework, no build step, no server-side code.
- **Package manager:** None (no `package.json`, no lockfile, no `node_modules`).
- **Routing:** None — a single page served as `index.html`.
- **Files:**
  - `index.html` — the entire page. Self-contained: markup, inline `<style>`,
    and a tiny inline `<script>` (sets the footer year). No external assets,
    no fonts, no images, no third-party scripts.
  - `robots.txt` — allows all crawlers (`Disallow:` is empty).
  - `README.md` — one-line description.
- **Auth / session layer:** None.
- **API routes:** None.
- **Middleware:** None.
- **Env handling:** None — no secrets, no env vars, no `.env` files.
- **Tests:** None configured.
- **Hosting/deploy:** No deploy config is committed (no `CNAME`, no
  `netlify.toml`, `vercel.json`, or CI workflow). Deployment mechanism is
  external to this repo — confirm with the maintainer before assuming one.

## Local Commands

There is no build or test toolchain. To preview locally, serve the directory
with any static server, e.g.:

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

Or simply open `index.html` in a browser.

## Security Rules

- This is a **public marketing page**. Never add secrets, API keys, tokens, or
  credentials — there is no server and anything committed here is public.
- Keep the page self-contained. Do not add third-party scripts, trackers,
  analytics, or external CDNs without explicit approval; each one is a new
  supply-chain and privacy surface on a page that currently has zero.
- The only outbound link is a `mailto:` to `hello@blksheepos.com`. Validate any
  new links/forms; do not wire up forms that POST user data without a reviewed
  backend.
- If a form or interactivity is added, sanitize/escape any user-rendered input
  to avoid XSS.

## Code Style Rules

- Match the existing style in `index.html`: HTML5 doctype, inline CSS in a
  single `<style>` block, CSS custom properties under `:root`, compact rules.
- 2-space indentation.
- Keep everything in one file unless there is a clear reason to split; if
  assets are added, keep them local to the repo.
- Plain, dependency-free HTML/CSS/JS. No build tooling, no frameworks.

## Forbidden Actions

- Do **not** introduce a framework, bundler, or `node_modules` without explicit
  request — it changes the deploy model entirely.
- Do **not** commit secrets, credentials, or `.env` files.
- Do **not** add tracking/analytics/third-party scripts without approval.
- Do **not** push to `main` — work on the designated feature branch.
- Do **not** open a pull request unless explicitly asked.
- Do **not** change the domain, contact email, or branding copy without
  confirmation.

## Verification Checklist

Before committing changes:

- [ ] `index.html` opens in a browser with no console errors.
- [ ] Page renders correctly at mobile and desktop widths (it is responsive via
      `clamp()` and `min()`).
- [ ] All links/`mailto:` targets are correct.
- [ ] No secrets, keys, or external scripts were added unintentionally.
- [ ] HTML validates (e.g. https://validator.w3.org/) — no unclosed tags.
- [ ] `robots.txt` still reflects intended crawl policy.
- [ ] Changes are on the feature branch, not `main`.
</content>
</invoke>
