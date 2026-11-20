# DS3 Hide Quiver

Dark Souls III **1.15.0**

Equipping a bow or crossbow no longer puts a quiver, bolt case, or the arrows inside them on your character.
Bow and crossbow stats, damage, stamina cost, weight and saves are untouched.

This is a set of 39 replacement `parts` models — 78 `.partsbnd.dcx` files, each model plus its `_l` LOD twin.
No DLL, no param edits.

## Models replaced

- Arrow quiver: `wp_a_6399`
- Bolt case: `wp_a_6700` (male), `wp_a_9700` (female)
- Arrows: `wp_a_7000` – `7071`
- Greatarrows: `wp_a_7300` – `7331`
- Bolts: `wp_a_7600` – `7661`

## Install

The `parts` folder in this repository is the whole mod: 78 files, flat, no subfolders. Use either method.

### Option A — Mod Engine 2 (game stays packed)

1. Download [Mod Engine 2](https://github.com/soulsmods/ModEngine2/releases) (`ModEngine-2.1.0.0-win64.zip`) and extract it anywhere.
2. Copy the `parts` folder into Mod Engine's `mod` folder, so you end up with `mod\parts\wp_a_6399.partsbnd.dcx` and the rest.
3. Start the game with `launchmod_darksouls3.bat`. Starting it from Steam bypasses the loader and the mod will not appear.

Mod Engine 2 is discontinued upstream; its successor [me3](https://github.com/garyttierney/me3) takes the same
`parts` folder. Nothing on disk gets overwritten this way — delete `mod\parts` to uninstall.

### Option B — UXM unpacked (no launcher)

1. Download [UXM](https://github.com/JKAnderson/UXM/releases), point it at `DARK SOULS III\Game\DarkSoulsIII.exe` and unpack.
   That patches the executable and leaves `Game\parts` as loose files.
2. Copy the 78 files from `parts\` into `Game\parts\`, keeping copies of the originals you replace.
3. Start the game normally from Steam. `parts` models are only read at process start, so restart if it was running.

## Uninstall

- Option A: delete `mod\parts`.
- Option B: copy your backed-up originals back into `Game\parts\`.

## License

Scripts and text: MIT (see `LICENSE`). The `.dcx` files are modified FromSoftware game assets — see
[THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).
