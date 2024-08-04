# 额外战利品

## 🪄介绍

这个模组主要是为整合包而作，用于快速向已存在的战利品表注入新的战利品。

## ⚙️配置

### 初始配置文件：

```
{
  "patches": []
}
```

本模组通过`config/loot-patcher.json`文件配置。默认情况下，本模组不会对任何战利品表做注入操作。

本模组兼容了ModMenu，你可以安装它以在游戏内通过配置屏幕配置本模组。修改配置后需要重新加载数据包（游戏内输入`/reload`指令）以应用修改。

## 📜用法示例

显然，JSON 格式文件中不应该有省略号或注释，这个例子中只是为了解释。

### 配置文件：
#### ```loot-patcher.json```

```
{
	"patches": [
	    {
		    "target_tables": [
			    "minecraft:chests/ancient_city",
			    "^(?!.*xxx).*entities.*" //Support regular expressions.
			],
		    "extra_tables": [
			    "xxx:entities/common_drop",
			    "xxx:entities/rare_drop"
			]
	    },
	    {
		    "target_tables": ...
		    "extra_tables": ...
		},
		...
	]
}
```

### 结果

上述配置表明，将向ID为`minecraft:chests/ancient_city`的战利品表以及所有 ID 包含`entities`但不包含`xxx`的战利品表添加两个额外的战利品抽取池，池中仅有的抽取项为战利品表类型的抽取项（`xxx:entities/common_drop`和`xxx:entities/rare_drop`）。

## 🚨警告

在配置过程中，应尽量避免战利品表中的无限循环/套娃递归。

~~虽然即使你不这样做，也不会有什么严重的后果......~~

```
{
  "patches": [
    {
      "target_tables": [".*"],
      "extra_tables": ["minecraft:entities/zombie"]
    }
  ]
}
```

在这种情况下，目标战利品表包含要注入的额外的表。如果你杀死了一个僵尸，僵尸的战利品表会试图掉落自己，这会导致无限递归。

## ✉️反馈

如果有任何Bug或建议，请反馈到Github的Issue页面。
