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

### DNS setup (registered through Wix, not a typical registrar)

The domain was bought through Wix (auto-renews yearly, currently ~£22.80/yr - manage
that under Billing in the Wix account if it ever needs changing). DNS is *not* set
here or in this repo - it's done in the Wix dashboard:

1. **First**, confirm the domain's contact info via the separate verification email
   Wix sends after purchase - this is an ICANN requirement; the domain can be
   suspended if it's not confirmed within the given window. Do this before anything
   else.
2. In Wix: **Domains -> mdwcwineclub.com -> DNS Records** (may be under "Advanced" /
   "Manage DNS"). Wix often pre-fills records pointing at Wix's own hosting - remove
   or replace those, don't just add alongside them.
3. Add four **A records** for the root (`@`) pointing to:

   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

4. Optional, if you also want `www.mdwcwineclub.com` to work: add a **CNAME record**
   for `www` pointing to `dascpt1.github.io`.

DNS changes can take anywhere from a few minutes to a few hours to propagate. Once it
resolves, GitHub automatically provisions an HTTPS certificate for the domain - no
action needed beyond correct DNS.

## Pages

- `index.html` - public-facing info: about the club, how it works, how to join.
- `schedule.html` - members area: upcoming tastings and general notes. No financial data.
- `tips.html` - members area: serving/storage tips, a running tasting notes log, and
  supermarket recommendations. No financial data.
- `spotlight.html` - members area: this month's featured wines (several at once), plus
  an archive table of past months. See "Monthly spotlight" below for the update process.
- `order.html` - members area: how to place an order, payment (general note only -
  no account details), and where the club orders from.

## Editing

Plain HTML/CSS, no build step - edit the `.html` files and `style.css` directly, then
commit and push. Changes go live within a minute or two of pushing to `master`.

Things to fill in:

- Real schedule rows on `schedule.html` (currently example placeholder rows)
- Real tips, tasting notes and supermarket recommendations on `tips.html`
  (currently example placeholder content)
- Real ordering steps and supplier cards on `order.html`

## Monthly spotlight

`spotlight.html` is manually updated, not automated - each month:

1. Move each of the current month's wine cards into a new row (one row per wine) at
   the top of the "Past spotlights" table (`#archive`), summarizing each in one line.
2. Replace the month heading and the wine cards in `#current` with the new month's
   picks - as many as you like.
3. Commit and push.

## Local preview

Run the `wine-club-site` launch config (serves this folder on `localhost:8080`), or
open the `.html` files directly in a browser.
