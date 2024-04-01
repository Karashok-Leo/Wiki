# 社交距离 / Social Distance

## 🪄介绍

这个模组主要是为整合包而作，防止玩家在远处击杀（赖死）Boss。

## ⚙️配置

### 初始配置文件：

```
{
  "show_message": true,
  "message_overlay": true,
  "distance_config": {
    "minecraft:wither": 32.0,
    "minecraft:warden": 32.0
  }
}
```

在 distance_config 属性中添加条目，冒号前是实体的 ID，冒号后是“社交距离”（float 类型），在该距离范围外玩家无法攻击实体。

![Screenshot](assets/social-distance/screenshot.png)

## ✉️反馈

如果有任何Bug或建议，请反馈到Github的Issue页面。