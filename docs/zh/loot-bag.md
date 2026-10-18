# 战利品袋

## 🪄介绍

又一个战利品袋模组，为魔改而生。

### 版本与安装

| Minecraft | 加载器 | Java | 额外前置模组 |
| --------- | ------ | ---- | ------------ |
| 1.20.1 | Fabric | 17 | Fabric API |
| 1.20.1 | Forge | 17 | 无 |
| 1.21.1 | Fabric | 21 | Fabric API |
| 1.21.1 | NeoForge | 21 | 无 |

请选择与 Minecraft 版本和加载器相符的模组文件。多人游戏时，客户端和服务端都需要安装。

### 使用方式

![image](assets/loot-bag/loot-bag.png)

右键打开预览屏幕。单项和随机战利品袋支持潜行右键快捷开启：主手开启一个，副手开启整组。可选战利品袋需要在界面中选择奖励。

### (单项) 战利品袋

包含单组战利品。

![image](assets/loot-bag/single.png)

### 可选战利品袋

包含多组战利品，你可以选择获取其中一组。

![image](assets/loot-bag/optional.gif)

### 随机战利品袋

包含多组战利品，你可以获取其中随机一组。

![image](assets/loot-bag/random.gif)

## ⚙️配置

自1.2.0起，战利品袋通过数据包定义，不再读取旧版配置文件。升级旧版整合包时，需要将原配置改写为数据包；不再需要BRRP前置。

### 示例数据包

请使用与游戏版本和加载器对应的示例，并保留其中的 `pack.mcmeta`：

- [Fabric 1.20.1](https://github.com/Karashok-Leo/loot-bag/tree/master/example)
- [Forge 1.20.1](https://github.com/Karashok-Leo/loot-bag/tree/forge-1.20.1/example)
- [Fabric 1.21.1](https://github.com/Karashok-Leo/loot-bag/tree/fabric-1.21.1/example)
- [NeoForge 1.21.1](https://github.com/Karashok-Leo/loot-bag/tree/neoforge-1.21.1/example)

数据包的主要目录在以上版本中保持一致：

- 战利品袋定义：`data/<命名空间>/loot-bag/bag/<名称>.json`
- 奖励内容定义：`data/<命名空间>/loot-bag/content/<名称>.json`

其中物品堆栈的格式随 Minecraft 版本变化：1.20.1使用 `id`、`Count` 和可选的 `tag`；1.21.1使用 `id`、`count` 和可选的 `components`。不要直接混用两个版本的物品数据。

如果你是模组开发者，也可以使用模组提供的Provider类生成数据，或扩展战利品袋类型。

### 战利品袋物品与版本迁移

所有战利品袋共用物品ID `loot-bag:loot_bag`，通过袋子标识符引用数据包中的定义。Forge和NeoForge使用的加载器模组ID是 `loot_bag`，但物品和数据包命名空间仍是 `loot-bag`。

安装并启用示例数据包后，可以用以下命令获取其中的单项战利品袋：

Minecraft 1.20.1（Fabric / Forge），标识符保存在NBT字段 `BagId` 中：

```mcfunction
/give @s loot-bag:loot_bag{BagId:"loot-bag:single"}
```

Minecraft 1.21.1（Fabric / NeoForge），标识符保存在自定义数据组件 `loot-bag:bag_id` 中：

```mcfunction
/give @s loot-bag:loot_bag[loot-bag:bag_id="loot-bag:single"]
```

将 `loot-bag:single` 替换为你自己的袋子标识符即可。1.21.1不会读取旧的 `BagId`，也不会读取 `minecraft:custom_data` 中的 `BagId`；升级时需更新相关命令和物品数据。

## ✉️反馈

如果有任何Bug或建议，请反馈到[GitHub Issues](https://github.com/Karashok-Leo/loot-bag/issues)，并注明 Minecraft 版本、加载器和模组版本。
