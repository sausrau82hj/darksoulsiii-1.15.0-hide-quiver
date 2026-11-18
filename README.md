# DS3 Hide Quiver · 隐藏箭袋 / 箭矢

Dark Souls III **1.15.0**

[English](#english) · **中文**

---

## 中文

装弓或弩时，角色身上不再出现箭袋、弩矢盒或插在里面的箭。弓、弩的属性、伤害、精力消耗、重量与存档都不受影响。

替换的是一组 `parts` 模型，所以游戏需为 **UXM 解包**状态（`Game\parts` 是散开的文件）。不涉及 DLL、不改 params、不需要 Mod Engine。

### 替换的模型

39 个模型、共 78 个文件（每个模型带一个 `_l` LOD）：

- 箭袋：`wp_a_6399`
- 弩矢盒：`wp_a_6700`（男）、`wp_a_9700`（女）
- 箭：`wp_a_7000` – `7071`
- 大箭：`wp_a_7300` – `7331`
- 弩矢：`wp_a_7600` – `7661`

### 安装

用 `files\` 里那 78 个 `.partsbnd.dcx` 覆盖游戏 `Game\parts\` 下的同名文件。

覆盖前先把每个要被替换的原文件复制一份放在旁边，文件名后面加 `.pre-hidequiver`，这份副本就是卸载时用的备份。装完重启游戏生效 —— `parts` 模型只在进程启动时读取。

### 卸载

把 `parts\` 里的 `.pre-hidequiver` 备份改回原名，覆盖掉被替换的文件，再删掉这些备份，`parts` 就回到安装前的样子。

要是当初没留备份，用 UXM 重新解包 `parts`，或 Steam「验证文件完整性」（会连别的 mod 一起清掉）。

### 版权

`files` 里的 `.dcx` 是修改过的 FromSoftware 游戏资源（© FromSoftware / Bandai Namco），仅供单机 mod 修改使用，不可商用。

---

## English

Equipping a bow or crossbow no longer puts a quiver, bolt case, or the arrows inside them on your character.
Bows, crossbows, damage, stamina cost, weight and saves are untouched.

This is a set of replacement `parts` model files, so the game has to be UXM-unpacked (`Game\parts` as loose
files). No DLL, no param archive edits, no Mod Engine needed.

### Models replaced

39 models, 78 files in total, each model with its `_l` LOD twin:

- Arrow quiver: `wp_a_6399`
- Bolt case: `wp_a_6700` (male), `wp_a_9700` (female)
- Arrows: `wp_a_7000` – `7071`
- Greatarrows: `wp_a_7300` – `7331`
- Bolts: `wp_a_7600` – `7661`

### Install

Overwrite the 78 `.partsbnd.dcx` files in the game's `Game\parts\` with the same filenames from `files\`.

Before overwriting, copy each original that is about to be replaced next to itself with a `.pre-hidequiver`
suffix — those copies are the uninstall backup. Restart the game afterwards, since `parts` models are only read
at process start.

### Uninstall

Rename every `.pre-hidequiver` backup in `parts\` back to its original name, overwriting the replaced files, then
delete the backups. `parts` is back to how it was before the install.

No backup left? Re-unpack `parts` with UXM, or use Steam's "verify integrity" (which also wipes other mods'
changes).

### Credits and copyright

The `.dcx` files in `files` are modified FromSoftware game assets (© FromSoftware / Bandai Namco). They are
for single-player modding and tinkering, not for commercial use.
