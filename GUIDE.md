# Ashfall Survivors 0.4.0 — Class Campaign

Import this folder's project.godot in Godot 4.3 Standard and press F5. Extract the ZIP to a new writable folder first. Source uses tabs consistently. The main scene now loads campaign.gd; do not change it back to game.gd or covenant.gd.

## Before a run
Choose your class on the title screen. CLASS TALENTS opens the Class Archive; browse all six classes with its tabs. UPGRADE CATALOG lists each class's six upgrade lines and the general upgrade pool. BANKED EQUIPMENT shows retained gear and filters weapons by class.

Each class has its own permanent XP, level and talent allocation. Three branches with four nodes each form a 12-node, 24-rank tree per class (72 nodes total). Nodes have 3, 2, 2 and 1 maximum ranks down each branch. You must max the preceding node before advancing. There is one point per class level after level 1, up to 24 points at class level 25. Free respec refunds all points between runs. These are original Ashfall trees inspired by the ranked/pre-run structure requested, not copied WoW talent tables.

## During a run
WASD/arrows move; Space dashes; Q flask; B equipment; T read-only talent snapshot; J upgrade journal; Esc pauses. Skills auto-cast. Run level-ups grant temporary upgrade cards, never permanent talent points. J can switch between global totals and class skill totals.

Your FIRST FOUR DISTINCT CLASS UPGRADE LINES fill four slots. Choosing the same line again increases its rank and does not use another slot. Once full, you can only improve those four class lines; unchosen lines, even from your own class, cannot appear. General upgrades such as life and movement do not use slots. A class line automatically learns its skill when needed, up to three active skill families total. The class's starting skill does not itself consume a line slot. Class Gem is one line, Damage another, Range another, etc. Pure and hybrid builds are both possible before the lock. Rarity Unique is separate from this four-line system.

Rarity probabilities remain Common 48%, Uncommon 27%, Rare 15%, Epic 7%, Legendary 2.5%, Unique 0.5%. A Unique roll is the maximum numerical bonus, once per upgrade type per run. Repeat Unique rolls for that type become Legendary. Caps remain in effect. Class upgrades only affect their own skill family.

## Class progression after runs
Permanent class XP = floor(kills / 10) + floor(min(survival seconds, 900) / 6) + 100 per mini-boss kill + 300 per final boss kill.
The next permanent level costs 100 + current class level * 60 XP. XP thresholds are cumulative across runs. Kills and survival also grant XP on defeat or explicit abandonment. Closing the application mid-run does not finalize XP. Results show each component and level changes. Old ash mastery is retained separately.

## Encounters and loot
Mini-bosses arrive at 4, 7, 10 and 12 minutes, once each, with telegraphed attacks. The Warden arrives at 15 minutes. Normal wave spawning stops then; remaining enemies and boss fights may extend beyond 15 minutes. Final-boss death grants its loot before victory banking.

| Encounter | Gear roll chance | Gear tier |
|---|---:|---|
| 4:00 Sentinel | 70% | T1 |
| 7:00 Seer | 78% | T2 |
| 10:00 Reaver | 85% | T3 |
| 12:00 Matron | 90% | T4 |
| 15:00 Warden | 100% | T5 |

Quality odds (Common / Uncommon / Rare / Epic / Legendary / Unique) on a successful gear roll:
- T0 ordinary loot: 65 / 25 / 8 / 1.8 / 0.2 / 0 percent.
- T1: 15 / 50 / 25 / 8 / 1.8 / 0.2 percent.
- T2: 0 / 25 / 45 / 23 / 6 / 1 percent.
- T3: 0 / 5 / 30 / 45 / 17 / 3 percent.
- T4: 0 / 0 / 15 / 40 / 38 / 7 percent.
- T5: 0 / 0 / 0 / 25 / 55 / 20 percent.

## Equipment
Eight slots: Helmet, Shoulders, Chestplate, Legs, Boots, Hands, Wrists, Weapon. Armour is shared across classes. Weapons are retained per class; legacy migrated weapons are universal. One-handed weapons trade raw damage for critical chance; two-handed weapons give more damage. There is one weapon slot, with no off-hand or dual-wield system in this version.

| Class | One-handed | Two-handed |
|---|---|---|
| Pyro | Wand | Staff |
| Storm | Wand | Storm Staff |
| Frost | Sceptre | Ice Staff |
| Plague | Dagger | Plague Staff |
| Blade | Sword | Greatsword |
| Rune | Hammer | Great Hammer |

Stronger compatible gear auto-equips; weaker drops are salvaged for healing. Victory banks the equipped loadout and forging; defeat/abandon preserves the old bank and discards provisional changes. This remains a best-equipped loadout collection, not an unlimited backpack or manual inventory manager.

## Saves and migration
campaign-profile.json in the existing Ashfall Survivors Godot user-data folder stores all six class profiles and the new gear bank. Atomic temporary-file/backup writes and Retry Save protect against write failures. On first use, old relic-bank.json items migrate: sceptre→universal weapon, cuirass→chestplate, greaves→boots, ring→wrists, amulet→shoulders, preserving their bonuses. The old save is not deleted. Prior mastery/settings are retained. New class levels start at 1 because older releases did not record the needed per-class run history.

## Source and validation
- campaign.gd: campaign UI, permanent progression, class modifiers, four-slot draft, boss schedule, loot, migration.
- campaign_data.gd: classes, talent definitions, weapon options and loot tables.
- covenant.gd: v0.3 journal/rarity/animation foundations.
- game.gd / base.gd: shared skills, rendering, settings and core simulation.
- test_v4.gd: isolated persistence, class/talent/upgrade/boss/gear tests. Set ASHFALL_V3_TEST=1, ASHFALL_PROFILE_PATH=/tmp/... and ASHFALL_BANK_PATH=/tmp/... when running headlessly in a test environment. Do not use your real save paths.
- soak_v4.gd: long simulations with invulnerability, automatic XP pickup and seeded four-line class builds. These test stability and execution, not human win rates.

Menus are visually checked using the Linux Godot 4.3 renderer. Windows execution and human balance still need playtesting. Exported packs exclude test scripts.

## Publishing
This release is version 0.4.0, build 4. The next release must use a new versioned pack filename and build 5 or greater. Export PCK/ZIP from the game project, sign using the separate private publisher kit, upload the PCK first, then manifest.json last. Do not publish signing-key.pem or overwrite the launcher's own Windows/AshfallSurvivors.pck.

Feed: https://raw.githubusercontent.com/Keiaka/ashfall-updates/main/manifest.json

Reference reviewed: https://github.com/OutThisLife/azeroth-survivors-re (README and survivors module/enemy architecture). Ashfall remains its own Godot implementation and original procedural artwork; no source or game assets were copied from that repository for this update.
