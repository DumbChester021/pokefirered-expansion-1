# Wild Encounter Changes

All changes relative to [cawtds/pokefirered-expansion](https://github.com/cawtds/pokefirered-expansion) upstream.

---

## Version Exclusives — Available in Both Versions

All FRLG version exclusives are now obtainable regardless of which version you're playing. The fix strategy: for each route where a version exclusive appears in multiple slots, one slot is kept as the original exclusive and one is replaced with the counterpart.

### Exclusive Pairs Fixed

| FireRed Original | LeafGreen Original |
|------------------|--------------------|
| Ekans / Arbok | Sandshrew / Sandslash |
| Oddish / Gloom / Vileplume | Bellsprout / Weepinbell / Victreebel |
| Psyduck / Golduck | Slowpoke / Slowbro |
| Growlithe / Arcanine | Vulpix / Ninetales |
| Scyther | Pinsir |
| Electabuzz | Magmar |

### Areas Fixed (128 slot changes across 100 tables)

**Kanto Routes:**
- Route 4 — Ekans/Sandshrew (land)
- Routes 5, 6 — Oddish/Bellsprout (land); Psyduck/Slowpoke (water + fishing)
- Route 7 — Oddish/Bellsprout + Growlithe/Vulpix (land)
- Route 8 — Ekans/Sandshrew + Growlithe/Vulpix (land)
- Routes 9, 10, 11 — Ekans/Sandshrew (land)
- Routes 12–15 — Oddish/Bellsprout + Gloom/Weepinbell (land)
- Routes 22, 23 — Ekans/Sandshrew + Arbok/Sandslash (land); Psyduck/Slowpoke (water + fishing)
- Routes 24, 25 — Oddish/Bellsprout (land, 2 of 3 slots each); Psyduck/Slowpoke (water + fishing)

**Dungeons / Special Areas:**
- Pokémon Mansion (1F–B1F) — Growlithe/Vulpix (land)
- Cerulean Cave (1F, B1F) — Psyduck/Slowpoke + Golduck/Slowbro (water + fishing)
- Seafoam Islands (1F, B1F–B4F) — Psyduck/Slowpoke + Golduck/Slowbro (land + water)
- Safari Zone (Center, East, North, West) — Psyduck/Slowpoke (water); **see TODO below for Scyther/Pinsir**

**Cities / Water Routes:**
- Viridian City, Celadon City, Vermilion City, Fuchsia City — Psyduck/Slowpoke (water + fishing)
- Route 6 — Psyduck/Slowpoke (water + fishing)

**Sevii Islands:**
- Two Island Cape Brink — Psyduck/Slowpoke + Oddish/Bellsprout + Golduck/Slowbro (land + water + fishing)
- Three Island Berry Forest, Bond Bridge — Psyduck/Slowpoke (land + water + fishing)
- Four Island, Icefall Cave — Psyduck/Slowpoke (water + fishing)
- Six Island Ruin Valley, Water Path — Psyduck/Slowpoke (land + fishing)

### TODO — Single-Slot Exclusives (not yet fixed)

These areas have only one encounter slot for the version exclusive, so automatic splitting is not possible without removing the original:

| Area | FireRed | LeafGreen |
|------|---------|-----------|
| Safari Zone Center & East | Scyther (1 slot) | Pinsir (1 slot) |
| Seafoam Islands B3F–B4F water | Psyduck (1 slot) | Slowpoke (1 slot) |
| Four Island water | Psyduck (1 slot) | Slowpoke (1 slot) |
| Icefall Cave Back | Psyduck (1 slot) | Slowpoke (1 slot) |
| Five Island Meadow | Psyduck (1 slot) | Slowpoke (1 slot) |
| One Island Kindle/Treasure Beach | Psyduck (1 slot) | Slowpoke (1 slot) |
| Six Island Sevault Canyon | Psyduck (1 slot) | Slowpoke (1 slot) |
| Three Island Berry Forest (land) | Psyduck (1 slot) | Slowpoke (1 slot) |
| Three Island Bond Bridge | Psyduck (1 slot) | Slowpoke (1 slot) |

**Fix:** Replace a lower-priority encounter slot (e.g. a duplicate common species) with the counterpart exclusive in each of these tables.

---

## Encounter Level Notes

Wild Pokémon encounter levels are unchanged from the cawtds upstream. They are compatible with the badge-based hard level cap system (14→21→24→29→43→43→47→50→63).
