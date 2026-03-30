# Trainer Changes

All trainer changes relative to [cawtds/pokefirered-expansion](https://github.com/cawtds/pokefirered-expansion) upstream.

---

## Global: AI Upgrade

Every trainer in the game upgraded from `AI: Check Bad Move` to full competitive AI:

```
AI: Check Bad Move / Try To Faint / Check Viability / Smart Switching / Smart Mon Choices
```

This affects all trainer classes including Youngsters, Hikers, Lasses, Gym Leaders, Rocket Grunts, Rivals, and Elite Four.

---

## Global: IV Scaling

Trainer IVs normalized from inconsistent vanilla values to a zone-based system keyed to the badge level cap structure (14→21→24→29→43→47→50→63). With team-wide EXP Share always on, every party member trains to the cap — so IV scaling is the primary difficulty lever for regular trainers.

**Zone tiers (by highest mon level on the team):**

| Level Zone | Base IVs | Rationale |
|------------|----------|-----------|
| ≤ 29 (pre-Surge) | 0 | Early game; player builds are unoptimized |
| ≤ 43 (pre-Koga) | 8 | Mid game ramp |
| ≤ 47 (pre-Blaine) | 15 | Late mid-game |
| ≤ 50 (pre-Giovanni) | 20 | Near endgame |
| 51+ | 25 | Post-game / endgame trainers |

**Special overrides:**

| Trainer Type | IVs |
|--------------|-----|
| Gym Leaders | 31 |
| Elite Four | 31 |
| Champion | 31 |
| Boss Giovanni | 30 |
| Rocket Admins | 20 |
| Rival (1st encounter) | 6 |
| Rival (progression) | 6 → 12 → 18 → 24 → 30 |
| Rematch _2 / _3 / _4 | zone + 3 / +6 / +10 |
| Advanced classes (Cooltrainer, Black Belt, Juggler, Psychic) | zone + 5 |

---

## Global: Species Normalization

Duplicate or thematically mismatched Pokémon replaced with more appropriate species throughout. Changes focused on removing non-Kanto placeholder Pokémon from early routes and replacing them with vanilla-feeling alternatives.

---

## Route 24 — Nugget Bridge

Level cap before Misty: **21** (enforced until Misty is defeated).

| Trainer | Vanilla | Modified |
|---------|---------|----------|
| Bug Catcher Cale | Caterpie 10, Weedle 10, Metapod 10, Kakuna 10 | Metapod 14, Kakuna 14, Butterfree 16, Beedrill 16, Venonat 15 |
| Lass Ali | Pidgey 12, Oddish 12, Bellsprout 12 | Pidgey 15, Oddish 16, Bellsprout 15, Jigglypuff 16 |
| Youngster Timmy | Sandshrew 14, Ekans 14 | Sandshrew 16, Ekans 16, **Geodude 17** |
| Lass Reli | Nidoran M 16, Nidoran F 16 | **Nidorino 17**, **Nidorina 17**, Clefairy 16 |
| Camper Ethan | Mankey 18 | Mankey 17, **Machop 18** |
| Rocket Grunt (end) | Ekans 15, Zubat 15 | Zubat 18, Ekans 19, **Koffing 20**, **Raticate 21** |

**Notable threats:**
- Timmy's Geodude hard-counters Bird and Fire types (Rock Throw)
- Rocket Grunt Raticate sits at the Lv 21 level cap — the hardest fight before Misty

---

## Route 25 — Path to Bill

Buffed to provide a proper grinding path before Cerulean Gym. All trainers are Lv 16–18.

| Trainer | Vanilla | Modified |
|---------|---------|----------|
| Hiker Franklin | Machop 15, Geodude 15 | Machop 17, Geodude 17, **Onix 17** |
| Youngster Joey | Rattata 15, Spearow 15 | Rattata 16, Spearow 16, **Nidoran M 17** |
| Hiker Nob | Geodude 13, Pidgey 13, Machop 13, Spearow 13 | Geodude 16, Pidgey 16, Machop 16, Spearow 16, **Onix 17** |
| Hiker Wayne | Onix 17 | Onix 18, **Geodude 18** |
| Youngster Dan | Slowpoke 17 | Slowpoke 17, **Psyduck 18** |
| Picnicker Kelsey | Nidoran M 15, Nidoran F 15 | Nidoran M 16, Nidoran F 16, **Clefairy 17** |
| Camper Flint | Rattata 14, Ekans 14 | Rattata 17, Ekans 17, **Sandshrew 17** |
| Youngster Chad | Ekans 14, Sandshrew 14 | Ekans 17, Sandshrew 17, **Rattata 17** |
| Lass Haley | Oddish 13, Pidgey 13, Tangela 13 | Oddish 17, Pidgey 17, Tangela 17, **Bellsprout 18** |

---

## Cerulean City Gym

| Trainer | Vanilla | Modified |
|---------|---------|----------|
| Swimmer Luis | Horsea 16, Shellder 16 | Horsea 18, Shellder 18, **Poliwag 18** |
| Picnicker Diana | Goldeen 19 | Goldeen 19, **Horsea 19** |

**Notable threats:**
- Luis's Poliwag has Hypnosis — can put a mon to sleep before you switch
- Diana's Horsea opens with Smokescreen, stacking accuracy drops before Misty

---

## Gym Leader Misty

| Vanilla | Modified |
|---------|----------|
| Staryu Lv 18 — Tackle / Harden / Recover / Water Pulse | **Psyduck Lv 18** — Scratch / Confusion / Disable / Water Pulse |
| Starmie Lv 21 — Hydro Pump / Psychic / Ice Beam / Thunderbolt | **Goldeen Lv 20** — Supersonic / Horn Attack / Agility / Waterfall |
| | Starmie Lv 21 — Hydro Pump / Psychic / Ice Beam / Thunderbolt *(unchanged)* |
| Items: Super Potion | Items: Super Potion *(unchanged)* |

**Design notes:**
- Psyduck's **Disable** shuts down repeated moves (punishes Thunderbolt spam from Pikachu)
- Psyduck's **Confusion** pressures Grass-type leads
- Goldeen's **Agility** doubles its Speed mid-fight; **Supersonic** forces confusion before the sweep
- Starmie's coverage (Water / Psychic / Ice / Electric) punishes mono-type teams
