# SteamCraft Mod Development Plan

This development plan outlines the implementation of the SteamCraft mod for Minecraft Bedrock Edition (1.21.82), using the stable Beta Scripting API v2 and Custom Block Components v2. The plan prioritizes tasks based on difficulty (Easy, Medium, Hard) to ensure a structured approach, starting with foundational elements and progressing to complex systems. The goal is to create a mod that feels like a natural extension of Minecraft, focusing on kinetic, steam, and electric stages with intuitive mechanics and a clear tech tree. Tasks are organized to balance development effort, testing, and iteration while respecting the user’s preference to brainstorm ideas rather than generate code.

---

## Development Principles
- **Modularity**: Build systems incrementally to ensure each stage (Kinetic, Steam, Electric) is functional before adding complexity.
- **Minecraft Integration**: Ensure blocks and mechanics align with vanilla aesthetics and systems (e.g., redstone, hoppers).
- **Performance**: Optimize for Bedrock Edition’s performance constraints, minimizing tick lag in large setups.
- **Iterative Testing**: Test each stage for functionality and balance before moving to the next.

---

## Development Plan by Difficulty

### Easy Tasks (Low Complexity, Foundational Mechanics)
These tasks involve basic block creation, simple interactions, and minimal scripting. They establish the core framework for SteamCraft and are critical for early playtesting.

1. **Create Basic Blocks (Kinetic Stage)**
   - **Blocks**: Crusher, Smelter, Kinetic Water Pump, Wind Turbine, Water Wheel, Kinetic Shaft.
   - **Description**: Implement block models, textures, and basic placement/breaking mechanics using Custom Block Components v2.
   - **Tasks**:
     - Define block states (e.g., active/inactive) and crafting recipes.
     - Create rustic textures using wood, copper, and iron to match Minecraft’s aesthetic.
     - Implement simple particle effects (e.g., dust for Crusher, water droplets for Kinetic Water Pump).
   - **Why Easy**: Leverages existing Bedrock block creation tools with minimal scripting for basic functionality.
   - **Estimated Time**: 1–2 weeks for modeling, texturing, and basic integration.
   - **Dependencies**: None.

2. **Implement Item Transport Mechanics**
   - **Description**: Enable Crusher and Smelter to accept and eject items via hoppers or manual placement without a GUI.
   - **Tasks**:
     - Use Scripting API v2 to handle item input/output on designated block faces.
     - Allow Wrench to configure input/output sides.
     - Ensure compatibility with vanilla hoppers and droppers.
   - **Why Easy**: Relies on Bedrock’s existing item transport systems with simple scripting for block interactions.
   - **Estimated Time**: 1 week.
   - **Dependencies**: Basic block implementation.

3. **Kinetic Energy System**
   - **Description**: Create a basic kinetic energy system for Wind Turbine and Water Wheel to power Kinetic Stage blocks.
   - **Tasks**:
     - Define kinetic energy as a numeric value (e.g., 0.5–3 units/tps) using Scripting API v2.
     - Implement Kinetic Shaft as a transmission block to connect power sources to machines.
     - Add environmental effects (e.g., Wind Turbine output varies by height/biome, Water Wheel by water flow).
     - Create basic particle effects (e.g., spinning visuals for shafts).
   - **Why Easy**: Simple numeric system with limited block interactions, using predefined environmental checks.
   - **Estimated Time**: 1–2 weeks.
   - **Dependencies**: Basic block implementation.

4. **Redstone Integration (Basic)**
   - **Description**: Allow Kinetic Stage blocks to interact with redstone signals.
   - **Tasks**:
     - Enable on/off toggling via levers/buttons for Crusher, Smelter, and Kinetic Water Pump.
     - Allow redstone comparators to read block states (e.g., active/inactive).
     - Implement sound effects (e.g., clanking for kinetic machines).
   - **Why Easy**: Leverages vanilla redstone mechanics with minimal scripting for signal detection.
   - **Estimated Time**: 1 week.
   - **Dependencies**: Basic block implementation.

---

### Medium Tasks (Moderate Complexity, System Expansion)
These tasks build on the Easy tasks, introducing more complex interactions like fluid and steam systems, as well as the Steam Stage. They require additional scripting and testing for balance.

5. **Fluid Pipe System**
   - **Description**: Implement Fluid Pipes and Pressure Pipes for water and steam transport.
   - **Tasks**:
     - Create pipe models with copper textures and directional connection states.
     - Use Scripting API v2 to manage fluid flow (water units, steam units) between blocks.
     - Implement valves to control flow direction and prevent backflow.
     - Add visual feedback (e.g., water droplets, steam clouds) to indicate pipe contents.
   - **Why Medium**: Requires networked block interactions and fluid calculations, but builds on existing item transport logic.
   - **Estimated Time**: 2–3 weeks.
   - **Dependencies**: Kinetic Water Pump implementation.

6. **Steam Stage Blocks**
   - **Blocks**: Coal Boiler, Steam Crusher, Steam Smelter, Steam Water Pump.
   - **Description**: Implement steam-powered blocks with upgraded functionality.
   - **Tasks**:
     - Define block models with iron and blaze powder accents.
     - Script steam consumption (e.g., 1 steam unit/tps for Steam Crusher) and overheating mechanics (e.g., red particles if water supply is low).
     - Implement faster processing (e.g., 2.5s for Steam Crusher, 8 items per blaze powder for Steam Smelter).
     - Add crafting recipes requiring Nether resources (blaze powder, blaze rods).
   - **Why Medium**: Involves new resource dependencies and more complex block interactions, but reuses Kinetic Stage mechanics.
   - **Estimated Time**: 3–4 weeks.
   - **Dependencies**: Fluid Pipe System, Kinetic Stage blocks.

7. **Steam Turbine and Coal Generator**
   - **Description**: Implement power generation for the Electric Stage, bridging Steam and Electric systems.
   - **Tasks**:
     - Create models for Coal Generator (furnace-like with copper) and Steam Turbine (spinning blades with steam vents).
     - Script Coal Generator to consume fuel and produce 1 energy/tps.
     - Script Steam Turbine to convert steam (1–5 energy/tps based on pressure) with cooling requirements (e.g., adjacent water blocks).
     - Implement Copper Wire for energy transmission (16-block range).
   - **Why Medium**: Requires energy calculations and new transmission mechanics, but builds on existing fluid and kinetic systems.
   - **Estimated Time**: 2–3 weeks.
   - **Dependencies**: Fluid Pipe System, Steam Stage blocks.

8. **Redstone Integration (Advanced)**
   - **Description**: Enhance redstone control for Steam Stage and early Electric Stage blocks.
   - **Tasks**:
     - Allow comparators to read steam pressure or energy output.
     - Implement redstone-controlled valves for Fluid/Pressure Pipes.
     - Add toggleable modes for Steam Turbine (e.g., low/high output).
   - **Why Medium**: Expands redstone interactions with more complex block states, requiring additional scripting.
   - **Estimated Time**: 1–2 weeks.
   - **Dependencies**: Steam Stage blocks, Steam Turbine, Coal Generator.

---

### Hard Tasks (High Complexity, Advanced Systems)
These tasks involve intricate systems, rare resource integration, and optimization for large-scale setups. They complete the Electric Stage and ensure scalability.

9. **Electric Stage Blocks**
   - **Blocks**: Electric Crusher, Electric Smelter, Electric Water Pump.
   - **Description**: Implement high-efficiency blocks for industrial automation.
   - **Tasks**:
     - Create futuristic models with netherite and ender pearl accents.
     - Script high-throughput mechanics (e.g., 8 items at once for Electric Crusher, 0.5s smelting for Electric Smelter).
     - Implement crafting recipes requiring Netherite Scraps and Ender Pearls.
     - Add electric particle effects and humming sounds.
   - **Why Hard**: Requires complex scripting for high-speed processing and integration with End/Nether resources, plus balancing for late-game progression.
   - **Estimated Time**: 4–5 weeks.
   - **Dependencies**: Steam Turbine, Coal Generator, Copper Wire.

10. **Scalable Systems and Optimization**
    - **Description**: Ensure machines can be chained and perform efficiently in large setups.
    - **Tasks**:
      - Script support for chaining multiple machines (e.g., 3 Crushers feeding 1 Smelter).
      - Optimize fluid/energy calculations using batch processing to reduce tick lag.
      - Implement upgrade mechanics (e.g., copper/iron upgrades for efficiency).
      - Test large-scale setups (e.g., 10+ interconnected blocks) for performance.
    - **Why Hard**: Requires extensive testing and optimization to handle complex player contraptions without crashing Bedrock Edition.
    - **Estimated Time**: 4–6 weeks.
    - **Dependencies**: All blocks, Fluid Pipe System, Copper Wire, Kinetic Shaft.

11. **Tech Tree Progression and Balance**
    - **Description**: Finalize the tech tree with resource progression and gameplay balance.
    - **Tasks**:
      - Balance resource costs (e.g., Overworld for Kinetic, Nether for Steam, End for Electric).
      - Adjust machine outputs (e.g., Electric Crusher yields vs. Kinetic Crusher) to reward progression.
      - Script environmental interactions (e.g., biome effects on Wind Turbine, overheating in deserts).
      - Create progression milestones (e.g., first steam setup, first electric factory).
    - **Why Hard**: Requires iterative playtesting to ensure progression feels rewarding without being overpowered or grindy.
    - **Estimated Time**: 3–4 weeks.
    - **Dependencies**: All blocks and systems.

12. **Polishing and Immersion**
    - **Description**: Add final visual and audio effects to enhance the steampunk aesthetic.
    - **Tasks**:
      - Implement stage-specific visuals (wood/copper for Kinetic, iron/steam for Steam, netherite/ender for Electric).
      - Add dynamic particles (e.g., steam clouds, electric sparks) and sounds (clanks, hisses, hums).
      - Create warning effects for errors (e.g., overheating particles, pipe leaks).
      - Ensure compatibility with vanilla shaders and resource packs.
    - **Why Hard**: Requires extensive asset creation and scripting for dynamic effects, plus optimization for performance.
    - **Estimated Time**: 3–4 weeks.
    - **Dependencies**: All blocks and systems.

---

## Development Timeline
- **Total Estimated Time**: ~20–26 weeks (5–6.5 months), assuming a small team or solo developer working part-time.
- **Phase 1: Easy Tasks (Weeks 1–4)**:
  - Complete Kinetic Stage blocks, item transport, kinetic energy system, and basic redstone integration.
  - Deliverable: Playable Kinetic Stage with basic automation.
- **Phase 2: Medium Tasks (Weeks 5–12)**:
  - Implement Fluid Pipe System, Steam Stage blocks, Steam Turbine, Coal Generator, and advanced redstone integration.
  - Deliverable: Functional Steam Stage with pipe networks and early Electric Stage power generation.
- **Phase 3: Hard Tasks (Weeks 13–26)**:
  - Complete Electric Stage blocks, scalable systems, tech tree balance, and polishing.
  - Deliverable: Fully functional mod with all stages, optimized for large setups and immersive aesthetics.

---

## Testing and Iteration
- **Alpha Testing (After Phase 1)**: Test Kinetic Stage for basic functionality, hopper compatibility, and performance.
- **Beta Testing (After Phase 2)**: Test Steam Stage for pipe networks, steam mechanics, and balance with Kinetic Stage.
- **Final Testing (After Phase 3)**: Test full tech tree, large-scale setups, and edge cases (e.g., extreme biome conditions).
- **Community Feedback**: Release beta versions to Bedrock Edition modding communities for balance and bug reports.

---

## Risk Mitigation
- **Performance Issues**: Prioritize batch processing and limit networked block updates to prevent lag.
- **Complexity Creep**: Focus on core mechanics before adding optional features (e.g., vehicles, conveyors).
- **Resource Balance**: Playtest resource costs to ensure accessibility for casual players while rewarding exploration.
- **API Limitations**: Monitor Beta Scripting API v2 updates for potential changes and test compatibility early.

---

## Future Considerations
- **Optional Features**: Brainstorm additional machines (e.g., conveyor belts, steam-powered minecarts) after core systems are stable.
- **Multiplayer Support**: Test for synchronization issues in multiplayer Bedrock worlds.
- **Community Mod Integration**: Explore compatibility with other Bedrock addons for expanded gameplay.