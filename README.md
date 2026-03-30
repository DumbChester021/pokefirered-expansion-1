# pokefirered-expansion (QOL Fork)

A QOL-focused fork of [cawtds/pokefirered-expansion](https://github.com/cawtds/pokefirered-expansion), which itself ports the full [RHH pokeemerald-expansion](https://github.com/rh-hideout/pokeemerald-expansion) feature set to FireRed.

This fork adds **gameplay quality-of-life features** on top of the existing expansion infrastructure.

## Base: cawtds/pokefirered-expansion

The upstream already provides (~95% RHH parity):

- Gen 1–9 Pokémon, moves, abilities, items
- Physical/Special split, Fairy type
- Mega Evolution, Z-Moves, Dynamax, Terastallization
- Battle Frontier, DexNav, Follower Pokémon
- Day/Night system (DNS), RTC
- Configurable level caps, EV caps, scaled EXP
- Type effectiveness & type display in battle
- BW-style Repel/Lure menu
- Gen 4+ whiteout cutscene
- Modern EXP Share (always-on team-wide; see QOL section)
- Reusable TMs (config toggle)
- Running indoors (config toggle)
- Instant text speed
- Decapitalization
- Field moves without HMs
- Test framework, debug menus
- Modular config system (19 headers)

## QOL Features — Status Tracker

### Phase 0: Foundation

| Status | Feature | Description |
|--------|---------|-------------|
| `DONE` | **Merge `no-ql-and-hs` branch** | Remove Quest Log and Help System from upstream. Frees L/R buttons for RHH battle features (move info, catch prompt) and LR box navigation |

### Phase 1: Ports from firered-romhack-1

| Status | Feature | Description |
|--------|---------|-------------|
| `DONE` | **TM Shop Logic** | Shops prevent buying TMs you already own (`GetItemPocket` fix); TM28 (Dig) removed from Celadon Dept Store (redundant); TM10 (Hidden Power) added. TMs are reusable, unsellable, and quantity is hidden (`I_REUSABLE_TMS TRUE`) |
| `DONE` | **Running Shoes from Start** | Running shoes enabled from game start (no item pickup required); Pewter City aide now gives a **White Herb** after Brock instead |
| `DONE` | **Team-Wide Exp Share Always On** | All party members always share EXP after battle — no item required. `IsGen6ExpShareEnabled()` hardcoded to `TRUE`. Route 15 Oak's Aide (50 Pokémon caught) now gives a **Choice Band** instead |
| `DONE` | **Party Menu Memory Leak Fix** | Fix the tilemap buffer leak in `party_menu.c` that was only commented out, not actually fixed |

### Phase 2: New QOL Features

| Status | Feature | Description |
|--------|---------|-------------|
| `DONE` | **IV/EV Checker** | L/R cycles Stats → IVs → EVs on the summary screen skills page. Shows actual numbers (`P_SUMMARY_SCREEN_IV_EV_INFO TRUE`, `P_SUMMARY_SCREEN_IV_EV_VALUES TRUE`) |
| `DONE` | **Trade Evolutions Without Trading** | Pure trade evos (Alakazam, Machamp, Gengar, Golem, etc.) use the **Linking Cord** item instead. Held-item trade evos (Metal Coat, Electirizer, etc.) are usable directly from the bag (`I_USE_EVO_HELD_ITEMS_FROM_BAG TRUE`). Nat Dex evolution block already removed. |
| `DONE` | **Evo Items at Celadon Dept Store 4F** | All evolution stones (incl. Gen 4–8 stones), Linking Cord, and all held-item trade evolution items (Metal Coat, King's Rock, Dragon Scale, Upgrade, Dubious Disc, Electirizer, Magmarizer, Protector, Prism Scale, Reaper Cloth, Deep Sea Tooth/Scale, Razor Claw/Fang) sold on 4F |
| `DONE` | **Expanded Item Bag** | Items pocket expanded from 42 → 64 slots (save-breaking; `BAG_ITEMS_COUNT`) |
| `DONE` | **Auto-Run Toggle** | `FLAG_AUTO_RUN` (flag `0x4AB`): when set, player always runs without holding B. Core movement logic patched in `field_player_avatar.c`. **TODO:** wire L-button press in `field_control_avatar.c` to toggle the flag in-game |
| `TODO` | **LR Box Navigation** | L/R shoulder buttons to switch between PC boxes |
| `TODO` | **Skip Teachy TV** | Yes/No prompt when aide offers Teachy TV — declining skips the tutorial entirely |
| `TODO` | **Normal First Rival Battle** | First rival battle in Oak's Lab behaves as a regular battle (no tutorial special rules) |
| `TODO` | **Item Usage Animation Removal** | Skip/speed up the animation when using items in battle |
| `TODO` | **PSS Icon in Move Selection** | Physical/Special/Status category icon displayed next to moves during attack selection |
| `TODO` | **Held Items Not Consumed** | Competitive-style: consumable held items (berries, Focus Sash, etc.) restored after battle |
| `TODO` | **All Pokémon Obtainable** | Every Pokémon obtainable in-game; evolution blocks (Nat Dex gating) removed |

### Config Defaults

```c
// include/config/item.h
I_REUSABLE_TMS          TRUE           // TMs reusable, unsellable, quantity hidden
// Note: Exp. Share is hardcoded always-on (IsGen6ExpShareEnabled returns TRUE)
// I_EXP_SHARE_FLAG / I_EXP_SHARE_ITEM are unused — no item obtainment in-game

// include/config/battle.h
B_SHOW_EFFECTIVENESS    SHOW_EFFECTIVENESS_SEEN
B_SHOW_TYPES            SHOW_TYPES_CAUGHT

// include/config/caps.h
B_EXP_CAP_TYPE          EXP_CAP_SOFT   // or EXP_CAP_HARD
B_LEVEL_CAP_TYPE        LEVEL_CAP_FLAG_LIST
```

## Building

See [INSTALL.md](https://github.com/rh-hideout/pokeemerald-expansion/blob/upcoming/INSTALL.md) for toolchain setup.

```bash
make -j$(nproc)
```

## Credits

- [pret/pokefirered](https://github.com/pret/pokefirered) — base decompilation
- [rh-hideout/pokeemerald-expansion](https://github.com/rh-hideout/pokeemerald-expansion) — RHH Gen 9 expansion ([credits](https://github.com/rh-hideout/pokeemerald-expansion/wiki/Credits))
- [cawtds/pokefirered-expansion](https://github.com/cawtds/pokefirered-expansion) — FireRed-native RHH expansion port (upstream)
- [Sotomura/pokefirered-rtc](https://github.com/Sotomura/pokefirered/tree/pokefirered-rtc) — RTC implementation
