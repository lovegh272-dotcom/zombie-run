ZOMBIE RUN v14 - PERFORMANCE GOVERNOR + AUDIO FIX + NECROMANCER

PERFORMANCE (target: minute 2 onward on mobile)
- Found real accumulator: blood splats on every kill + explosion scorch marks had no cap
  (130-180 large filled circles alive at once). Now one shared cap: 44 desktop / 26 mobile / 14 low quality,
  shorter lifetime, off-screen culling.
- Enemy cap is now adaptive (governor): base 85 mobile / 125 desktop. If avg frame > 20 ms or a spike > 45 ms
  persists 2 s, cap drops by 10 (min 50 mobile / 70 desktop); after 12 good seconds it recovers by 5.
- Spawn curve: gentler early ramp, and spawn rate slows as the screen fills (rate x (1.35 - Z/MAX_Z)).
- Horde event smaller (12 mobile / 16 desktop).
- Damage text cap 70 -> 36 desktop / 22 mobile / 10 low (outline pass skipped when crowded).
- Particle cap 360 -> 260 desktop / 150 mobile / 60 low. FX rings, fire zones (FZ) and smoke now capped.
- Zombie shadows are batched into one path; goblin additive glow skipped on low quality;
  large additive explosion fills skipped on mobile; off-screen FX skipped.
- Zombie vs obstacle push-out runs every other frame per zombie. Spatial grid map reset threshold lowered.
- Low quality also lowers canvas resolution (DPR max 1.25).
- Settings > Show FPS now shows: FPS, AVG ms, MAX ms, update ms, draw ms (JS time only, not GPU),
  Z alive/cap, FX, particles, damage texts, decals, bullets, quality, DPR.

AUDIO
- iOS unlock fixed: unlock now also on touchend/click/keydown (pointerdown alone is not accepted by iOS audio),
  plays a silent buffer, handles 'interrupted' state.
- App switch / screen lock: BGM stops + AudioContext suspends, resumes when visible again (no stacked music).
- SFX toggle is now independent from BGM (before, SFX-off also killed BGM). Speaker button = master mute.
- Separate volume for BGM and SFX (35/70/100%), saved.
- Shared noise buffer (was allocating a new buffer per shot/hit), voice limiter (14 normal / 28 important),
  SFX skipped while context not running.
- BGM adds a bass pulse during gameplay and an arpeggio during boss fights; ducks while paused.
- New game-over sound.

ZOMBIES
- Added type 'necromancer' (TYPES, ALLOW for custom maps, spawn after minute ~2:10, ~2.5% of spawns),
  loads img/z_necromancer.png via the existing loadZ path (code-drawn fallback if the PNG is missing).
  Its summon ability is NOT enabled yet (deferred). Screamer is unchanged.

OTHER
- Service worker cache zrun-v14, adds img/z_necromancer.png to precache.

TESTED: JS syntax (node --check); headless Chromium (iPhone UA/viewport) simulated 300 game-seconds with
skills for several characters: no runtime errors, caps respected, audio context running.
NOT TESTED: real iPhone/Safari, real GPU frame times, audio on a physical device (note: iPhone silent switch
mutes Web Audio in Safari).
