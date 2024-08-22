# Enchantment Infusion

## 🪄Introduction

This mod adds a directional enchanting method, inspired by the Enchanting Apparatus recipes from [Ars Nouveau](https://www.curseforge.com/minecraft/mc-mods/ars-nouveau).

### How to enchant ?

Two new blocks have been added to: the Enchantment Infusion Table and the Enchantment Infusion Pedestal. Use item to right-click them to put it in, and empty-handed right-click to remove item from them.

You need to place a enchantment infusion table (centre position) and enchantment infusion pedestals (surrounding position) like the picture below, then place the corresponding items on the pedestals according to the recipe (the order doesn't matter), and finally place the item you want to enchant on the infusion table in the centre, and wait for seconds for it to finish enchanting.

![image](assets/enchantment-infusion/machine.png)

### 合成配方

![image](assets/enchantment-infusion/recipe.png)

## 🪚Recipe

### New Recipe Type

This mod adds a recipe type (`enchantment_infusion:enchantment_infusion`). The JSON file for a single recipe is as follows:

```
{
  "type": "enchantment_infusion:enchantment_infusion",
  "enchantment": "minecraft:efficiency",
  "force": false,
  "ingredients": [
    {
      "item": "minecraft:redstone_block"
    },
    {
      "item": "minecraft:redstone_block"
    },
    {
      "item": "minecraft:diamond_pickaxe"
    },
    {
      "item": "minecraft:diamond_shovel"
    },
    {
      "item": "minecraft:amethyst_shard"
    },
    {
      "item": "minecraft:amethyst_shard"
    },
    {
      "item": "minecraft:lapis_block"
    },
    {
      "item": "minecraft:lapis_block"
    }
  ],
  "input": {
    "enchantment": "minecraft:efficiency",
    "min_level": 4
  },
  "level": 5
}
```

| Field | Required | Description |
| ----- | ----- | ----- |
| type | Required | specify the recipe type as enchantment infusion |
| enchantment | Required | the identifier of the target enchantment |
| level | Required | the level of the target enchantment |
| ingredients  | Required | the ingredients of the recipe, is up to 8, the order does not matter (this is a shapeless recipe) |
| input | Optional | the existing enchantment needed, will be consumed when infused |
| force | Optional | whether to ignore enchantment compatibility and force a match for the item to be enchanted, defaults to `false` |

### Default Recipes

This mod adds some default recipes that are derived from Ars Nouveau, but use vanilla items instead of those in Ars Nouveau:

| Original Item        | Replacement      |
| -------------------- | ---------------- |
| Source Gem           | Amethyst Shard   |
| Water Essence        | Water Bucket     |
| Air Essence          | Phantom Membrane |
| Fire Essence         | Fire Charge      |
| Abjuration Essence   | Golden Apple     |
| Earth Essence        | Leaves           |
| Manipulation Essence | Clock            |
| Wilden Spike         | Sweet Berries    |

## 🧩Compatibility

This mod has built-in REI and EMI compatible plug-ins, which means you can use either to view all recipes in this mod.

## ✉️Feedback

This mod has not been fully tested yet, so it is still in Beta.

If there are any bugs or suggestions, please provide feedback to the issue page.

### About models and textures

AUTHOR: I'm not good at art 😫 so the models and textures for the two new blocks look a bit shoddy, if you're interested in making new models and textures for them, please contact me! Thanks! 🥰🥰🥰🥰.