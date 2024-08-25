# Attribute Loot Condition

## 🪄Introduction

This mod has added a new type of loot table condition ([What is that?](https://minecraft.wiki/w/Predicate)) so that you can configure the loot based on entity attributes.

Recommended to use with [RpgDifficulty](https://modrinth.com/mod/rpgdifficulty), [L2 Hostility](https://modrinth.com/mod/l2hostility) and other mods that implement monster attribute scaling.

## ⚙️Configuration

### The initial configuration file looks like:

### ```(config/attribute_loot_condition.json)```

```
{
  "attributeWeights": [
    {
      "attribute": "minecraft:generic.max_health",
      "weight": 1.0
    },
    {
      "attribute": "minecraft:generic.armor",
      "weight": 1.0
    },
    {
      "attribute": "minecraft:generic.armor_toughness",
      "weight": 1.0
    },
    {
      "attribute": "minecraft:generic.attack_damage",
      "weight": 1.0
    }
  ]
}
```

The entries in this array determine the weights of various attributes.

You can configure addtional attributes, not just limited to these four.

## 📜Example Usage

It is obvious that there should be no comments in the JSON format file, and this case is only for the sake of explanation.

### Datapack:

### ```data/minecraft/loot_tables/entities/zombie.json```

```
{
    "pools": [
        {
            "rolls": 1,
            "entries": [
                {
                    "type": "item",
                    "name": "minecraft:apple"
                }
            ],
            "conditions": [
                {
                    "condition": "attribute_loot_condition:attribute_weighted_sum",
                    "entity": "this",
                    "min": 20,
                    "max": 0  // Not greater than 0 means canceling this check
                }
            ]
        }
    ]
}
```

After loading this datapack, when a player kills a zombie, the game will weight and sum the maximum health, armor, armor toughness, and attack damage of the zombie. If this sum is not less than 20, then the condition is met.

## ✉️Feedback

If there are any bugs or suggestions, please provide feedback to the issue page.