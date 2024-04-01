# Fusion Smithing

## 🪄Introduction

This mod adds a item - Fusion Smithing Template, which allows you to transfer the nbt (including enchantments) of one item to another item.

![Screenshot](assets/fusion-smithing/smithing.png)

### Loot Table

You can find the fusion smithing template in the treasure chest of the End City.

![Screenshot](assets/fusion-smithing/loot_table.png)

### Recipe

![Screenshot](assets/fusion-smithing/recipe.png)

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