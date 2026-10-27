# Ashfall Survivors updates

## Install the current game update

Open the existing Windows launcher, then choose **CHECK FOR UPDATES → INSTALL UPDATE → PLAY**.

If a feed is not set, paste this address and choose **SAVE FEED**:

```text
https://raw.githubusercontent.com/Keiaka/ashfall-updates/main/manifest.json
```

## Current release: 0.4.0 (build 4)

Ashfall 0.4.0 — Class Campaign
- Pre-run Class Archive: inspect all six classes, their talents, class upgrades and general upgrades.
- Six permanent class levels (cap 25), with 72 talent nodes: three branches, four tiers per class, ranked nodes, prerequisites and capstones. One point per class level after level 1; free respec between runs. Talents are read-only during runs.
- Result-screen class XP breakdown: 1 XP per 10 kills, 1 XP per 6 survival seconds (up to 15 minutes), 100 per mini-boss, 300 per final boss. Defeat and abandonment still award earned XP. Closing mid-run does not finalize XP.
- Mini-bosses at 4:00, 7:00, 10:00 and 12:00; final Warden at 15:00. Normal wave spawning stops at 15:00 so remaining enemies and bosses can be finished.
- Eight gear slots: Helmet, Shoulders, Chestplate, Legs, Boots, Hands, Wrists, Weapon. Class-compatible one- and two-handed weapon options; shared armour and separate retained weapons for each class.
- Mini-boss loot chances: 70%, 78%, 85%, 90%; Warden 100%. Gear tiers T1-T5 grow with encounter tier, with improving rarity odds. Warden gear is Epic or better. A rolled drop is not necessarily stronger than equipped gear.
- Victory banks equipped gear; defeat/abandon loses new gear and forging, while preserving previous banked items. Existing v0.3 equipment migrates without deleting its old save.
- 36 class upgrade lines including class-only damage, projectiles/chains/echoes/blades/totems, range, cast speed and status effects.
- Four DISTINCT class lines per run: repeats improve the same line. Once four are selected, no new class lines or gems appear, including unchosen lines from the same class. General upgrades use no slots. Three active skill families maximum.
- J journal includes a toggle between global totals and actual class skill totals.
- Swept projectile collision fixes missed point-blank hits at lower frame rates.

See [the full game guide](GUIDE.md) for class progression, gear probabilities, controls, migration and editing instructions.

## Validation

Automated checks cover permanent class XP and repeat-award prevention, all talent ranks/prerequisites, respec and in-run edit rejection, four-line pool locking, class modifier isolation, exact boss timers, gear compatibility, victory/death banking, legacy migration, failed-save refunds and point-blank projectile collision. Six long simulations completed using seeded four-line builds, invulnerability and automatic XP pickup; these are stability checks, not human difficulty measurements. UI and exported game pack tested with Godot 4.3 on Linux. Windows-specific execution remains to be playtested.

Only public game packs, signed manifests and game documentation belong here. Never commit signing credentials. The pinned launcher supports Godot 4.3 packs; engine/launcher changes may require a separate installer. Old versioned packs remain available for rollback.
