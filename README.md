# BetterShopAuction Dungeon UI Pack

Asset-only companion plugin for [BetterShopAuction](../Better-Shop-AuctionHouse) that
swaps the modern dark/cyan theme for a grim **cracked stone / rusted iron /
torch-amber / blood** dungeon look.

This pack ships:

- A custom `BetterShopCommon.ui` with a dungeon color palette (bleached
  bone, dust-covered stone, torch amber, brass).
- All 45 page-level `.ui` files re-pointing button / container / dropdown /
  input textures from `Textures/ModernShop/...` → `Textures/DungeonShop/...`.
- A texture folder under `Common/UI/Custom/Textures/DungeonShop/` populated
  with stone/iron/torch dungeon art from `dungeon-final/`.
- A mirror of the rarity textures at `Common/UI/Custom/Textures/ModernShop/Rarities/`
  to override the main plugin's hardcoded Java path (`Textures/ModernShop/Rarities/Slot*.png`).

## Installation

1. Build the jar: `gradle jar` — produces
   `build/libs/BetterShopAuctionDungeonUI-1.0.0.jar`.
2. Drop the jar into your server's `mods/` folder alongside
   `BetterShopAuction`.
3. **Do NOT install** any of the other theme packs at the same time —
   they all override the same `.ui` file paths under `Common/UI/Custom/Pages/`
   and will conflict. Pick one theme.
4. Restart the server. Open any shop / auction / market UI in-game and verify
   the new theme appears.

## Color palette (already wired in `BetterShopCommon.ui`)

| Token | Hex | Usage |
|---|---|---|
| `@ColorDefault` | `#d8d2c4` | Bleached bone — main bright text |
| `@ColorDefaultLabel` | `#9a958a` | Dust-covered stone — default labels |
| `@ColorBlueAccent` | `#c08030` | Torch amber (replaces blue accent) |
| `@ColorBlueAccentHovered` | `#e5a248` | Bright torch (hover) |
| `@ColorBlueAccentPressed` | `#8a5020` | Dim torch (pressed) |
| `@ColorGoldHighlight` | `#d4a040` | Brass highlight |
| `@ColorGrayCaption` | `#807868` | Stone caption |
| `@ColorButtonText` | `#e8dfc4` | Warm bone text on buttons |
| `@ColorDisabled` | `#4a4640` | Mossy iron (disabled) |
| `@ColorPlaceholder` | `#6a6258` | Dust placeholder |
| `@ColorBackgroundCode` | `#15151a` | Deep void / dungeon dark |

## Texture mapping (from `dungeon-final/`)

| Destination | Source `dungeon-final/` |
|---|---|
| `DungeonShop/Patches/Container*.png` (6) | `Container*@2x.png` |
| `DungeonShop/Patches/Dropdown*.png` (3) | `Dropdown*@2x.png` (Default + Hovered + Pressed) |
| `DungeonShop/Patches/InputBox*.png` (4) | `InputBox*@2x.png` (4 states) |
| `DungeonShop/Patches/Scrollbar*.png` (4) | `Scrollbar*@2x.png` (background + handle states) |
| `DungeonShop/Patches/Buttons/Primary*.png` (3) | `Buttons/Primary*@2x.png` |
| `DungeonShop/Patches/Buttons/Destructive*.png` (3) | `Buttons/Destructive*@2x.png` |
| `DungeonShop/Patches/Buttons/Disabled.png` (1) | `Buttons/Disabled@2x.png` |
| `DungeonShop/Patches/Buttons/Secondary*.png` (3) | `Buttons/Action1*@2x.png` |
| `DungeonShop/Patches/Buttons/Tertiary{,_Hovered,_Pressed,_Active}.png` (4) | `Buttons/Action2*@2x.png` |
| `DungeonShop/BuyButton/Buy*.png` (3) | `Buttons/Action3*@2x.png` |
| `DungeonShop/SellButton/Sell*.png` (3) | `Buttons/Action4*@2x.png` |
| `DungeonShop/Decorations/ContainerDecoration{Top,Bottom}.png` (2) | `ContainerDecoration{Top,Bottom}@2x.png` |
| `DungeonShop/CheckBox/{CheckBoxFrame,Checkmark}.png` (2) | `CheckBoxFrame@2x.png`, `CheckBoxFrameChecked@2x.png` |
| `DungeonShop/Slider/{SliderBackground,SliderHandle}.png` (2) | `Slider*@2x.png` |
| `DungeonShop/Rarities/Slot*.png` (7) | `BlockSelectorSlotBackground@2x.png` (cloned across all rarities) |
| `ModernShop/Rarities/Slot*.png` (7 — Java legacy override) | same as above |

## Conflicts

This plugin and any other BetterShopAuction theme pack
(`BetterShopAuctionExtensionsUI`, `BetterShopAuctionMedievalUI`,
`BetterShopAuctionForestWoodUI`) cannot coexist — they ship the same `.ui`
file paths under `Common/UI/Custom/Pages/`. Install **only one theme pack at
a time**.

## Notes

- The `dungeon-final/` source folder doesn't include explicit Slot rarity
  art (Common, Uncommon, …, Legendary), so all 7 rarity slot frames use
  the same `BlockSelectorSlotBackground@2x.png`. The result is a uniform
  stone slot regardless of item rarity — fits the theme but doesn't
  visually distinguish rarities. Add rarity-specific PNGs later if you
  want differentiation.
- A few non-critical textures (`ContainerCloseButton`,
  `ContainerSectionSeparator`, `DropdownBox`, `DropdownCaret`,
  `InputBinding`) have no matching art in `dungeon-final/` and may need
  to be sourced or painted later.

## License

Same as the parent BetterShopAuction project.
