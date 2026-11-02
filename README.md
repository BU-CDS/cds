# cds.bu.edu

Sends visitors of `cds.bu.edu` to <https://www.bu.edu/cds-faculty/>. Hosted on GitHub Pages from
this repo, so CDS owns the hosting.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Redirects the home page (meta refresh + `location.replace`, with a fallback link) |
| `404.html` | Same redirect, so `cds.bu.edu/anything` also lands on bu.edu/cds-faculty |
| `_config.yml` | Keeps README, CHANGELOG and the default theme off the published site |
| `CNAME` | Not present yet. GitHub adds it when the custom domain is set (step 3 below) |

This is a client-side redirect, not a server 301. That is fine for a vanity URL. To put real content
here later, replace `index.html` and `404.html`.

## Hosting

Settings → Pages → Deploy from branch `main`, folder `/ (root)`. Test address:
<https://bu-cds.github.io/cds/>.

## Switching cds.bu.edu over

Keep the custom domain empty until DNS resolves; setting it early sends the github.io address to
the dead `cds.bu.edu`.

1. Org settings → Pages → Add a verified domain → `cds.bu.edu`. Note the TXT record GitHub shows.
2. IS&T DNS ticket: `CNAME cds.bu.edu → bu-cds.github.io`, plus that TXT record (it stops other
   GitHub accounts from claiming the name).
3. Once DNS resolves: repo Settings → Pages → Custom domain = `cds.bu.edu`. GitHub gets a Let's
   Encrypt certificate (bu.edu's CAA record allows `letsencrypt.org`).
4. Tick "Enforce HTTPS", then test `https://cds.bu.edu` and `http://cds.bu.edu`.

Last verified: 2026-11-02
