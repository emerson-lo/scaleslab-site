# scaleslab.com — GitHub Pages setup

Plain static site (HTML, CSS, a little JavaScript). No build step.

## 1. Contact form (Formspree)
1. Sign up at https://formspree.io, create a form, and set the notification email (e.g. info@scaleslab.com).
2. Copy the form ID (the part after `formspree.io/f/`).
3. In `index.html`, the form ID is already set (`xoedwyvw`). To change it, edit the form's `action` in index.html.
4. The form posts in the background and redirects to `thanks.html`. If the request fails, it shows a message with the email and phone number. Spam honeypot field: `_gotcha`.

## 2. Publish
1. Create a repository (e.g. `scaleslab-site`) and push the contents of this folder to the root of `main`. Keep `CNAME` and `.nojekyll` (hidden file) in the root.
2. Settings → Pages → Source: "Deploy from a branch", Branch: `main` / `(root)`.
3. Settings → Pages → Custom domain: `www.scaleslab.com` (already in the `CNAME` file). Recommended: verify the domain first (Settings → Pages → Verified domains; adds a TXT record).

## 3. GoDaddy DNS (My Products → scaleslab.com → DNS)
Screenshot the current records first so you can roll back.
- A records for `@` (replace the existing @ A record; four records total): 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- CNAME `www` → `<github-username>.github.io`
- Do NOT change MX / TXT records (email).

After DNS resolves, tick "Enforce HTTPS" in Settings → Pages. scaleslab.com will redirect to www.scaleslab.com.

## 4. Cut over
Test the live site and send a test inquiry, then cancel Cargo.

## Files
- `index.html`: homepage (slideshow, work grid and filters, services, about, contact)
- `<project>.html`: one page per project
- `thanks.html`: shown after the contact form; `404.html`: not-found page
- `images/`: all images (max 2000 px wide)
