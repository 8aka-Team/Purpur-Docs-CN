
本页面详细介绍了 PurpurExtras 配置文件中可用的各种配置设置。

## anvil-crushes-blocks
启用后，将使用方块转换列表。键代表原始方块材质，值代表转换后的目标方块材质。默认配置中，若铁砧坠落到圆石方块上，该圆石将被转化为沙子。

## anvil-splits-boats
启用后，当从高处掉落铁砧砸中储物船（物品形态）时，不会摧毁该物品，而是将船与储物箱分离并分别掉落。

## anvil-splits-minecarts
启用后，当从高处掉落铁砧砸中带有内容的矿车（如储物矿车、动力矿车等，物品形态）时，不会摧毁该物品，而是将矿车与其内容物分离并分别掉落。

## block-building-above-nether
### enabled
启用本功能。

### height-limit
无 `purpurextras.netherbuildheightbypass` 权限的玩家在地狱维度可建造的最大高度限制。

### no-permission-message
玩家在地狱维度尝试超越建造高度限制时，动作栏显示的无权限提示信息。

## blocks
### chorus-flowers-always-drop
确保紫颂花无论是否被直接破坏都会掉落。

### shift-right-click-for-invisible-item-frames
潜行时右键点击带有物品的物品框可使其隐形。需要 `purpurextras.invisibleframes` 权限。

## chat
### escape-commands
允许玩家通过反斜杠转义发送以斜杠开头的消息（例如输入 `\/command` 将在聊天中显示为 `/command`）。

### send-sleep-percentage-message
启用后，根据 `playersSleepingPercentage` 游戏规则在聊天中发送所需睡眠玩家数量的提示信息。

## create-suspicious-blocks
启用后，玩家可潜行右键点击沙砾或沙子方块（手持物品时）生成可疑方块，并将手持物品作为战利品存入其中。每块可疑方块仅能存入一件物品，手持物品会被消耗。

## creeper-squid
鱿鱼将具备苦力怕行为：若玩家进入 `agro-distance` 范围内，鱿鱼将在 `fuse-ticks` 刻的引信时间后爆炸，并以 `velocity` 速度向玩家移动。爆炸威力/半径可通过 `explosion-radius` 配置。

### enabled
启用本功能。

### fuse-ticks
爆炸引信的持续时间（单位：游戏刻）。

### agro-distance
鱿鱼的探测范围（单位：方块）。

### explosion-radius
爆炸影响半径。

### velocity
鱿鱼朝向玩家的移动速度。

## dispenser
### break-blocks
若启用某工具类别，发射器发射该工具时会破坏其前方的方块。仅破坏该工具可挖掘的方块，且破坏效果与手持工具相同（例如木镐可破坏钻石矿，但不会掉落物品）。

### interact-with-cauldron
启用后，发射器可操作炼药锅进行填充或清空。

### puts-discs-in-jukebox
启用后，发射器可向唱片机插入或更换音乐唱片。

### shears-shear-pumpkin
启用后，当发射剪刀且前方有南瓜时，剪刀将被使用以雕刻南瓜。

## dye-boss-bars
启用后，玩家可通过右键点击Boss实体使用染料对其血条进行染色。

## furnace
### burn-time
启用后，将通过 `multiplier` 字段调整熔炉燃料的燃烧时长。

## gameplay-settings
### cancel-damage-from-pet-owner
启用后，宠物主人无法对自身宠物造成伤害。

### fall-damage-when-jump-boost-applied
控制具有跳跃提升效果的实体是否承受跌落伤害。

### open-iron-doors-with-hand
允许徒手开启铁门（类似木门）。可通过 `purpurextras.openirondoors` 权限控制（默认启用）。

### open-iron-trapdoors-with-hand
允许徒手开启铁质活板门（类似木活板门）。可通过 `purpurextras.openirontrapdoors` 权限控制（默认启用）。

### respawn-anchor-needs-charges
设为 `false` 时，重生锚将永不耗尽充能。

### run-faster-on-paths
若 `speed-multiplier` 值大于0，玩家在特定路径上会获得对应等级的加速药水效果。仅接受整数值。可通过 `path-blocks` 列表自定义被视为路径的方块。

### spawner-placement-requires-specific-permission
玩家需拥有 `purpurextras.spawnerplace.<生物类型>` 权限方可放置对应生物的刷怪笼。

## grindstone
### gives-enchants-back
启用后，若玩家在砂轮解除物品附魔时背包中有书，书籍将被消耗以返还被移除的附魔（此过程不会产生经验球）。

## items
### beehive-lore
启用后，拾取的蜂巢将显示包含蜜蜂数量与蜂蜜量的描述文本。

## leash-snap
启用后，栓绳因距离过远断裂时会播放音效。

### pitch
音效的音高（浮点数，范围 -1 至 1）。

### sound
栓绳断裂时播放的音效名称。完整音效列表参见[此链接](https://minecraft.wiki/w/Sounds.json)。

### volume
音效播放音量（整数，需大于0）。

## loom

### max-layers
最大可添加至旗帜的图层数量。默认值为6。客户端当前可能无法显示超过6个图层。

## lightning-transforms-entities
若启用，左侧类型的实体将被转化为右侧类型实体。此设置将覆盖原版转化规则。使用原版生物ID识别生物。特殊案例包括：
- `killer_bunny` - 杀手兔
- `jeb_sheep` - 彩虹羊
- `johnny` - 攻击性卫道士
- `toast` - 特殊兔种

## mobs

### sheep

#### jeb-shear-random-color
剪切名为`jeb_`的绵羊将掉落随机颜色的羊毛方块

### snow_golem

#### drop-pumpkin-when-sheared
设为false时，雪傀儡被剪切头戴雕刻南瓜时将不会掉落南瓜

## protect-blocks-with-loot
保护带有战利品表的方块免遭破坏。默认情况下，潜行状态可破坏，可通过配置调整。拥有`purpurextras.lootblockprotectionbypass`权限可绕过保护。可自定义提示消息类型（参见[消息类型](#message-types)）。

## raid-totem-drops

### enabled
启用后，可配置袭击中唤魔者掉落图腾的几率

### chance
袭击中唤魔者掉落图腾的概率（0到1之间的浮点数）

## rideables

### mob-needs-to-be-nametagged-to-ride
启用后，仅被命名的生物可通过Purpur的骑乘设置进行骑乘/操控

## shields

### cooldown
斧暴击盾牌后的冷却时间（单位：tick，1秒=20tick）。默认100tick（5秒）

### damage-reduction
0到1之间的数值。表示盾牌防御时的伤害减免百分比。默认减免100%（1.0）

## stonecutter-damage-filter
启用后，当[石切机造成伤害](https://purpurmc.org/docs/Configuration/stonecutter_1)功能开启时，可过滤特定实体类型不受石切机伤害

## totem

### work-on-void-death
启用后，不死图腾可在虚空死亡中拯救玩家，将其传送至最后触地位置。若未找到有效坐标，则传送至世界重生点

## twerk-to-reduce-burn-time

### amount
减少燃烧时间的百分比

### chance
蹲跳成功减少燃烧时间的概率（0到1之间的浮点数）

## unlock-all-recipes-on-join
玩家加入时解锁所有配方。拥有`purpurextras.unlockallrecipesonjoin`权限的玩家可豁免此功能

## use-notarget-permissions
启用后，拥有`target.bypass.<mojang_mob_name>`权限的玩家不会被该类型生物锁定为目标

## 消息类型

### CHAT
常规系统聊天消息

### ACTION_BAR
动作栏消息