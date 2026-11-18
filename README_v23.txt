ZOMBIE RUN v23 (on top of v22)

1. Character select redesigned: each character is a card with portrait (the in-game sprite), name, description and its 4 skill icons
   (DASH / BLAST / SHIELD / ULT) with labels, in the character's theme color. The selected card is raised (lifted, glow, white border);
   pressing a card pushes it down, releasing pops it up (short pop animation on the card you just picked). Falls back to emoji icons
   for characters without icon files (e.g. custom characters).
2. Necromancer skill (summon): keeps distance from the player (backs off if closer than 190, stops at ~290). About every 7 s it casts for 0.7 s
   (purple ring telegraph), then summons up to 3 mini zombies (HP scales with time). Max 6 alive minions per Necromancer, never above the
   global zombie cap. Max 3 Necromancers alive at once. Perf logger spike flags now include N when a Necromancer is on screen.
sw.js cache zrun-v23.

TESTED: node --check, headless Chromium (see chat). NOT TESTED: real iPhone/Safari, touch feel of the press/raise animation.
