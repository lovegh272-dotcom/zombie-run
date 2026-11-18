ZOMBIE RUN v16 - WALK ANIMATION "ทาง 1" (on top of v15, gameplay unchanged)

- Player: while moving, the existing sprite hops (up to ~3.4 px), sways (~4 deg) and squashes/stretches slightly
  in step with the stride (P.wk). The shadow shrinks at the top of each hop. Strength P.wm eases in/out (~0.1 s),
  so stopping settles smoothly. Idle = no change.
- Zombies: gentle sway (+-5 deg, bosses +-1.7 deg) driven by existing z.ph, on top of the old size pulse.
- Pure math on existing transforms: no extra draw calls, no new allocations.
- sw.js cache zrun-v16. Older READMEs kept.

TESTED: JS syntax (node --check); headless Chromium (844x390): game starts, P.wm -> 1.0 when moving and -> 0 when stopped,
6 s of movement with zombies, no page errors.
NOT TESTED: real iPhone/Safari, visual feel on device, performance on device (change is arithmetic only).
img/z_necromancer.png added (drawn with code in the style of the other sprites; replace with a final artwork any time). Necromancer skill still not enabled.

- v16: folder img/maps/ added for background/obstacle images (map_<id>.png, obs_<id>_<n>.png); code paths updated. Currently empty (code-drawn floor is used).
