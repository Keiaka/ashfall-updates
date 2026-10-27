# Ashfall Survivors updates

## Current release: 0.5.0 (build 5)

Open the existing Windows launcher: **CHECK FOR UPDATES → INSTALL UPDATE → PLAY**.

Feed: `https://raw.githubusercontent.com/Keiaka/ashfall-updates/main/manifest.json`

- Three-column class, equipment and expedition menu; rarity-framed upgrade cards with original class sigils.
- Keep all collected equipment, compare items, equip/unequip manually, and save a loadout for each class.
- Six sequential zones per class with Common → Uncommon → Rare → Epic → Legendary → Unique equipment.
- Run options for enemy density, health, damage and speed; reward multiplier capped at x2.
- Twelve account achievements fund six perks: rerolls, banishes, skipping, fourth cards, class XP and loot chance.
- Results include progression, loot and combat totals. Try again, return to menu, or continue into endless after victory.
- Endless spawns bosses every two minutes; pause and Extract to bank finds. Death retains the earlier victory's bank.
- Optional damage, healing and boss-damage meters under Settings → Combat Meters.
- Existing class talents, upgrade rules, settings and banked gear are preserved and migrated.

See [GUIDE.md](GUIDE.md) for exact progression, odds, controls and save behavior.

This is original Ashfall gameplay inspired by the supplied references, not a complete Azeroth Survivors port. The six zones reuse three environment themes. No 3D appearance editor, companions or co-op in this release.

## Validation

System tests cover save migration, manual swaps, equipment banking, achievement/perk persistence, capped rewards, overkill/overheal metrics, DOT damage, card banishes, endless bosses/extraction and repeat-award prevention. Prior v0.4 regression tests pass. Six invulnerable long simulations completed with all four minibosses and the final boss; these check stability, not human balance. UI and exported pack checked with Godot 4.3 on Linux. Windows-specific gameplay remains to be playtested.

Only public game packs, signed manifests and documentation belong here. Never commit signing credentials. Engine/launcher changes may require a new installer. Previous versioned packs remain for rollback.
