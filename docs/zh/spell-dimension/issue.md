# 已知问题 / Known Issues

- 结构`simply_houses:taiga_inn`的箱子尝试生成不存在的战利品表`luna_structures:chests/taiga_inn/taiga_inn_barrels`
    - [相关链接](https://github.com/Aureljz/SimplyHouses-Forge/issues/3)
- Trinkets崩端
    - 复现步骤: 
        1. 在护符栏位上装备抢夺宝珠A, 添加了一个护符栏位
        2. 在刚添加的护符栏位上装备抢夺宝珠B
        3. 取下抢夺宝珠A, 此时抢夺宝珠B不会自动弹出
        4. 取下抢夺宝珠B, 崩溃
    - [相关链接](https://github.com/emilyploszaj/trinkets/issues/361)
    - 已尝试在0.5.5版本中修复
- 未知来源的大量黄心
    - <del>疑似原因为治疗之环，也许已在0.5.3版本修复</del>
    - 原因仍然未知
- 共振羽毛(破魔掉落)难以获得
    - 已尝试在0.5.5版本中修复，通过调整破魔和法术穿透的机制
- 附魔**盔甲耐久**无效
    - [相关链接](https://github.com/LangYueMc/EquipmentStandard/pull/13)