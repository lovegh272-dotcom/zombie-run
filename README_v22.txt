ZOMBIE RUN v22 (on top of v21)

- Added all skill icons for all 8 characters (sk_<id>_dash|blast|shield.png, ult_<id>.png), 256 px, cropped from 2x2 sheets.
- Added FIRE (normal attack) button icons fire_<id>.png for all 8 characters. Code: new loader + applySkIcons() sets the FIRE
  button image (falls back to the gun emoji if a file is missing). The FIRE button only shows in manual-aim mode.
- sw.js cache zrun-v22.
TESTED: node --check, headless Chromium: icons applied for all characters, no page errors.
NOT TESTED: real iPhone/Safari.
