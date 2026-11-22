# OpenWrt 配置修改器

A static web tool that checks an OpenWrt backup's config files and parameters
against source-verified rules. Bilingual (English-first, Chinese), Argon dark.

- Upload a backup (`backup-*.tar.gz`) in the browser; every file is parsed
  locally — nothing is uploaded anywhere.
- Each parameter is checked against the real source (LuCI / netifd / hostapd /
  UCI schema), never guessed. Uncertain parameters are flagged, not invented.
- One parameter lives in exactly one place; no duplicates.

## Deploy

Hosted on Cloudflare Pages, imported from this repository. No build step:
`index.html` is the whole site. Every push to `main` redeploys automatically.

## Update flow

The source of truth is the tool inside Muse. After an edit there:

1. Export the page to a single HTML file.
2. Replace `index.html` in this repo and push.
3. Cloudflare Pages deploys the new version automatically.
