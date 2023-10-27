# ElementalCombat-Datapacks

A collection of the datapacks for the elemental combat properties of different mods.

Feel free to use any datapack and change them for your modpack. These datapacks provide a good starting point for any modpack and may only need some slight adjusting depending on your expected difficulty curve.

## How to use

1. Select the branch with correct version
2. Click on the folder with mod you are interessted in
3. Download the .zip file
4. Add it to the datapack folder of your modpack save file.

## Balancing

Every pack is trying to be balanced around the default setting of the mod. Balancing is rather difficult to do alone, so if you want to propose changes, please do it by opening an issue or making a pull request. In both cases please describe your reasoning for the balance changes.

Here is a rundown on how I usually balance a datapack. In some cases I divert from this list. For example the enchanted forest biome from Twilight Forest will give biome dependent mobs magic style defense.

- Entities should only have defense values up to 100.
- Entities should only rarely have more than 100 defense (Keep in mind, that elemental defense higher than 100 will result in healing instead of damaging).
- Biomes should only have defense values up to 50.
- Biomes should usually only add elemental defense and not style defence
- An armor set gives the following defense values: Helmet = 5, chestplate = 15, leggings = 10 and boots = 5 for every element or style it has.
- I associate certain elements with certain metals. Any armor with this metal gives the associated elemental defense, while any tool has the associated elemental attack. Here is the mapping:
  - Silver=Ice
  - Copper=Fire
  - Electrum=Thunder
  - Bronze=Earth
  - Lead=Darkness
  - Platin/Shiny=Light
  - more to come later
- (Long) swords, axes and hoes/scythes have the style "slash"
- Daggers, spears, tridents and pickaxes have the style "stab"