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

Last verified: 2026-11-02
