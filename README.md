# Victoria 3 War Reparations Infamy Fix

A mod for Victoria 3 (v1.9.8) that provides an adjustable infamy system for war reparations, allowing players to customize infamy generation with faster decay rates and raised thresholds.

## Overview

This mod addresses the imbalance in Victoria 3's war reparations system where demanding war reparations generates excessive infamy compared to other war goals like territorial conquest. The mod provides a flexible, customizable solution that maintains game balance while improving diplomatic strategy options.

## Features

- **Adjustable Infamy Generation**: Lower divide values increase infamy generation, with customizable min/max limits
- **5x Faster Infamy Decay**: Increased yearly decay rate from 5.0 to 25.0
- **War Reparations Optimization**: Reduces excessive infamy from war reparations while maintaining strategic balance

## Installation

1. Download the mod files
2. Place in Victoria 3 mod directory
3. Enable the mod in the game launcher
4. Start a new game or load an existing save

## Technical Details

### Infamy Calculation Parameters

The mod modifies three key parameters in the war reparations infamy calculation:

- **divide**: Lower values increase infamy generation (default: 10000)
- **min**: Minimum infamy value (max: 5)
- **max**: Maximum infamy value (max: 50)

### File Structure

```
common/
├── defines/
│   └── 99_mwid_infamy_fix.txt          # Infamy thresholds and decay rates
└── treaty_articles/
    └── 99_mwid_transfer_money.txt      # War reparations infamy calculations
```

### Naming Convention

- Files prefixed with `99_` ensure highest loading priority
- Overrides game files in `game/common/defines/` and `game/common/treaty_articles/`
- Maintains compatibility with other mods

## Customization

You can adjust the infamy generation by modifying the following values in `common/treaty_articles/99_mwid_transfer_money.txt`:

```txt
divide = 10000  # Lower values = higher infamy
min = 0.5       # Minimum infamy (max: 5)
max = 20        # Maximum infamy (max: 50)
```

## Development Background

This mod was created to address the gameplay imbalance where war reparations generated disproportionately high infamy compared to their strategic value. The solution focuses on the `money_transfer` treaty article's infamy calculation, providing a targeted fix that doesn't affect other game systems.

### Key Discovery

The core infamy calculation is located in:
```
game/common/treaty_articles/money_transfer.wargoal.infamy
```

By modifying the `divide`, `min`, and `max` parameters, we can precisely control war reparations infamy without affecting other diplomatic actions.

## Compatibility

- **Game Version**: Victoria 3 v1.9.8
- **Multiplayer**: Synchronized
- **Other Mods**: Compatible with most mods due to high loading priority

## Support

For issues or suggestions, please refer to the mod's discussion page or create an issue in the repository.