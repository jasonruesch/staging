# staging.jasonruesch.dev

Staging host for jasonruesch.dev's sites, on GitHub Pages like production.
This repo owns the custom domain `staging.jasonruesch.dev`; each site is
published under the same path it has in production.

| Site | Staging | Production | Source |
|---|---|---|---|
| Pinochle | https://staging.jasonruesch.dev/pinochle/ | https://jasonruesch.dev/pinochle/ | [jasonruesch/pinochle](https://github.com/jasonruesch/pinochle) |

## Deploying

Actions → **Deploy staging** → **Run workflow**, and enter the branch (or tag or
SHA) of `jasonruesch/pinochle` to publish. Deploys are manual only.

The workflow builds the site exactly as production does (base `/pinochle/`),
then marks it as staging: `noindex` on every page, no `sitemap.xml`, and a
full-width "Staging" bar pinned above the site header. Canonical links still point at production. `root/`
holds the host root: a redirect to `/pinochle/` and a `robots.txt` that
disallows everything.

## DNS

`staging` is a CNAME to `jasonruesch.dev` (GitHub's Pages check wants the
account's user-site domain, since `jasonruesch.github.io` uses that custom
domain), and the domain is verified in
the account's Pages settings (a `_github-pages-challenge-jasonruesch.staging`
TXT record).
