# turfstorm-website

Static marketing and support site for Turfstorm, served at turfstorm.com.

Served from the repo root. No build step, no dependencies, no JavaScript.

| Path | Why it exists |
|---|---|
| `index.html` | Landing page |
| `privacy.html` | Required by App Store Connect before an app can be submitted |
| `support.html` | Also required, and the support URL on the product page |
| `app-ads.txt` | Must sit at the domain root. Intentionally empty of seller lines until real ad network dashboards exist; a wrong line authorises a seller we do not use |
| `style.css` | Shared styles, matching the app's broadcast-telestrator direction |
| `CNAME` | Custom domain for GitHub Pages |

## Deploying

GitHub Pages, served from `main` at the repo root. `CNAME` holds the custom domain and
`.nojekyll` stops Jekyll from processing the files.

DNS at Namecheap must point turfstorm.com here:

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | therealcreynold.github.io. |

`app-ads.txt` must be reachable at exactly `https://turfstorm.com/app-ads.txt`, not under a
subdirectory. Verify after DNS propagates.

## Rules for this repo

This repo is **public**. Nothing from the game repo's `research/` directory belongs here.

Nothing on this site may name a real league, club, player or competing product. The game
repo's `tools/presubmission-gates.sh` greps store metadata for those terms; this site is
reviewed by hand for the same thing.
