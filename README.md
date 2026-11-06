# Beastworks

A virtual-pet game. Creatures are generated from mixed-up parts, every name is
used once and then retired, and there are nine mini-games with three difficulty
levels behind the care loop.

Built with Claude. Single-page app, no build step, no dependencies.

## Layout

```
index.html              the entire game (HTML + CSS + JS in one file)
manifest.webmanifest    PWA manifest
sw.js                   service worker — offline cache
icon-192.png            app icons
icon-512.png
icon-512-maskable.png
```

## Running locally

```sh
python3 -m http.server 8777
# http://localhost:8777
```

A service worker needs an origin, so `file://` won't register one. Everything
else works either way.

## Deploying

Static hosting, nothing to build.

**Cloudflare Pages** — Workers & Pages → Create → Pages → Upload assets, drag
the six files in.

**GitHub Pages** — push, then Settings → Pages → Branch `main`, folder `/`.

## IMPORTANT: bump the cache on every deploy

`sw.js` line 3:

```js
const CACHE = 'beastworks-v1';
```

Increment it (`v2`, `v3`, …) **every time `index.html` changes**. Skip this and
installed clients keep serving the cached copy and never see the update.

## Save data

- `localStorage` holds the live game state per browser.
- **Backup codes** (`BW1-…`) are base64 of the whole save; they work offline and
  are the only transfer method in this standalone build.
- **Short codes** (`tocagoats1015`) are stored server-side and only work in the
  Claude-hosted version, which has the `db` capability. This build detects the
  absence and says so.

## Notes

- Meters only advance while the page is open; closed time is ignored by design.
- Google Fonts is the one external request. It fails gracefully to system fonts
  and the service worker caches it after first load.
