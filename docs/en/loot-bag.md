# Loot Bag

## NOTES❗❗❗

In version 1.2.0 I rewrote almost the entire mod.
What's different from before?
1. The mod now no longer depends on any other dependency mod other than the fabric api.
2. It is now configured via datapack instead of config files. (Don't update if you're not ready to rewrite the config file as a datapack!)
3. Every loot bag used to be a new item, this was done to accommodate some operations such as the vanilla recipe output that did not support writing NBT on items. But this practice was costly, introduced BRRP as a dependency, and defied conventional logic. Now all loot bags are the same item, and the loot bag data is stored in the item's NBT tag.
4. The mod is now extensible in code, if you are a mod developer you can generate your datapack using the provider class provided by the mod and even add more loot bag types.

## 🪄Introduction

Another loot bag mod, designed for modpacks.

![image](assets/loot-bag/loot-bag.png)

Right click to open a preview screen.
Right click when sneaking to open the bag directly.

### (Single) Loot Bag

Contains a single set of loot.

![image](assets/loot-bag/single.png)

### Optional Loot Bag

Contains multiple sets of loot, and you can choose to obtain one of them.

![image](assets/loot-bag/optional.gif)

### Random Loot Bag

Contains multiple sets of loot, and you can obtain a random set of them.

![image](assets/loot-bag/random.gif)

## ⚙️Configuration

~~This mod is highly configurable. The config files will be automatically generated as examples.~~
After version 1.2.0, the entire mod underwent a thorough refactoring. Now it is data driven (mostly), and the example data pack can be found [HERE](https://github.com/Karashok-Leo/loot-bag/tree/master/example).

## ✉️Feedback

If there are any bugs or suggestions, please provide feedback to the issue page.