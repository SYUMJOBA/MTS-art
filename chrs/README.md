# Characters (`chrs/`)

One file per playable character, all in this one flat folder. The game scans this folder on
every page load: drop a file in and it shows up. Old versions, exploded displays, figurines
and other extras live in `../extras/`.

## File names: `Name attribute.vox`

The first word is the character. Every further word is an **attribute** naming a variant of
that same character:

- `Arca gd.vox`, `Arca rg.vox`, `Arca un.vox` are three variants of Arca.
- `Kyle clo.vox` and `Kyle cloh.vox` are Kyle with the hood off and on.

The game groups variants under their character, lets you switch between them with **V**, and
gives all variants of one character the same backpack.

## The part template

Every character is split into the same named parts as Nox (`Nox.vox`), the standard humanoid:

`head`, `torso`, `shoulder-l/r` (upper arm), `arm-l/r` (forearm), `hand-l/r`, `thigh-l/r`,
`leg-l/r` (shin), `foot-l/r`, plus optional `plate`, `backpack` and `backpack lid`.

Shoulders and thighs are 3 rows tall and repeat the top row of the arm or leg below them; the
game puts the elbow and knee hinge in that shared row.

A file that is still one block (not split into these parts yet) is listed in the game but
cannot be played until it is split. Since 2026-11-15 every file here is split; the unsplit
originals of the last ten are kept in `../extras/unsplit originals/`.

# There are a few exceptional added named parts to these schemas

In the game, all of them are moved by **physics** (they swing with the character's motion)
rather than animated by hand.

## 1st: Long hair (`hair-<n>`)

Hair that hangs below the head is named `hair-<n>`, where `<n>` is how many rows farther it is
from the head, going down. Everything at head height stays part of `head`.

This is not only for straight flowing hair: any hair long enough to justify it gets this rule,
thick hair included (Lera and Lupa have thick hair that was made into `hair-<n>` too).

Files using it: Anfei, Ansa, Lera, Lupa, Mika, Miv, Paldi, Vikt, Vikt st.

## 2nd: Cape

There are two schemas.

**Simple cape** (one piece down the back): `cape`, then `cape-<n>` for every row below it,
going down.
Files using it: Arca (all three variants), Kyle clo, Kyle un, Sarho (the cloth hanging below its hood).

**Full cape** (Ozen only): front and back parts, each potentially flowing down. Named
`cape-<b for back, f for front>-<l for left, r for right>`, with a `-<n>` if there is vertical
depth: `cape-b-l`, `cape-b-l-1` ... `cape-b-l-4`, `cape-f-r`, and so on.

I thought of giving it the generic name "Back", but it could be confused with backpack, and
there is a fundamental difference: a cape can dynamically flow.

## 3rd: Pockets (actually called `item-<pos>`)

There are back, left, right and front variants: `item-b`, `item-l`, `item-r`, `item-f`.
These "pockets" can actually be any item.

Files using them: Arca (`item-l`, `item-r`), Kyle clo and Kyle cloh (`item-b`), Noz (`item-l`,
`item-r`, `item-b`), Ozen (`item-b`), Sarho (`item-b`, the pouch at its waist).

## 4th: Pendant (`pendant`)

Can be used for amulets and a bunch of other things. Meant for Ozen's whistle, but no file has
a part named `pendant` yet (Ozen has `item-b` and `plate`).

## 5th: Bun (`bun`)

Some characters have a bun attached to the back of their head. It gets extra motion: it
springs with the head's movement.

Files using it: Dedu.

## Proposed by the AI, not approved yet: held objects (`held-<l|r>`)

An object held in a hand: `held-r` in the right hand, `held-l` in the left. It rides rigidly on
that hand (no physics). Used for Paldi's staff (`held-r`) and ring (`held-l`) when Paldi was
split on 2026-11-15. Rename it if you prefer another name.

## Unnamed parts

Parts without a name are kept and ride rigidly on the nearest body part; all unnamed parts of
one file move together as one prop.

Engi's four unnamed parts are the screens coming out of his arm display. They are fully
optional and have no proper names yet.
