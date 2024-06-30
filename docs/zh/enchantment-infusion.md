# 魔咒灌注

## 🪄介绍

这个模组添加了一种定向附魔方式， 灵感来源于[新生魔艺](https://www.curseforge.com/minecraft/mc-mods/ars-nouveau)中的附魔灌注配方。

### 如何附魔

本模组添加了两个新方块：附魔灌注台和附魔灌注基座。使用物品右键它们将其放入，空手右键取出其中物品。

你需要像下图这样摆放魔咒灌注台（中心位置）与魔咒灌注基座（周围的位置），然后按照配方在基座上摆放对应的物品（次序不重要），最后在中心的灌注台上摆放你想要附魔的物品，等待若干秒即可完成附魔。

![image](assets/enchantment-infusion/machine.png)

### 合成配方

![image](assets/enchantment-infusion/recipe.png)

## 🪚配方

### 新的配方类型

本模组添加了一种配方类型（`enchantment_infusion:enchantment_infusion`）。配方JSON文件如下：

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
  "level": 5,  
  "mode": "ADD"  
}
```

`enchantment`字段即魔咒的标识符；
`level`字段即魔咒等级；
`ingredients`字段即配方的原料，最多8个，次序不重要（这是无序配方）；
`mode`字段即配方的模式，只能为`ADD`或者`SET`，`ADD`表示将`level-1`等级的魔咒提升至`level`级，而`SET`表示将该（小于`level`级的）魔咒设置为`level`级；
`force`字段即是否忽略魔咒兼容性，强制匹配被附魔物品，这是一个可选字段，默认为`false`。

### 匹配被附魔物品

放置在魔咒灌注台上的物品需要满足特定条件，否则将提示”未找到配方“。

此处的特定条件为：
1. 当`mode`为`ADD`时，被附魔物品上必须已有`level-1`等级的指定魔咒；当`mode`为`SET`时，只需被附魔物品上的指定附魔等级小于`level`；
2. `force`为`true`或者该魔咒兼容被附魔物品（该魔咒可以附在被附魔物品上并且不与已有附魔冲突）。

### 默认配方

本模组添加了一些默认配方，这些配方来源于新生魔艺，但使用了原版物品取代了新生魔艺中的物品：

| 原物品   | 替代品   |
| ----- | ----- |
| 魔源宝石  | 紫水晶碎片 |
| 水之精华  | 水桶    |
| 气之精华  | 幻翼膜   |
| 火之精华  | 烈焰弹   |
| 防护之精华 | 金苹果   |
| 土之精华  | 树叶    |
| 操纵之精华 | 时钟    |
| 荒野尖刺  | 甜浆果   |

## 🧩兼容

本模组内置了REI和EMI的兼容插件，你可以使用两者之一查看本模组的所有配方。

## ✉️反馈

这个模组还没有经过完备的测试，所以目前仍处于Beta阶段。

如果有任何Bug或建议，请反馈到Github的Issue页面。

### 关于模型与纹理

作者：我不擅长美术😫，所以两个新方块的模型与纹理看起来有些劣质，如果你有兴趣为它们制作新的模型和纹理，请联系我！感谢！🥰🥰🥰