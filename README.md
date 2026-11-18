# lasterminator.github.io

The home of my games: a hub page and one page per game. Plain HTML and one stylesheet, served by
GitHub Pages straight from `main`. There is no build step: what is in the repo is what is live.

Both games' store listings use `https://lasterminator.github.io/` as their marketing address, and
AdMob reads `app-ads.txt` from it, so the home page and that file must stay where they are.

## Layout

```
index.html                    the hub: one coloured tile per game
infinite-labyrinth/index.html the Infinite Labyrinth page
lantern-city/index.html       the Lantern City page
apps/index.html               old address, forwards to the hub
404.html                      shown for any address that does not exist
assets/site.css               the only stylesheet
assets/<game>/                icon.png and screenshots 1.jpg to 6.jpg
assets/fonts/                 the two typefaces, hosted here
app-ads.txt                   AdMob seller record. Do not move or rename.
google32c630a72dc2803f.html   Google Search Console ownership. Do not move or rename.
```

Privacy policies, terms and support pages live in the separate `Privacy-Policy` repo.

## Changing things

| To change | Do this |
|---|---|
| Text on a page | Edit that page's HTML |
| A game's colour | The `[data-game='…']` block near the top of `assets/site.css` |
| A screenshot or icon | Replace the file in `assets/<game>/`, keeping its name |
| Colours and type for the whole site | The variables at the top of `assets/site.css` |

## Adding a game

1. Make `assets/<game>/` with `icon.png` (256 px square) and screenshots `1.jpg` to `6.jpg`.
2. Add a `[data-game='<game>']` block to `assets/site.css` with its two colours.
3. Copy `lantern-city/` to `<game>/` and edit the text, links and the App Store id in the
   `apple-itunes-app` tag.
4. Copy one `<article class="tile">` on the hub page and point it at the new page.

## Previewing

Open the folder with any static file server, for example:

```bash
npx serve .
```

Paths start with `/`, so opening the HTML files directly from disk will not find the stylesheet.

## Publishing

Pushing to `main` publishes the site within a minute or two.
