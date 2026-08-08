# BTN Sideways

BTN Sideways is a paired CSS theme and Tampermonkey userscript bundle for
BroadcastTheNet. The CSS handles the site-wide visual restyle, while the
userscript adds the interactive pieces and external metadata panels.

Install both files together for the intended result:

- `BroadcastThatNet.css`
- `BTN All-In-One.user.js`

The userscript will run on its own, but the layout and styling are designed to
sit on top of the CSS. Likewise, the CSS looks best with the userscript-created
panels and controls present.

## What It Adds

The userscript merges eleven BTN helpers into one install. Each module still
only runs on the pages it needs, and a failed module is caught so the rest of
the script can continue.

- Animated BTN power logo on all pages.
- Front page tidy-up with unread/collapse handling for the main news post.
- TMDB trending shows on the front page.
- Show/hide toggle for the torrents search table.
- Series page declutter, including a rebuilt Series Info panel.
- One-line torrent details for easier scanning.
- Fanart.tv ClearLogo support.
- TMDB recommended shows.
- IMDb Parents Guide panel with collapsed card layout.
- Sonarr integration with multi-server support.
- TMDB Enricher with hero banner, extra metadata pills, trailer link, review
  snippet, keywords, and YouTube embed fixes.

The CSS provides the dark BTN Sideways look, dashboard-style spacing, cleaner
tables, refreshed icons, better series-page layout, forum lightbox fixes, and
the styling for the userscript panels.

## Install

### 1. Install The CSS

Install `BroadcastThatNet.css` as a user style for BTN.

Recommended match patterns:

```text
https://broadcasthe.net/*
https://*.broadcasthe.net/*
```

Stylus or another browser userstyle manager should work. If you already use a
custom BTN stylesheet slot, you can paste the CSS there instead.

### 2. Install The Userscript

Install `BTN All-In-One.user.js` in Tampermonkey, Violentmonkey, or another
compatible userscript manager.

After installing this merged script, disable any older individual BTN scripts
that duplicate these features. Leaving the originals enabled can create double
panels, duplicate buttons, or conflicting layout changes.

### 3. Add Your TMDB API Key

No TMDB API key is stored in the script. Add your own key through the
Tampermonkey menu:

1. Open any BTN page where the userscript is active, preferably a series page.
2. Click the Tampermonkey extension icon.
3. Open the menu for `BTN All-In-One`.
4. Choose `Set TMDB API key (v3)`.
5. Paste your TMDB v3 API key and confirm.
6. Reload the BTN page.

A TMDB v4 bearer token can also be set from the same menu if you prefer that.
If both are set, the bearer token is used first.

TMDB is used by the Trending Shows, Recommended Shows, and TMDB Enricher
modules. Those modules skip themselves if no TMDB key is set.

### 4. Optional: Configure Sonarr

On a BTN series page, click the `[Sonarr]` action link and add your Sonarr
server URL and API key. Multiple servers are supported.

## Tweaking

The userscript is split into numbered modules. The two most useful places to
edit are:

- `CONFIG` in `Series Page Declutter`, for showing or hiding series-page panels.
- `SHOW` in `TMDB Enricher`, for enabling optional TMDB sections such as cast,
  seasons, artwork, providers, or trailer behavior.

Change a value, save the userscript, and reload BTN.

## Notes

Userscript-manager storage is per script. If you are moving from separate
scripts to this merged one, enter your TMDB and Sonarr settings again once.
Browser `localStorage` settings, such as front-page read state and search-table
visibility, should remain untouched.

## Credits

Original work by Prism16 and the BTN userscript/style authors this bundle was
merged from. BTN Sideways packages the CSS and all-in-one userscript together
for easier installation and testing.
