ZOMBIE RUN v15 - AUTOMATIC PERFORMANCE LOGGER (on top of v14, gameplay unchanged)

- Every run records performance automatically into localStorage (key zperf, last 5 runs kept).
  * One row every 5 s: time, min FPS, avg ms, max ms, update ms, draw ms, zombies, cap, FX, particles, damage texts, decals, low-quality flag.
  * Spike log (frame > 45 ms, up to 40/run): time, ms, previous-frame update/draw ms, Z/FX/particles, flags
    (B = boss, U = ULT active, plus event name horde/fog/rain).
    If ms is high but upd+drw are small, the bottleneck is outside JS (GPU/compositor/system).
  * Saved every ~20 s, on game over, on page hide and when the tab is hidden.
- Settings > "บันทึกประสิทธิภาพ": shows per-minute summary + rows + spikes of the last 2 runs,
  with Copy and Clear buttons. Paste the text into chat.
- sw.js cache zrun-v15. README_v14.txt kept for the previous notes.

TESTED: JS syntax; headless Chromium: rows/spikes recorded, saved, report built, clear works, no errors.
NOT TESTED: real iPhone. Logger measures JS time only; real GPU time is not measurable from the page.
