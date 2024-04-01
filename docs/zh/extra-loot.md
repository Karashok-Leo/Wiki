# 额外战利品 / Extra Loot

## 🪄介绍

这个模组添加了一个新的战利品表谓词（[那是什么？](https://link.mcmod.cn/target/aHR0cHM6Ly96aC5taW5lY3JhZnQud2lraS93LyVFNiU4OCU5OCVFNSU4OCVBOSVFNSU5MyU4MSVFOCVBMSVBOCVFOCVCMCU5MyVFOCVBRiU4RA==)），以便根据实体属性配置战利品。  

此外，你可以通过编辑配置文件快速将额外的战利品添加到现有战利品表中。

## ⚙️配置

### 初始配置文件：

```
{
  "maxHealthWeight": 1.0,
  "armorWeight": 1.0,
  "armorToughnessWeight": 1.0,
  "attackDamageWeight": 1.0,
  "extraLoots": [],
  "extraXpMultiplier": 1.0,
  "extraXpChance": 0.5
}
```

前四个条目确定各种属性的权重。剩下的三个条目用于配置战利品和经验掉落。

## 📜用法示例

显然，JSON 格式文件中不应该有省略号或注释，这个例子中只是为了解释。

### 配置文件：
#### ```extra-loot.json```

```
{
  "maxHealthWeight": 1.0,
  "armorWeight": 2.0,
  "armorToughnessWeight": 2.0,
  "attackDamageWeight": 4.0,
  "extraLoots": [
    {
      "target_regex": "^(?!.*xxx).*entities.*", //Support regular expressions.
      "extra_table": "xxx:common_drop"
    }
  ],
  "extraXpMultiplier": 1.0,
  "extraXpChance": 0.1
}
```

### 数据包：
#### ```data/xxx/loot_tables/common_drop.json```

```
{
  "pools": [
    {
      "conditions": [
        {
          "condition": "minecraft:killed_by_player"
        },
        {
          "condition": "extra-loot:entity_tier",
          "entity": "this",
          "min": 0,
          "max": 50 //for "max" property, -1 means infinity.
        }
      ],
      "entries": [
      ...
      ]
    }
  ]
}
```

### 结果

上述配置表明，将向所有 ID 包含“entities”但不包含“xxx”战利品表添加一个额外的战利品表（“xxx:common_drop”）。

例如，当玩家杀死僵尸时，游戏将对僵尸的最大生命值、护甲、韧性和攻击力进行加权和求和。如果此总和介于 0 和 50 之间，则满足条件，掉落额外的战利品。

此外，当玩家杀死生物时，有一定的几率掉落额外的经验。概率等于配置文件中的“extraXpChance”，额外经验的值等于生物属性的加权和乘以配置文件中的“extraXpMultiplier”。

## 🚨警告

在配置过程中，应尽量避免战利品表中的无限循环/套娃递归。

~~虽然即使你不这样做，也不会有什么严重的后果......~~

```
{
...
  "extraLoots": [
    {
      "target_regex": ".*",
      "extra_table": "minecraft:entities/zombie"
    }
  ]
...
}
```

在这种情况下，目标战利品表包含额外的表。如果你杀死了一个僵尸，僵尸的战利品表会试图掉落自己，这会导致无限递归。

## ✉️反馈

如果有任何Bug或建议，请反馈到Github的Issue页面。
