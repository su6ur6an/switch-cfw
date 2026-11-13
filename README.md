# switch-cfw

Custom Nintendo Switch CFW pack for **HOS 23.5.0**.

This repo holds the complete SD-card release assembled from the component forks below. Each component repo only holds its own source and releases.

## Components

| Component | Upstream | Fork / branch | Base |
|---|---|---|---|
| hekate | `CTCaer/hekate` | `su6ur6an/hekate` `custom` | `master` (includes PR #1317) |
| Atmosphere | `Atmosphere-NX/Atmosphere` | `su6ur6an/Atmosphere` `custom` | `1.12.2` + PR #2912 |
| sys-patch | `Impeeza/sys-patch` | `su6ur6an/sys-patch` `custom` | `v1.6.3.0` |
| TegraExplorer | `suchmememanyskill/TegraExplorer` | `su6ur6an/TegraExplorer` `custom` | `4.2.0` + PR #106 |
| Lockpick_RCM_Pro | `sthetix/Lockpick_RCM_Pro` | `su6ur6an/Lockpick_RCM_Pro` `custom` | `2.2.0` |
| MissionControl | `ndeadly/MissionControl` | `su6ur6an/MissionControl` `custom` | `v0.16.1` |
| sys-clk | `ppkantorski/sys-clk` | `su6ur6an/sys-clk` `custom` | `2.0.1+r28` |
| Ultrahand-Overlay | `ppkantorski/Ultrahand-Overlay` | `su6ur6an/Ultrahand-Overlay` `custom` | `main` (includes `35e2fd1`) |

## PRs / cherry-picks

- **hekate PR #1317** (merged): `184584a` + `8e1392d` fix 23.5.0 non-exFAT/FAT32 nogc offsets. Already in `master`.
- **Atmosphere PR #2912** (`13053be`): non-exFAT 23.5.0 nogc offset fix, cherry-picked onto `1.12.2`.
- **Ultrahand `35e2fd1`**: post-`v2.5.4` home-press hold-duration fix. Already in `main`.
- **TegraExplorer PR #106**: 1TB+ SD card support, cherry-picked onto `4.2.0`.
- Not used: TegraExplorer PR #111 (incomplete BDK rewrite); hekate PR #1247 only if the build fails.

## Libraries

Flat shared clones, symlinked into component repos with `.gitmodules` removed on `custom` branches:

- `libnx` `b156b477`
- `Atmosphere-libs` `75c68891`
- `libtesla` `f766e9b`
- `libultrahand` `ea02e8d`

## Release layout

`release/` will mirror the SD-card root once assembly is complete:

```text
release/
  atmosphere/
  bootloader/
  switch/
```

No `prod.keys` or `title.keys` are included.

## Status

Building the `custom` component branches for HOS 23.5.0. Release assembly pending.
