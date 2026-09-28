# mod-biome-effects

<!-- links:start -->
[![Support me on Ko-fi](https://malura.de/assets/badge/kofi.svg)](https://malura.de/go/kofi?ref=mod-biome-effects)
[![Check out my page](https://malura.de/assets/badge/malura.svg)](https://malura.de/go/site?ref=mod-biome-effects)
<!-- links:end -->

An [AzerothCore](https://www.azerothcore.org/) module (WotLK 3.3.5a) that adds zone-based passive
auras for horizontal progression: stepping into a themed zone applies a hidden, passive resistance
buff ("biome"); leaving it swaps in the new biome's buff (or removes it) automatically.

## What it does

Each zone belongs to at most one biome. While a character is in a mapped zone, it carries a hidden,
passive resistance aura for that biome. No buff icon, no client patch, not dispellable.

| Biome    | Resistance | Example zones                         |
|----------|------------|----------------------------------------|
| Frozen   | Frost      | Dun Morogh, Winterspring                |
| Volcanic | Fire       | Searing Gorge, Burning Steppes          |
| Toxic    | Nature     | Swamp of Sorrows, Un'Goro Crater        |
| Arcane   | Arcane     | Netherstorm, Isle of Quel'Danas         |

Two optional trinkets amplify a biome further by granting the matching resistance directly, stacking
with the zone aura.

Works for real players and playerbots alike.

## Configuration

`conf/mod_biome_effects.conf.dist`:

| Key                             | Default | Description                                      |
|----------------------------------|---------|---------------------------------------------------|
| `BiomeEffects.Enable`            | `1`     | Master on/off switch                               |
| `BiomeEffects.IncludeBots`       | `1`     | Playerbots also receive biome auras                |
| `BiomeEffects.ResistanceAmount`  | `15`    | Flat resistance points granted by a biome aura     |

The zone -> biome mapping is documented in the `.conf.dist` file and defined in
`src/BiomeEffects.cpp`.

## Installation

Clone into your AzerothCore `modules/` directory, apply the SQL under
`data/sql/db-world/updates/`, and rebuild the worldserver.

## License

Released under the GNU GPL v2 (or later).
