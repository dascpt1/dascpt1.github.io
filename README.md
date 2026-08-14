# dascpt1.github.io - Wine Club site

A small, private wine club site. Unlisted (not linked anywhere public, `robots.txt`
and `noindex` meta tags discourage search engines) but not password-protected - anyone
with the exact URL can view it. **Do not add financial data, balances, or per-member
figures to this site** - keep that in your own private spreadsheet/tracking instead.

Served via GitHub Pages, once pushed - custom domain **mdwcwineclub.com** (via the
`CNAME` file), falls back to https://dascpt1.github.io/ if DNS isn't set up yet.
Custom domain note: a memorable domain name is easier to guess/share than a random
github.io URL, so it's slightly less obscure than before - still fine given "unlisted,
not password-protected" was the accepted tradeoff, just worth knowing.

### DNS setup (do this at your domain registrar, not here)

For the apex domain to work, add four **A records** for `mdwcwineclub.com` pointing to:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Optional, if you also want `www.mdwcwineclub.com` to work: add a **CNAME record** for
`www` pointing to `dascpt1.github.io`.

DNS changes can take anywhere from a few minutes to a few hours to propagate. Once it
resolves, GitHub automatically provisions an HTTPS certificate for the domain - no
action needed beyond correct DNS.

## Pages

- `index.html` - public-facing info: about the club, how it works, how to join.
- `schedule.html` - members area: upcoming tastings and general notes. No financial data.
- `tips.html` - members area: serving/storage tips, a running tasting notes log, and
  supermarket recommendations. No financial data.
- `spotlight.html` - members area: this week's featured grape/region/variety, plus an
  archive table of past weeks. See "Weekly spotlight" below for the update process.
- `order.html` - members area: how to place an order, payment (general note only -
  no account details), and where the club orders from.

## Editing

Plain HTML/CSS, no build step - edit the `.html` files and `style.css` directly, then
commit and push. Changes go live within a minute or two of pushing to `master`.

Things to fill in:

- About section and how-it-works cards on `index.html`
- Real schedule rows on `schedule.html` (currently example placeholder rows)
- Real tips, tasting notes and supermarket recommendations on `tips.html`
  (currently example placeholder content)
- Real ordering steps and supplier cards on `order.html`
- This week's first real entry on `spotlight.html`

## Weekly spotlight

`spotlight.html` is manually updated, not automated - each week:

1. Move the current "This week" block's summary into a new row at the top of the
   "Past spotlights" table (`#archive`).
2. Replace the "This week" heading, week-of date, and body text with the new
   grape/region/variety.
3. Commit and push.

## Local preview

Run the `wine-club-site` launch config (serves this folder on `localhost:8080`), or
open the `.html` files directly in a browser.
