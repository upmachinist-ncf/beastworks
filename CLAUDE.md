# Beastworks
Single-file PWA. All game code is in index.html — no build step.

## Every deploy
Bump `const CACHE = 'beastworks-vN'` in sw.js before pushing.
Installed clients serve the cached copy forever otherwise.
