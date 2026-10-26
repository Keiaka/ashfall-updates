# Ashfall Survivors updates

Signed game-content updates for the Ashfall Survivors Windows launcher.

## Update your game

Paste this address into the launcher's feed field, choose **SAVE FEED**, then **CHECK FOR UPDATES → INSTALL UPDATE → PLAY**:

```text
https://raw.githubusercontent.com/Keiaka/ashfall-updates/main/manifest.json
```

The launcher must already be installed. No manual ZIP extraction is needed for game updates.

## Current release: 0.3.0 (build 3)

Ashfall 0.3.0 — The Covenant
- 15-minute runs; Warden arrives at 15:00.
- Tilted ground perspective, animated heroes/enemies, cloth motion, flickering lights and impact particles.
- 24 passive talents in four branches; two starting points and another every four levels.
- Six upgrade rarities: Common, Uncommon, Rare, Epic, Legendary, Unique.
- Movement rolls: 1%, 3%, 5%, 8%, 12%, 16% of base movement speed.
- J opens your run journal: every selected upgrade, rarity and bonus, plus current stat totals.
- Victory banks your equipped loadout and forging. Defeat, abandonment or closing loses this run's changes; the previous bank survives.
- Enemy HP and damage increase over time. The final boss scales with level, banked gear and estimated build damage, and attacks faster below half health.
- Existing mastery/settings retained. New relic bank starts empty. Run upgrades and talents still reset each run.
- Blade Halo now hits enemies inside the orbit, fixing its point-blank dead zone.

## Controls and persistence

**J** opens the upgrade journal, **T** the passive tree, and **B** equipment. Victory banks the five currently equipped slots. This is a retained loadout, not an unlimited stash. Previous mastery/settings remain usable; the new relic bank begins empty. Talents and level-up bonuses reset each run.

The boss arrives at 15:00 and combat may continue afterward. Rarity rates are 48%, 27%, 15%, 7%, 2.5%, 0.5%. Unique is the highest numeric upgrade roll, once per upgrade type per run. Equipment retains its separate existing item tiers.

## Verification

Automated checks cover rarity distribution and values, all 24 talents/prerequisites, journal records, skill-slot limits, bank persistence on victory/death/abandon/crafting, progressive health/damage, boss timing/scaling and Blade Halo's point-blank coverage. Long-run tests use invulnerability to verify simulation stability, not human difficulty. UI screens checked on Godot 4.3 Linux; Windows execution has not been tested in this environment.

Only public game packs and signed manifests belong here. Never commit signing credentials. The current launcher supports Godot 4.3 game packs; engine/launcher upgrades may need a new installer.
