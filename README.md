# Örvar Smárason

A small author website. Plain HTML, no build step, hosted on GitHub Pages.

- `index.html` is the site. It reads everything it shows from `content.json`.
- `content.json` holds the text: name, about, books, extra texts, email.
- `images/` holds the pictures.
- `admin/` is the editor. Open `/admin/` on the live site.

## Editing the site

Open `/admin/` on the live site and sign in with the password.

The first time, the page asks for a one-off setup: a GitHub fine-grained token
with **Contents: Read and write** on this repository only, plus the password to
use from then on. The page explains how to make the token. The token is stored
in `admin/key.json`, encrypted with the password; the password itself is not
stored anywhere. Anyone can read `admin/key.json`, so the password is what
protects the site: keep it long and private.

Saving writes `content.json` (and any uploaded pictures) straight to this
repository, and the site updates about a minute later. When the token expires,
make a new one and run the setup again from the sign-in page.

## Moving the site to another GitHub account

1. In this repository: Settings → General → Danger Zone → Transfer ownership.
2. In the new account: Settings → Pages → deploy from the `main` branch, `/ (root)`.
3. The new owner opens `/admin/`, chooses "Set up again with a new GitHub token", and uses a token from their own account.

The admin page reads the account and repository name from the site address, so
nothing in the code needs to change. With a custom domain, type the account and
repository into the sign-in form once.

## Running it locally

```bash
python3 -m http.server 8791
```
