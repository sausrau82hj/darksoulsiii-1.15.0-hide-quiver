# DS3 Hide Quiver

Dark Souls III

Only verified for version 1.15.0, but it will likely work for other versions as well.

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

### Option A — Mod Engine (game stays packed)

1. Download [Mod Engine](https://www.nexusmods.com/darksouls3/mods/332) and put `dinput8.dll` and `modengine.ini`
   in `DARK SOULS III\Game\`.
2. In `modengine.ini`, under `[files]`, enable the override directory:

   ```ini
   useModOverrideDirectory=1
   modOverrideDirectory="\mod"
   ```

3. Copy this repository's `parts` folder into `Game\mod\`, so you end up with
   `Game\mod\parts\wp_a_6399.partsbnd.dcx` and the rest.
4. Start the game from Steam as usual — `dinput8.dll` loads the override. Restart if the game was running.

On game versions newer than 1.15.0, use the [patched Mod Engine build](https://www.nexusmods.com/darksouls3/mods/2410).

### Option B — UXM (unpacked and patched)

1. Download [UXM](https://github.com/JKAnderson/UXM/releases), point it at `Game\DarkSoulsIII.exe` and run **Unpack**.
   Then run **Patch** as well — unpacking alone leaves the game reading its archives, and the loose files only take
   effect once the executable is patched to load them.
2. Copy the 78 files from `parts\` into `Game\parts\`, keeping copies of the originals you replace.
3. Start the game from Steam. `parts` models are only read at process start, so restart if it was running.

## Uninstall

- Option A: delete `Game\mod\parts`, or set `useModOverrideDirectory=0` in `modengine.ini`.
- Option B: copy your backed-up originals back into `Game\parts\`.

## License

Scripts and text: MIT (see `LICENSE`). The `.dcx` files are modified FromSoftware game assets
(© FromSoftware / Bandai Namco), for single-player modding only, not for commercial use.
See [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for the tools referenced above.
