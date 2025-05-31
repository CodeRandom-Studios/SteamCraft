

# SteamCraft Mod Game Design Document - Expanded Systems

## Overview
This document expands on the systems introduced in the SteamCraft mod for Minecraft Bedrock Edition (1.21.82), built using the stable Beta Scripting API v2 and Custom Block Components v2. The focus remains on creating a steampunk-inspired technology system that feels like a natural extension of Minecraft, utilizing redstone, copper, water, and steam. This expansion details the Kinetic Stage with new blocks and introduces progression mechanics for each stage (Kinetic, Steam, Electric), ensuring a clear tech tree that integrates with vanilla Minecraft progression, including resources from the Overworld, Nether, and End.

---

## Expanded Systems

### Kinetic Stage (Early Game)
The Kinetic Stage is the entry point for SteamCraft, focusing on mechanical energy from Wind Turbines and Water Wheels. These blocks have no GUI to maintain simplicity and align with Minecraft’s tactile, block-based interaction style. The Kinetic Stage emphasizes low-tech, resource-efficient machines that introduce players to automation.

#### New Blocks
##### Crusher
- **Description**: A kinetic-powered machine that crushes single items into processed forms (e.g., ores into dusts, cobblestone into gravel).
- **Functionality**:
  - Input: Accepts one item at a time via hopper or manual placement from an input side.
  - Output: Crushes the item and ejects the result to an output side (configurable with the Wrench).
  - Requires 1 kinetic energy/tps to operate.
  - Processing time: 5 seconds per item.
  - Examples: Iron Ore → Iron Dust (2x yield), Cobblestone → Gravel.
- **Visuals**: A rotating drum with copper gears and stone textures, emitting small dust particles during operation.
- **Mechanics**:
  - Connects to Kinetic Shafts for power input.
  - No GUI; items are inserted/ejected via hoppers or manual interaction.
- **Crafting Recipe**:
  - 4 Stone, 3 Copper Ingots, 2 Iron Ingots.

##### Smelter
- **Description**: A kinetic-powered furnace alternative that uses blaze rods to generate heat for smelting ores and other items.
- **Functionality**:
  - Input: Accepts smeltable items (e.g., ores, raw food) via hopper or manual placement and blaze rods as a heat source.
  - Output: Produces smelted items (e.g., Iron Ore → Iron Ingot) and ejects them to an output side.
  - Requires 1 kinetic energy/tps to spin internal mechanisms, which agitate blaze rods to produce heat.
  - Blaze rods burn for 120 seconds (like in a furnace) and smelt up to 12 items per rod.
- **Visuals**: A copper and iron furnace with spinning wheels and blaze rod slots, emitting fire particles and a faint glow.
- **Mechanics**:
  - Blaze rods are inserted into a dedicated slot (accessible by right-clicking or hopper).
  - Connects to Kinetic Shafts for power.
  - No GUI; relies on physical item insertion/ejection.
- **Crafting Recipe**:
  - 4 Copper Ingots, 2 Iron Ingots, 2 Blaze Rods, 1 Furnace.

##### Kinetic Water Pump
- **Description**: A kinetic version of the Water Pump, designed for early-game fluid transport without electrical power.
- **Functionality**:
  - Extracts water from nearby water sources (3x3x3 area) and outputs it into Fluid Pipes.
  - Requires 0.5 kinetic energy/tps to operate.
  - Can be filled manually with water buckets as an alternative.
  - Output: 0.5 water units/tps (slower than the electric Water Pump).
- **Visuals**: A wooden and copper pump with a rotating crank, emitting water droplets.
- **Mechanics**:
  - Connects to Kinetic Shafts for power.
  - No GUI; water flow is managed via pipe connections.
- **Crafting Recipe**:
  - 4 Wooden Planks, 2 Copper Ingots, 1 Bucket, 1 Iron Ingot.

---

### Steam Stage (Mid Game)
The Steam Stage builds on the Kinetic Stage, introducing steam-powered machines that require water and fuel (via Coal Boiler). This stage enhances efficiency and introduces more complex automation, requiring resources like iron and blaze powder, some of which may come from the Nether.

#### Upgraded Blocks
##### Steam Crusher
- **Description**: An upgraded Crusher that processes items faster and supports multiple items simultaneously.
- **Functionality**:
  - Input: Accepts up to 3 items at a time via hopper or manual placement.
  - Output: Crushes items 2x faster (2.5 seconds per item) with 1.5x yield for ores (e.g., 3 Iron Dust per Iron Ore).
  - Requires steam input (1 steam unit/tps) from a Coal Boiler via Pressure Pipes.
- **Visuals**: Larger copper drum with steam vents and glowing redstone accents.
- **Mechanics**:
  - Connects to Pressure Pipes for steam input and Kinetic Shafts for optional auxiliary power.
  - No GUI; maintains hopper-based interaction.
- **Crafting Recipe**:
  - 1 Crusher, 4 Iron Ingots, 2 Blaze Powder, 2 Redstone Dust.

##### Steam Smelter
- **Description**: An advanced Smelter that uses steam for faster, more efficient smelting.
- **Functionality**:
  - Input: Smeltable items and blaze powder (replacing blaze rods for efficiency).
  - Output: Smelts items 1.5x faster (8 items per 120-second blaze powder burn).
  - Requires 1 steam unit/tps.
- **Visuals**: A reinforced furnace with steam pipes and a brighter glow.
- **Mechanics**:
  - Blaze powder lasts 60 seconds and smelts 8 items.
  - Connects to Pressure Pipes for steam.
- **Crafting Recipe**:
  - 1 Smelter, 3 Iron Ingots, 2 Blaze Powder, 1 Copper Ingot.

##### Steam Water Pump
- **Description**: An upgraded Water Pump with higher output and efficiency.
- **Functionality**:
  - Extracts water at 1 water unit/tps (double the Kinetic Water Pump).
  - Requires 0.5 steam unit/tps.
  - Can operate in larger water sources (5x5x5 area).
- **Visuals**: A larger pump with steam-powered pistons and reinforced copper pipes.
- **Mechanics**:
  - Connects to Pressure Pipes for steam input and Fluid Pipes for water output.
- **Crafting Recipe**:
  - 1 Kinetic Water Pump, 3 Iron Ingots, 2 Blaze Powder.

---

### Electric Stage (Late Game)
The Electric Stage represents the pinnacle of SteamCraft progression, requiring resources from the End (e.g., ender pearls, chorus fruit) and Nether (e.g., netherite scraps). Machines are highly efficient and support large-scale automation.

#### Upgraded Blocks
##### Electric Crusher
- **Description**: A high-efficiency Crusher for mass processing.
- **Functionality**:
  - Input: Accepts up to 8 items at a time.
  - Output: Crushes items in 1 second with 2x yield for ores.
  - Requires 2 energy/tps from a Coal Generator or Steam Turbine.
- **Visuals**: A sleek machine with copper wiring, redstone circuits, and ender pearl inlays.
- **Mechanics**:
  - Connects to Copper Wires for power.
  - No GUI; uses hoppers for high-throughput automation.
- **Crafting Recipe**:
  - 1 Steam Crusher, 2 Netherite Scraps, 2 Ender Pearls, 4 Redstone Dust.

##### Electric Smelter
- **Description**: A high-speed Smelter for industrial-scale production.
- **Functionality**:
  - Input: Smeltable items and blaze powder.
  - Output: Smelts items in 0.5 seconds per item (16 items per 60-second blaze powder burn).
  - Requires 2 energy/tps.
- **Visuals**: A futuristic furnace with glowing ender pearl accents and electric sparks.
- **Mechanics**:
  - Connects to Copper Wires for power.
- **Crafting Recipe**:
  - 1 Steam Smelter, 2 Netherite Scraps, 1 Ender Pearl, 3 Redstone Dust.

##### Electric Water Pump
- **Description**: The most efficient Water Pump for large-scale steam systems.
- **Functionality**:
  - Extracts water at 2 water units/tps from a 7x7x7 area.
  - Requires 1 energy/tps.
- **Visuals**: A high-tech pump with copper and netherite components, emitting electric particles.
- **Mechanics**:
  - Connects to Copper Wires for power and Fluid Pipes for output.
- **Crafting Recipe**:
  - 1 Steam Water Pump, 2 Netherite Scraps, 1 Ender Pearl, 2 Redstone Dust.

---

## Tech Tree Progression
The SteamCraft tech tree is designed to align with Minecraft’s progression, requiring increasingly rare resources as players advance through stages.

### Kinetic Stage
- **Resources**: Overworld materials (wood, stone, copper, iron, redstone).
- **Focus**: Simple automation with Wind Turbines, Water Wheels, and basic machines (Crusher, Smelter, Kinetic Water Pump).
- **Gameplay**: Encourages exploration for ideal Wind Turbine placements (high altitudes, windy biomes) and water sources for Water Wheels.

### Steam Stage
- **Resources**: Overworld materials plus Nether resources (blaze rods, blaze powder).
- **Focus**: Steam-powered efficiency with Coal Boiler and upgraded machines (Steam Crusher, Steam Smelter, Steam Water Pump).
- **Gameplay**: Requires Nether exploration for blaze rods/powder, introducing risk-reward dynamics. Players build more complex pipe networks.

### Electric Stage
- **Resources**: Overworld, Nether, and End resources (netherite scraps, ender pearls, chorus fruit for potential future items).
- **Focus**: Industrial automation with Coal Generator, Steam Turbine, and high-efficiency machines (Electric Crusher, Electric Smelter, Electric Water Pump).
- **Gameplay**: Encourages End exploration for ender pearls and Nether exploration for netherite. Players create large-scale factories with interconnected systems.

---

## Additional Features
- **Redstone Control**: All machines can be toggled or modulated with redstone signals (e.g., comparators read output rates, levers toggle on/off).
- **Visual Feedback**: Each stage has distinct visuals (wood/copper for Kinetic, iron/steam for Steam, netherite/ender for Electric) to reflect progression.
- **Scalability**: Machines can be chained (e.g., multiple Crushers feeding into a single Smelter) and upgraded with rare materials for efficiency boosts.
- **Sound Design**: Kinetic machines clank, Steam machines hiss, and Electric machines hum, enhancing immersion.

---

## Technical Notes
- **Scripting API v2**: Handles item processing, energy/steam/fluid calculations, and redstone interactions.
- **Custom Block Components v2**: Defines block states (e.g., active/inactive, overheating) and connections (pipes, wires, shafts).
- **Performance Optimization**: Batch processing for item and fluid calculations to minimize tick lag in large setups.
- **Compatibility**: Machines integrate with vanilla hoppers, droppers, and redstone for accessibility.

---

## Future Ideas
- **Hybrid Machines**: Machines that accept both kinetic and steam/electric power for flexible setups.
- **Ender-Enhanced Blocks**: Use chorus fruit for teleportation-based item transport in the Electric Stage.
- **Automation Modules**: Add conveyor belts or mechanical arms for advanced item handling.
- **Environmental Interactions**: Machines affected by biome (e.g., Steam Boilers overheat faster in deserts).

