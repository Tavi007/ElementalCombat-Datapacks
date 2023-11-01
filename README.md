# ElementalCombat-Datapacks

A collection of the datapacks for the elemental combat properties of different mods.

Feel free to use any datapack and change them for your modpack. These datapacks provide a good starting point for any modpack and may only need some slight adjusting depending on your expected difficulty curve.

Currently everything here is still work in progress. It takes some time to write all these files...

## How to use

1. Select the branch with correct version (the main branch is used for development)
2. Click on the folder with mod you are interessted in
3. Download the .zip file
4. Add it to the datapack folder of your modpack save file.

## How to contribute

If you want to write a elemental combat datapack for a mod you really like and share it with the world, then this is the right place for it. Here you will find a description on how you can write your own datapack.
First you need the following folder structure:
	
	data
	 ↳ <mod_id>
	    ↳ combat_properties 
	       ↳ biomes
	       ↳ damage_sources
	       ↳ items
	       ↳ mobs
	       ↳ projectiles

As you can imagine, you will have to add item properties to the items-subfolder, mob properties to the mobs-subfolder and so on.
 
### Items
The filename must be the equal to the name of the item. For example the item minecraft:apple will use the file with the name apple.json. This file will look like this
	
	{
		"attack_style": string,
		"attack_element": string,
		"defense_style": {
			"style1": int,
			"style1": int,
			...
		},
		"defense_element": {
			"element1": int,
			"element1": int,
			...
		}
	}
	
You don't have to specify all values. If they are missing in the file, the mod will fill them with the correct default values. 

### Mobs
Basically the same as the files for items. Again the file must be name accordingly. For example minecraft:pig -> pig.json. The structure is

	{
		"attack_style": string,
		"attack_element": string,
		"defense_style": {
			"style1": int,
			"style1": int,
			...
		},
		"defense_element": {
			"element1": int,
			"element1": int,
			...
		},
		"biome_dependency":boolean
	}

Note that it has the biome_dependency flag. When true, the mob will gain biome specific defense properties.

### Biomes

	{	
		"defense_element":{
			"element1": int,
			...
		},
		"defense_style":{
			"style1": int,
			...
		}
	}

a simple file containing all the values that will be added to a mob, if it has biome_dependency enabled.

### Projectiles

	{	
		"attack_style": "style1",
		"attack_element": "element1"
	}



### Damage Source
The structure is the same as for projectiles, becaus it does not need defense properties

	{	
		"attack_style": "style1",
		"attack_element": "element1"
	}

This is used as last resort, if the damage source is neither a mob nor a projectile. 

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
- Any item, that is able to shoot stuff, has the style "projectile" to better show what it will do.
- Wands are similar, but will have the style "magic"
- Throwable explosives is again similar, but with style "explosion"
