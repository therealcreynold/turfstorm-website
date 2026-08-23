# turfstorm-website

Static marketing and support site for Turfstorm, served at turfstorm.com.

Everything is in `public/`. No build step, no dependencies, no JavaScript.

| Path | Why it exists |
|---|---|
| `index.html` | Landing page |
| `privacy.html` | Required by App Store Connect before an app can be submitted |
| `support.html` | Also required, and the support URL on the product page |
| `app-ads.txt` | Must sit at the domain root. Intentionally empty of seller lines until real ad network dashboards exist; a wrong line authorises a seller we do not use |
| `style.css` | Shared styles, matching the app's broadcast-telestrator direction |

## Deploying

Point turfstorm.com (registered at Namecheap) at a static host and serve `public/` as the
root. Cloudflare Pages is the obvious fit. `app-ads.txt` must be reachable at
`https://turfstorm.com/app-ads.txt` exactly, not under a subdirectory.

## Rules for this repo

This repo is **public**. Nothing from the game repo's `research/` directory belongs here.

Nothing on this site may name a real league, club, player or competing product. The game
repo's `tools/presubmission-gates.sh` greps store metadata for those terms; this site is
reviewed by hand for the same thing.
