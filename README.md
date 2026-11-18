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

备份原文件，再用 `files\` 里的同名文件覆盖 `Game\parts\`，重启游戏生效（`parts` 只在进程启动时读取）。

要备份的就是即将被覆盖的那 78 个同名文件，备份名加 `.pre-hidequiver` 后缀放在 `parts\` 里即可。手动或整段粘贴：

```powershell
$mod   = "D:\Mods\HideQuiver"                                                 # 本仓库解压位置
$parts = "D:\steam\steamapps\common\DARK SOULS III\Game\parts"

Get-ChildItem "$mod\files\*.partsbnd.dcx" | ForEach-Object {
    $t = Join-Path $parts $_.Name
    if ((Test-Path -LiteralPath $t) -and -not (Test-Path -LiteralPath "$t.pre-hidequiver")) {
        Copy-Item -LiteralPath $t -Destination "$t.pre-hidequiver"
    }
    Copy-Item -LiteralPath $_.FullName -Destination $t -Force
}
```

已有 `.pre-hidequiver` 的不会再被覆盖，所以重复跑不会把改过的模型当成原版存起来。

### 卸载

把 `parts\*.pre-hidequiver` 覆盖回同名文件，再删掉这些备份：

```powershell
$parts = "D:\steam\steamapps\common\DARK SOULS III\Game\parts"
Get-ChildItem "$parts\*.pre-hidequiver" | ForEach-Object {
    Copy-Item -LiteralPath $_.FullName -Destination ($_.FullName -replace '\.pre-hidequiver$','') -Force
    Remove-Item -LiteralPath $_.FullName
}
```

没备份就用 UXM 重新解包 `parts`，或 Steam「验证文件完整性」（会连别的 mod 一起清掉）。

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

Back up the originals, then overwrite `Game\parts\` with the same filenames from `files\`. Restart the game
afterwards — `parts` models are only read at process start.

The files to back up are exactly the 78 matching names in `parts\`; keep each copy next to it with a
`.pre-hidequiver` suffix. By hand, or paste this whole block:

```powershell
$mod   = "D:\Mods\HideQuiver"                                                 # where you unpacked it
$parts = "D:\steam\steamapps\common\DARK SOULS III\Game\parts"

Get-ChildItem "$mod\files\*.partsbnd.dcx" | ForEach-Object {
    $t = Join-Path $parts $_.Name
    if ((Test-Path -LiteralPath $t) -and -not (Test-Path -LiteralPath "$t.pre-hidequiver")) {
        Copy-Item -LiteralPath $t -Destination "$t.pre-hidequiver"
    }
    Copy-Item -LiteralPath $_.FullName -Destination $t -Force
}
```

An existing `.pre-hidequiver` is never overwritten, so rerunning this never stores a patched model as the original.

### Uninstall

Copy every `parts\*.pre-hidequiver` back over its original name, then delete the backups:

```powershell
$parts = "D:\steam\steamapps\common\DARK SOULS III\Game\parts"
Get-ChildItem "$parts\*.pre-hidequiver" | ForEach-Object {
    Copy-Item -LiteralPath $_.FullName -Destination ($_.FullName -replace '\.pre-hidequiver$','') -Force
    Remove-Item -LiteralPath $_.FullName
}
```

No backup? Re-unpack `parts` with UXM, or use Steam's "verify integrity" (which also wipes other mods' changes).

### Credits and copyright

The `.dcx` files in `files` are modified FromSoftware game assets (© FromSoftware / Bandai Namco). They are
for single-player modding and tinkering, not for commercial use.
