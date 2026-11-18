# Items (`items/`)

One file per item: `<id>.vox`, holding one object named `<id>`. The game lists the items in its
own `items.json` (id, label, weight, backpack shape) and points each one at its file here.

## Where an item sits: the file says it

- **MagicaVoxel's origin is the centre of the hand.** The world origin, 0,0,0, is a vertex
  (a corner between cubes), and the hand is a 2x2x2 block, so its centre is a vertex too:
  the hand occupies the cubes -1 and 0 on every axis around the origin. Draw the item where
  you want it around that hand.
- **Draw it as held in the right hand.** In MagicaVoxel that is the hand on the +x side (the
  characters' `hand-l`: the game draws the art mirrored). Same orientation as the characters:
  up is z, the front is -y.
- **The left hand is a setting, not a redraw** (`offHand` in the game's `items.json`): by
  default the game moves the same model one cube across, so it points the same way and goes
  through the left fist as it goes through the right one. An item marked `"turn"` is turned
  180 degrees around the vertical line through the hand's centre instead: the ring shield, so
  its face points outward on both sides.
- **Two-handed items** (the power core): the origin is halfway between the two hands' centres.

A held item may pass through the fist: Paldi's sword has no cubes inside the hand.

## Where they came from (2026-11-18)

- `sword.vox` and `ring-shield.vox` were Paldi's `held-r` and `held-l` parts, taken out of
  `chrs/Paldi.vox` without changing a voxel or a colour (the sword was in his left hand, so it
  moved one cube to read as a right-hand item).
- The ten others were made by the AI as code in the game repo on 2026-11-15 and moved here.
  They are yours to edit now.

When you model a new character, keep what it holds out of its file: make each held object an
item here.
