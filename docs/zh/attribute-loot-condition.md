# 属性战利品条件

## 🪄介绍

这个模组添加了一个新的战利品表条件类型 （[那是什么？](https://minecraft.wiki/w/Predicate)） ，以便根据实体属性配置战利品。

推荐搭配 [RpgDifficulty](https://modrinth.com/mod/rpgdifficulty), [L2 Hostility](https://modrinth.com/mod/l2hostility) 等实现了怪物属性增强的模组一同使用。

## ⚙️配置

### 初始配置文件：

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

这个数组中的条目定义了各种属性的权重。

你可以配置额外的属性，而不仅限于这四个。

## 📜用法示例

显然JSON文件中不应该出现注释，这里只是为了便于解释。

### 数据包:

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

加载这个数据包后，当玩家杀死僵尸时，游戏将对僵尸的最大生命值、护甲、韧性和攻击力进行加权求和。如果此总和大于等于20，则满足条件，掉落一个苹果。

## ✉️反馈

如果有任何Bug或建议，请反馈到Github的Issue页面。