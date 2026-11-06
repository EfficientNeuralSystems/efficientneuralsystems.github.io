# Setting up efficientneuralsystems.com on GitHub Pages (Minimal theme)

## 1. Verify the domain for the organisation (recommended, prevents domain takeover)
1. github.com/organizations/EfficientNeuralSystems/settings/pages → **Add a domain** → `efficientneuralsystems.com`.
2. GitHub shows a TXT record (name starting `_github-pages-challenge-EfficientNeuralSystems`). Add it at your domain registrar's DNS settings.
3. Back on GitHub, click **Verify** (may take a few minutes to hours).

## 2. Create the repository
- In the org: **New repository** → name `efficientneuralsystems.github.io` → **Public** → Create.

## 3. Upload these files
- Web: **Add file → Upload files**, drag in the *contents* of this folder (keep the `_layouts`, `_includes`, `_posts`, `assets` folders), commit to `main`.
- Or git:
  ```
  git clone https://github.com/EfficientNeuralSystems/efficientneuralsystems.github.io.git
  cd efficientneuralsystems.github.io
  # copy these files in
  git add . && git commit -m "Initial lab website" && git push
  ```

## 4. Turn on GitHub Pages
- Repo **Settings → Pages**:
  - Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)` → Save.
  - Custom domain: `efficientneuralsystems.com` → Save (the included CNAME file already sets this).

## 5. DNS records at your registrar
Delete any existing A/AAAA/CNAME records for `@` and `www` (including "parking" pages or URL forwarding), then add:

| Type  | Name | Value |
|-------|------|-------|
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |
| AAAA  | @    | 2606:50c0:8000::153 (optional, IPv6) |
| AAAA  | @    | 2606:50c0:8001::153 |
| AAAA  | @    | 2606:50c0:8002::153 |
| AAAA  | @    | 2606:50c0:8003::153 |
| CNAME | www  | efficientneuralsystems.github.io |

## 6. Wait and enable HTTPS
- DNS can take up to 24 h. When Settings → Pages shows "DNS check successful", tick **Enforce HTTPS**.
- Test: https://efficientneuralsystems.com and https://www.efficientneuralsystems.com

## 7. Day-to-day editing
- Pages: edit `index.md`, `research.md`, `people.md`, `publications.md`.
- Menu: edit `navigation:` in `_config.yml`.
- News item / blog post: add `_posts/YYYY-MM-DD-short-title.md` with front matter
  ```
  ---
  layout: post
  title: "Title"
  categories: news      # or: blog
  ---
  ```
- Logo: put an image at `assets/img/logo.png` and uncomment `logo:` in `_config.yml`.
- Notebook posts: `jupyter nbconvert --to markdown notebook.ipynb`, add the front matter above, move the `.md` into `_posts/` and the generated image folder next to it (fix image paths if needed).
- Each commit to `main` rebuilds the site in ~1 minute (see the repo's **Actions** tab for build status/errors).
