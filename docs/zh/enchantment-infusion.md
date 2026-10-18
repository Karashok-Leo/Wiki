# 魔咒灌注

## 🪄介绍

这个模组添加了一种定向附魔方式， 灵感来源于[新生魔艺](https://www.curseforge.com/minecraft/mc-mods/ars-nouveau)中的附魔灌注配方。

### 版本与安装

| Minecraft | 加载器 | Java | 额外前置模组 |
| --------- | ------ | ---- | ------------ |
| 1.20.1 | Fabric | 17 | Fabric API |
| 1.20.1 | Forge | 17 | 无 |
| 1.21.1 | Fabric | 21 | Fabric API |
| 1.21.1 | NeoForge | 21 | 无 |

请选择与 Minecraft 版本和加载器相符的模组文件。多人游戏时，客户端和服务端都需要安装。

### 如何附魔

本模组添加了两个新方块：附魔灌注台和附魔灌注基座。使用物品右键它们将其放入，空手右键取出其中物品。

你需要像下图这样摆放魔咒灌注台（中心位置）与魔咒灌注基座（周围的位置），然后按照配方在基座上摆放对应的物品（次序不重要），最后在中心的灌注台上摆放你想要附魔的物品，等待若干秒即可完成附魔。

![image](assets/enchantment-infusion/machine.png)

### 合成配方

![image](assets/enchantment-infusion/recipe.png)

## 🪚配方

使用数据包添加或修改配方时，请注意目录随 Minecraft 版本变化：

- 1.20.1：`data/<命名空间>/recipes/<配方名>.json`
- 1.21.1：`data/<命名空间>/recipe/<配方名>.json`

下方的魔咒灌注配方格式适用于这两个版本；简单灌注的输出物品格式需要按版本区分。

### 魔咒灌注

本模组添加了一种配方类型（`enchantment_infusion:enchantment_infusion`）。实例配方JSON文件如下：

```json
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

| 配方字段        | 是否必需 | 说明                             |
| ----------- | ---- | ------------------------------ |
| type        | 必需   | 指定配方类型为附魔灌注                    |
| enchantment | 必需   | 目标魔咒的标识符                       |
| level       | 必需   | 魔咒等级                           |
| ingredients | 必需   | 配方的原料，1至8个，次序不重要（这是无序配方）       |
| input       | 可选   | 需要已有的魔咒，灌注时会消耗该魔咒              |
| force       | 可选   | 是否忽略魔咒兼容性，强制匹配被附魔物品，默认为`false` |

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

### 简单灌注

简单灌注（`enchantment_infusion:simple_infusion`）使用基座上的原料，将中央物品转换为输出物品。下面是仅使用原版物品的自定义配方示例，适用于 Minecraft 1.20.1（Fabric / Forge）：

```json
{
  "type": "enchantment_infusion:simple_infusion",
  "ingredients": [
    {
      "item": "minecraft:redstone"
    },
    {
      "item": "minecraft:iron_ingot"
    }
  ],
  "input": {
    "item": "minecraft:leather_boots"
  },
  "output": {
    "Count": 1,
    "id": "minecraft:iron_boots"
  },
  "copy_nbt": false
}
```

在 Minecraft 1.21.1（Fabric / NeoForge）中，将上例的 `output` 替换为以下内容，其余字段保持不变。数量字段使用小写 `count`，额外物品数据使用 `components`，不再使用 `Count` 和 `tag`：

```json
{
  "id": "minecraft:iron_boots",
  "count": 1
}
```

| 配方字段        | 是否必需 | 说明                                 |
| ----------- | ---- | ---------------------------------- |
| type        | 必需   | 指定配方类型为简单灌注                        |
| ingredients | 必需   | 配方的原料，1至8个，次序不重要（这是无序配方）           |
| input       | 必需   | 中央灌注台的输入原料                         |
| output      | 必需   | 输出物品                               |
| copy_nbt    | 可选   | 是否拷贝输入物品的数据，默认为`true`；1.20.1拷贝NBT，1.21.1拷贝物品组件改动并合并自定义数据 |

## 🧩兼容

以上各版本均内置JEI、REI和EMI兼容插件，可查看魔咒灌注和简单灌注配方。这些配方查看器都是可选的，请安装与 Minecraft 版本和加载器相符的版本。

## ✉️反馈

如果有任何Bug或建议，请反馈到[GitHub Issues](https://github.com/Karashok-Leo/Enchantment-Infusion/issues)，并注明 Minecraft 版本、加载器和模组版本。
