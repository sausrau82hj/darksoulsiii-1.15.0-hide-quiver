# DS3 Hide Quiver

Dark Souls III **1.15.0**

Equipping a bow or crossbow no longer puts a quiver, bolt case, or the arrows inside them on your character.
Bows, crossbows, damage, stamina cost, weight and saves are untouched.

This is a set of replacement `parts` model files, so the game has to be UXM-unpacked (`Game\parts` as loose
files). No DLL, no param archive edits, no Mod Engine needed.

## Models replaced

39 models, 78 files in total, each model with its `_l` LOD twin:

- Arrow quiver: `wp_a_6399`
- Bolt case: `wp_a_6700` (male), `wp_a_9700` (female)
- Arrows: `wp_a_7000` – `7071`
- Greatarrows: `wp_a_7300` – `7331`
- Bolts: `wp_a_7600` – `7661`

## Install

Back up the originals in `Game\parts\` that are about to be replaced, then overwrite them with the 78
`.partsbnd.dcx` files from `files\`. Restart the game afterwards — `parts` models are only read at process start.

## Uninstall

Copy the backed-up originals back over the replaced files; `parts` ends up as it was before the install.

## Credits and copyright

The `.dcx` files in `files` are modified FromSoftware game assets (© FromSoftware / Bandai Namco). They are
for single-player modding and tinkering, not for commercial use.
