# Örvar Smárason

A small author website. Plain HTML, no build step, hosted on GitHub Pages.

- `index.html` is the site. It reads everything it shows from `content.json`.
- `content.json` holds the text: name, about, books, extra texts, email.
- `images/` holds the pictures.
- `admin/` is the editor. Open `/admin/` on the live site.

## Editing the site

Open `/admin/` on the live site and sign in with a GitHub fine-grained token
that has **Contents: Read and write** on this repository. The page explains how
to make one. Saving writes `content.json` (and any uploaded pictures) straight
to this repository, and the site updates about a minute later.

The token lives only in that browser. Nothing secret is stored in this repository.

## Moving the site to another GitHub account

1. In this repository: Settings → General → Danger Zone → Transfer ownership.
2. In the new account: Settings → Pages → deploy from the `main` branch, `/ (root)`.
3. The new owner makes their own token for `/admin/`.

The admin page reads the account and repository name from the site address, so
nothing in the code needs to change. With a custom domain, type the account and
repository into the sign-in form once.

## Running it locally

```bash
python3 -m http.server 8791
```
