# Fusion Smithing

## 🪄Introduction

This mod adds a item - Fusion Smithing Template, which allows you to transfer the nbt (including enchantments) of one item to another item.

![Screenshot](assets/fusion-smithing/smithing.png)

### Loot Table

You can find the fusion smithing template in the treasure chest of the End City.

![Screenshot](assets/fusion-smithing/loot_table.png)

### Recipe

![Screenshot](assets/fusion-smithing/recipe.png)

## 🪚Recipe

### New Recipe Type

This mod adds a recipe type (`fusion-smithing:smithing_fusion`). The JSON file for a single recipe is as follows:

```
{
  "type": "fusion-smithing:smithing_fusion",
  "template": {
    "item": "fusion-smithing:fusion_smithing_template"
  },
  "base": {
    "tag": "c:boots"
  },
  "addition": {
    "tag": "c:boots"
  }
}
```

The `template` field is the forge template used for the recipe (placed in the template slot, but can be any item, not necessarily a template);
The `base` field is the source item for the NBT data transfer;
The `addition` field is the target item for the NBT data transfer.

### Default Recipes

This mod adds some default recipes, in the form of the example recipe above, containing the tags:

（Require [AutoTag](https://modrinth.com/mod/autotag)）

| Tag             | Items       |
| --------------- | ----------- |
| `c:helmets`     | Helmets     |
| `c:chestplates` | Chestplates |
| `c:leggings`    | Leggings    |
| `c:boots`       | Boots       |
| `c:bows`        | Bows        |
| `c:crossbows`   | Crossbows   |
| `c:shields`     | Shields     |
| `c:tridents`    | Tridents    |

（Require Vanilla or Fabric）

| Tag                  | Items    |
| -------------------- | -------- |
| `minecraft:swords`   | Swords   |
| `minecraft:axes`     | Axes     |
| `minecraft:pickaxes` | Pickaxes |
| `minecraft:shovels`  | Shovels  |
| `minecraft:hoes`     | Hoes     |
| `c:shears`           | Shears   |

## ⚙️Configuration

### The initial configuration file looks like:

```
{  
  "injected_loot_table": "minecraft:chests/end_city_treasure"
}
```

If you don't want the template to appear in the treasure chest of the End City, you can modify the "injected_loot_table" entry to another loot table, or just leave it blank.

### How to adapt to more items?

Just create a datapack to add new recipes.

## ✉️Feedback

If there are any bugs or suggestions, please provide feedback to the issue page.