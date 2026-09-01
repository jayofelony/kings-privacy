# Kings — public site (home page + privacy policy + terms)

These static pages exist to satisfy Google's OAuth / Play Games verification, which
requires a **publicly reachable home page on a domain you can verify**, that explains
the app and links to a privacy policy. A `raw.githubusercontent.com` URL does not
qualify.

## Files

| File | Purpose |
|---|---|
| `index.html` | Home page — explains what Kings is (Google: "outline the purpose") |
| `privacy-policy.html` | Privacy Policy |
| `terms-of-service.html` | Terms of Service |
| `style.css` | Shared styling |
| `assets/icon.png`, `assets/feature.png` | Images |

**Before publishing:** replace every `CONTACT@EXAMPLE.COM` with a real support address.

## Deploy on GitHub Pages (free, works with your public `kings-privacy` repo)

1. Copy the contents of this `site/` folder into the **root** of the
   `github.com/jayofelony/kings-privacy` repo and push to `main`.
2. In that repo: **Settings → Pages → Build and deployment → Source: "Deploy from a
   branch" → Branch: `main` / `(root)` → Save.**
3. After ~1 minute the site is live at
   **`https://jayofelony.github.io/kings-privacy/`**

## Verify ownership in Google Search Console

1. <https://search.google.com/search-console> → **Add property → URL prefix** →
   `https://jayofelony.github.io/kings-privacy/`
2. Choose the **HTML file** method: download `google<...>.html`, put it in the repo
   root, push, then click **Verify**.
   *(Or: add the `<meta name="google-site-verification" ...>` tag Google gives you into
   the `<head>` of `index.html`.)*

## Update the OAuth consent screen (Google Auth Platform → Branding / Audience)

| Field | Value |
|---|---|
| App name | `Kings` |
| App home page | `https://jayofelony.github.io/kings-privacy/` |
| Privacy policy link | `https://jayofelony.github.io/kings-privacy/privacy-policy.html` |
| Terms of service link | `https://jayofelony.github.io/kings-privacy/terms-of-service.html` |
| Authorized domain | `jayofelony.github.io` |
| Developer contact / support email | your address |

Then re-submit for verification. This resolves all five findings:
unresponsive → live; not registered to you → Search Console verified; behind login →
Pages is public; purpose not explained → `index.html`; name mismatch → the page is
titled "Kings".

If Google rejects `jayofelony.github.io` as an authorized domain, the fallback is a
domain you register yourself (e.g. an `xbitsnl.nl` subpath) and verify the same way.
