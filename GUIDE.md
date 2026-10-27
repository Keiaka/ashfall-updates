# Ashfall Survivors 0.5.0 — Armory & Expeditions

Open `project.godot` with Godot 4.3. Extract this entire ZIP to a writable folder first (for example Documents/AshfallSource); do not edit inside the ZIP or Program Files. Run with F6/F5. The game starts through `main.tscn` → `dominion.gd` → `campaign.gd` → `covenant.gd` → `game.gd` → `base.gd`.

## Playing the update

Existing Windows launcher: CHECK FOR UPDATES → INSTALL UPDATE → PLAY. This is content build 5; no engine replacement is needed. Sound, graphics and control settings remain available. Settings → COMBAT METERS separately enables damage, effective healing and boss damage. Meters are off by default and save their choices. Values are actual damage (excluding overkill), effective healing (excluding overheal), and average rate over active run time, including noncombat time. Poison, ignite and bleed are counted separately. Upgrade health bonuses and entering a run are not healing events.

## Main menu and collection

The three-column menu contains class selection, the active class's equipment and unlocked expeditions. Collection opens the armory. Click a slot, click a collected item, compare it, then EQUIP SELECTED or UNEQUIP SLOT. Every class remembers its own eight-slot loadout. Armor is shared; weapons retain class compatibility and one-/two-handed bonuses. Banked equipment is never automatically replaced or deleted by a stronger drop. Existing v0.4 best-in-slot gear migrates into the collection and is initially equipped.

During a run, B → COLLECTION / SWAP GEAR opens the same collection and pauses play. New drops only auto-fill empty slots. All finds, including weaker pieces, remain available. Forging modifies the run's item copy; winning or extracting banks the changes. Defeat/abandon discards unbanked finds and forging. Swapping gear does not heal you. Victory keeps ALL collected items, including unworn ones. The collection has paginated lists, not a fixed capacity.

## Expeditions

Each class starts with Sundered Cloister. Defeat its final boss to unlock the next zone for that class. Previously saved gear and talents are preserved; old saves have no zone-clear history, so they start at zone one.

| Zone | Equipment rarity | Enemy health multiplier |
| --- | --- | --- |
| Sundered Cloister | Common | 1.00 |
| Blighted Crypt | Uncommon | 1.65 |
| Cinder Forge | Rare | 2.30 |
| Tempest Bastion | Epic | 2.95 |
| Hollow Citadel | Legendary | 3.60 |
| Crown of Ruin | Unique | 4.25 |

The six expeditions reuse three existing environment themes. Zone rank determines gear rarity; miniboss tier determines additional power. Upgrade-card rarity still rolls independently (48/27/15/7/2.5/0.5%). Equipment may roll any of eight slots. This release does not use named fixed boss-to-item tables. The Drop Tables screen describes these actual rules.

Minibosses appear at 4, 7, 10 and 12 minutes. The Warden appears at 15 minutes; the run ends when defeated, not immediately at 15:00. Base equipment drop odds are 70%, 78%, 85%, 90%, 100%. Normal enemies have 0.2% and elites 5% gear drop chances. Every zone also increases enemy damage by 22% per rank, on top of existing time/arena scaling.

## Run options

Density 100–500%, health 100–500%, damage 100–300%, speed 100–150%, adjustable in 25-point steps. Settings lock at run entry. Reward multiplier is `min(2, 1 + sum(multiplier - 1) / 4)` for permanent class XP and boss loot chance. Density accelerates spawn cadence; the existing 230 normal-enemy cap remains. Run XP per enemy is divided by the density multiplier. Boss loot chance caps at 100%.

## Results and endless

Results show class XP/progress, newly secured loot, kills, survival, total damage, healing, damage taken, boss damage, average DPS and achievement rewards. TRY AGAIN starts another run; MAIN MENU returns to preparation. After the first victory, KEEP FIGHTING / ENDLESS resumes the same build with full health and three seconds of protection. Your victory collection and XP are already secured.

Endless spawns more waves and a Warden every two minutes. Each endless wave adds 35% health and 20% damage scaling. ESC → EXTRACT / BANK FINDS ends endless and saves its new equipment. Death/abandon retains the first victory's bank but loses subsequent finds. Permanent XP and lifetime counters award only the unsaved delta; opening a results screen again never duplicates rewards. Extraction ends the endless session. Closing the game mid-run keeps previously saved progress but does not award unfinished-run XP.

## Achievements and account perks

Twelve achievements cover lifetime kills, survival, bosses, wins, collection size and endless survival. Each awards points once, shared across all classes. Counters begin with this update; unavailable prior run history is not invented.

Six perks: extra rerolls (3 ranks), banishes (3), skip-for-orb (1), fourth upgrade choice (1), +10% permanent XP per rank (3), and +5 percentage points boss loot per rank (2). Purchase before runs in REWARDS. REFUND ALL PERKS returns every spent point for free. No real currency. Achievement purchases and equipment selections revert if saving fails.

Upgrade cards use rarity borders, original class sigils, descriptions, new-line labels, and optional banish/skip controls. 1–4 selects; R rerolls. Four distinct class upgrade lines lock the build as before; general bonuses do not consume those slots. Up to three skill families can be learned. J shows acquired upgrades and stat totals. Permanent talent trees (12 nodes per class, 72 total) remain pre-run only; T during a run is read-only.

## Save files and development

`%APPDATA%/Godot/app_userdata/Ashfall Survivors/campaign-profile.json` now uses schema 3 with `.bak` recovery. It imports schema 2 and the older relic bank. Do not manually delete these files. `progress.cfg` and `settings.cfg` are retained. Failed result saves block retry/menu/endless until Retry Save succeeds.

`dominion.gd` owns the new menu, collection, zones, achievements, perks, metrics and endless flow. `campaign_data.gd` owns class talents and upgrade lines. Tests are development-only and excluded from the game pack: `test_v5.gd` checks migration, equipment swapping, victory/death/extraction, perk persistence, meters, banishing and reward idempotency. `soak_v5.gd` is an invulnerable six-class stability harness, not a human balance benchmark. `visual_v5.gd` produces development screenshots.

This is an original Godot survivors game inspired by the supplied screenshots. It is not a complete port of the Rust/Bevy repository or the original Azeroth Survivors game. This release does not add Warcraft assets, a 3D character appearance editor, companions, co-op, cosmetic collections or the screenshot's full skill/item catalog. The existing procedural gameplay art remains. Windows-native gameplay still needs testing on the player's PC; automated runtime checks use Godot 4.3 on Linux.