ZOMBIE RUN v18 (on top of v16/v17, only these changes)

1. Gun always faces the aim direction (not only while firing). Auto mode = nearest zombie in range, no target = movement direction. Manual mode = AIM direction. Smooth turn.
2. Sniper BLAST (charge skill): aim-assist removed (drag-to-aim, hold mode, laser line, settings card). The button still works: press -> charge ~1.5 s (ring shown) -> beam fires where the gun is facing.
3. Menus: re-rendering the same page (select / buy / toggle) keeps the scroll position. Changing page goes back to top.
sw.js cache zrun-v18. Replace index.html + sw.js only (img/ untouched).

TESTED: node --check, headless Chromium: scroll kept on toggle, aim matches nearest zombie, sniper charge->fire, no page errors.
NOT TESTED: real iPhone/Safari.
