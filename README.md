[English](README.md) | [中文](README.zh.md)

# Victoria 3 War Reparations Infamy Fix

A mod for Victoria 3 (v1.9.8) that provides an adjustable infamy system for war reparations, allowing players to customize infamy generation with faster decay rates and raised thresholds.

## Overview

This mod addresses the imbalance in Victoria 3's war reparations system where demanding war reparations generates excessive infamy compared to other war goals like territorial conquest. The mod provides a flexible, customizable solution that maintains game balance while improving diplomatic strategy options.

## Features

- **Adjustable Infamy Generation**: Lower divide values increase infamy generation, with customizable min/max limits
- **5x Faster Infamy Decay**: Increased yearly decay rate from 5.0 to 25.0
- **War Reparations Optimization**: Reduces excessive infamy from war reparations while maintaining strategic balance

## Installation

### Recommended: Steam Workshop

1. Visit the [Steam Workshop page](https://steamcommunity.com/sharedfiles/filedetails/?id=3567979652)
2. Click "Subscribe" to automatically download and install
3. Launch Victoria 3 - the mod will be automatically enabled
4. Start a new game or load an existing save

**Note**: Steam Workshop installation is the most reliable method. Manual installation may cause the mod to not work properly.

### Manual Installation

1. Download the mod files
2. Place in Victoria 3 mod directory
3. Enable the mod in the game launcher
4. Start a new game or load an existing save

## File Structure

```
common/
├── defines/
│   └── 99_mwid_infamy_fix.txt          # Infamy thresholds and decay rates
└── treaty_articles/
    └── 05_transfer_money.txt            # War reparations infamy calculations
```

## Customization

You can adjust the infamy generation by modifying the following values in `common/treaty_articles/05_transfer_money.txt`:

```txt
divide = 10000  # Lower values = higher infamy
min = 0.5       # Minimum infamy (max: 5)
max = 20        # Maximum infamy (max: 50)
```

## Development Approach

This mod uses a hot-patch approach:

1. **Complete File Override**: The entire `05_transfer_money.txt` treaty article file is copied and modified
2. **Selective Value Changes**: Only specific parameters (`divide`, `min`, `max`) are adjusted while preserving all other functionality
3. **Minimal Impact**: Precisely control war reparations infamy without affecting other diplomatic actions or risking conflicts with other mods.

The core infamy calculation is located in:
```
game/common/treaty_articles/05_transfer_money.txt - money_transfer.wargoal.infamy
```

## Compatibility

- **Game Version**: Victoria 3 v1.9.8
- **Multiplayer**: Synchronized
- **Other Mods**: Compatible with most mods due to high loading priority

## Support

For issues or suggestions, please refer to the mod's discussion page or create an issue in the repository.
