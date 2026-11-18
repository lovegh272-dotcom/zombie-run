ZOMBIE RUN v19 (on top of v18, code unchanged except sw.js cache)

- img/z_necromancer.png: 1254 -> 384 px.
- img/maps/map_*.png: 1254 -> 768 px (the game draws the floor as a 512 px tiling pattern, so no visible loss).
- Total img/ about 18 MB -> a few MB: faster first load, less memory spike on iPhone at start.
- sw.js cache zrun-v19. Keep your original 1254 px files elsewhere if you need them.

TESTED: headless Chromium loads all maps/sprites, no page errors.
NOT TESTED: real iPhone/Safari, visual check of every map on device.
