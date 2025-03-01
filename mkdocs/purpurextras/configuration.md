本页面详细说明 PurpurExtras 配置文件中各项功能的设定参数。

## unlock-all-recipes-on-join
玩家加入时自动解锁所有合成配方。拥有 `purpurextras.unlockallrecipesonjoin` 权限的玩家可豁免此功能。

## creeper-squid
使鱿鱼具备苦力怕特性 - 当玩家进入 `agro-distance` 范围内时，鱿鱼将在 `fuse-ticks` 刻引信时间后爆炸，并以 `velocity` 速度向玩家移动。爆炸威力/半径可通过 `explosion-radius` 调整。

### enabled
是否启用该功能

### fuse-ticks
爆炸引信持续时间（刻）

### agro-distance
敌意侦测范围（方块）

### explosion-radius
爆炸作用半径

### velocity
移动速度值

## protect-blocks-with-loot
对具有战利品表的方块实施防破坏保护。默认情况下潜行状态下可破坏，此行为可配置。拥有 `purpurextras.lootblockprotectionbypass` 权限可绕过保护。提示信息内容可自定义，[消息类型](#message-types) 可配置。

## create-suspicious-blocks
启用后，玩家手持物品潜行右击沙砾类方块可生成可疑方块并将手持物品封存其中。手持物品将消失并转化为可疑方块的战利品内容。每个方块仅能存放一件物品。

## stonecutter-damage-filter
当 [切石机造成伤害](https://purpurmc.org/docs/Configuration/stonecutter_1) 功能启用时，可在此设置不受切石机伤害的实体类型白名单。

## anvil-crushes-blocks
启用后，铁砧从高空坠落到指定方块时将触发方块转化。配置表中键为原始方块材质，值为转化目标材质。默认配置中，铁砧坠落到圆石时会将其转化为沙子。

## use-notarget-permissions
启用后，拥有 `target.bypass.<mojang_mob_name>` 权限的玩家不会被对应生物锁定为攻击目标。

## anvil-splits-minecarts
启用后，铁砧从高空坠落到载物矿车（运输矿车、动力矿车等）时将分离矿车与装载物，使其各自以物品形式掉落，而非直接损毁。

## anvil-splits-boats
启用后，铁砧从高空坠落到储物船时将分离船只与箱子，使其各自以物品形式掉落，而非直接损毁。

## dye-boss-bars
启用后，玩家可用染料右击 Boss 来染色其血条。

## loom

### max-layers
旗帜可添加的最大图案层数。默认6层，客户端可能无法显示超过6层的效果。

## raid-totem-drops

### enabled
是否可配置袭击事件中唤魔者的图腾掉落率

### chance
唤魔者在袭击中掉落图腾的概率（0到1之间的浮点数）

## shields

### damage-reduction
伤害减免系数（0到1之间）。代表盾牌格挡时减免的伤害百分比，默认1.0（完全减免）

### cooldown
斧类暴击盾牌后触发的冷却时间（刻，1刻=0.05秒）。默认100刻（5秒）

## items

### beehive-lore
启用后，采集蜂箱时会显示包含蜜蜂数量和蜂蜜量的物品描述

## lightning-transforms-entities
启用后，左侧实体类型被闪电击中时将转化为右侧实体类型（覆盖原版转化规则）。使用原版生物ID进行识别，特殊案例包括：
- `killer_bunny` - 杀手兔
- `jeb_sheep` - 彩虹羊
- `johnny` - 敌对所有生物的卫道士
- `toast` - 特殊品种兔子

## blocks
## anvil-splits-minecarts

### shift-right-click-for-invisible-item-frames
潜行状态下右击含物品的展示框可使其隐形。需要 `purpurextras.invisibleframes` 权限

### chorus-flowers-always-drop
确保紫颂花在任何破坏方式下都会掉落

## block-building-above-nether

### enabled
是否启用下界建筑高度限制

### height-limit
无 `purpurextras.netherbuildheightbypass` 权限玩家在下界维度可建造的最大高度

### no-permission-message
玩家尝试在下界超限建造时在动作栏显示的消息

## gameplay-settings

### respawn-anchor-needs-charges
设为 false 时，重生锚将无需充能即可无限使用

## blocks

### open-iron-doors-with-hand
允许徒手开启铁门（类似木门）。可通过 `purpurextras.openirondoors` 权限控制（默认开启）

### open-iron-trapdoors-with-hand
允许徒手开启铁活板门（类似木活板门）。可通过 `purpurextras.openirontrapdoors` 权限控制（默认开启）

### spawner-placement-requires-specific-permission
放置刷怪笼需要 `purpurextras.spawnerplace.<生物类型>` 权限

### cancel-damage-from-pet-owner
启用后，宠物主人无法伤害自己的宠物

### fall-damage-when-jump-boost-applied
控制带有跳跃提升效果的实体是否会承受跌落伤害

### run-faster-on-paths
当 `speed-multiplier` 值大于0时，玩家在指定路径方块上会获得对应等级的速度效果。仅接受整数值，路径方块类型可在 `path-blocks` 列表中配置

## chat

### escape-commands
允许玩家通过反斜杠转义发送以斜杠开头的消息（例如输入 `\/command` 将显示为 /command）

### send-sleep-percentage-message
启用后在聊天栏显示基于 playersSleepingPercentage 游戏规则计算的入睡玩家需求数量

## dispenser

### break-blocks
启用工具类别后，发射器发射对应工具可破坏前方方块。仅破坏该工具可采集的方块，并模拟工具采集效果（例如木镐可破坏钻石矿但不掉落物品）

### shears-shear-pumpkin
启用后，发射剪刀时若前方有南瓜会自动雕刻为南瓜头

### interact-with-cauldron
允许发射器与炼药锅进行液体存取交互

### puts-discs-in-jukebox
允许发射器向唱片机放入或更换音乐唱片

## furnace

### burn-time
启用后，通过燃料燃烧时间系数调整熔炉燃料效率

## grindstone

### gives-enchants-back
启用后，玩家在砂轮解除附魔时若有书在物品栏，将消耗书籍返还被移除的附魔（此过程不产生经验）

## leash-snap

### mob-needs-to-be-nametagged-to-ride
启用后，仅有名牌的生物可通过 Purpur 骑乘系统进行骑乘操控

### pitch
牵引绳断裂音效的音调（-1到1之间的浮点数）

### sound
牵引绳断裂时播放的音效（音效列表参见[此处](https://minecraft.wiki/w/Sounds.json)）

### volume
音效播放音量（大于0的整数）

## mobs

### sheep

#### jeb-shear-random-color
剪切名为 jeb_ 的绵羊会掉落随机颜色的羊毛

### snow_golem

#### drop-pumpkin-when-sheared
控制是否允许通过剪切雪傀儡获得其佩戴的雕刻南瓜

## totem

### work-on-void-death
启用后，不死图腾可在虚空致死时生效，将玩家传送到最后接触的实体地面位置。若无法定位则传送至世界出生点

## twerk-to-reduce-burn-time

### amount
通过扭动减少燃烧时间的百分比

### chance
扭动成功减少燃烧时间的概率（0到1之间的浮点数）

## Message types

### CHAT
常规系统聊天消息

### ACTION_BAR
动作栏消息