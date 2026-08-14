# dascpt1.github.io - Wine Club site

A small, private wine club site. Unlisted (not linked anywhere public, `robots.txt`
and `noindex` meta tags discourage search engines) but not password-protected - anyone
with the exact URL can view it. **Do not add financial data, balances, or per-member
figures to this site** - keep that in your own private spreadsheet/tracking instead.

Served via GitHub Pages at https://dascpt1.github.io/ once pushed.

## Pages

- `index.html` - public-facing info: about the club, how it works, how to join.
- `schedule.html` - members area: upcoming tastings and general notes. No financial data.

## Editing

Plain HTML/CSS, no build step - edit the `.html` files and `style.css` directly, then
commit and push. Changes go live within a minute or two of pushing to `master`.

Things to fill in:

- Club name (currently "Our Wine Club" throughout)
- About section and how-it-works cards on `index.html`
- Contact email (currently `you@example.com`)
- Real schedule rows on `schedule.html` (currently example placeholder rows)

## Local preview

Run the `wine-club-site` launch config (serves this folder on `localhost:8080`), or
open the `.html` files directly in a browser.
