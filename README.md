# turfstorm-website

Static marketing and support site for Turfstorm, served at turfstorm.com.

Served from the repo root. No build step, no dependencies, no JavaScript.

| Path | Why it exists |
|---|---|
| `index.html` | Landing page |
| `privacy.html` | Required by App Store Connect before an app can be submitted |
| `support.html` | Also required, and the support URL on the product page |
| `app-ads.txt` | Must sit at the domain root. Holds `OWNERDOMAIN=turfstorm.com` and Google's real DIRECT line, copied from the AdMob dashboard rather than typed. AdMob is the only network in the build, so it is the only line here; a wrong line authorises a seller we do not use |
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
subdirectory, as `text/plain`, HTTP 200, with no redirect. Verify after DNS propagates.

Google's crawl walks from the App Store listing's marketing URL to this domain, so it cannot
succeed until the listing is live. Expect the store link to appear, then the crawl, then
Google's app readiness review: a week or more of barely filling after launch is the system
working rather than a fault.

## Rules for this repo

This repo is **public**. Nothing from the game repo's `research/` directory belongs here.

Nothing on this site may name a real league, club, player or competing product. The game
repo's `tools/presubmission-gates.sh` greps store metadata for those terms; this site is
reviewed by hand for the same thing.
