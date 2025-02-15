这个页面详细介绍了PurpurExtras配置文件中提供的各种配置设置。

## anvil-crushes-blocks

如果启用，将使用块列表。键是要转换的方块材料，值是要转换为的方块材料。在默认配置中，如果铁砧落在鹅卵石方块上，那么该鹅卵石将被转换为沙子。

## anvil-splits-boats

如果启用，从高处将铁砧掉落到装有船只的箱子船上，不会摧毁物品，而是分开船只和箱子并将它们同时掉落。

## anvil-splits-minecarts

如果启用，从高处将铁砧掉落到带有内容（箱子矿车、熔炉矿车等）的矿车上，不会摧毁物品，而是分开矿车和内容并将它们同时掉落。

## block-building-above-nether

### enabled

启用该功能。

### height-limit

玩家在地狱世界中可以建造的最大高度，没有 `purpurextras.netherbuildheightbypass` 权限的玩家无法建造。

### no-permission-message

在尝试在地狱世界中建造超过设定限制时在操作栏中显示的消息。

## blocks

### chorus-flowers-always-drop

使唱诗花总是掉落，无论它们是直接被摧毁还是其他方式。

### shift-right-click-for-invisible-item-frames

潜行右键点击带有物品的物品展示框将使物品展示框变为隐形。需要 `purpurextras.invisibleframes` 权限。

## chat

### escape-commands

允许玩家通过用反斜杠转义以斜杠开头的消息发送到聊天中（`\/command` 将显示为 `/command`）。

### send-sleep-percentage-message

如果启用，将在聊天中发送包含基于 `playersSleepingPercentage` 游戏规则所需睡觉的玩家数量的消息。

## create-suspicious-blocks

如果启用，玩家可以携带物品潜行右键点击沙子和砂砾来创建可疑方块并放入手持物品。手持物品将从玩家手中消失，并作为战利品放入可疑方块中。每个方块只能添加一个物品。

## creeper-squid

乌贼将会像苦力怕一样行动 - 如果在`agro-distance`范围内，在`fuse-ticks` ticks的延迟后爆炸，同时以`velocity`的速度向你移动。爆炸威力/半径也可以通过`explosion-radius`进行配置。

### 启用

启用该功能。

### fuse-ticks

“引线”持续的时间。

### agro-distance

探测范围（方块为单位）。

### explosion-radius

爆炸半径。

### velocity

它朝向玩家移动的速度。

## dispenser

### break-blocks

如果启用了工具类别，从发射器中发出的工具将摧毁其前方的方块。它只会摧毁工具可以摧毁的方块，并且会像使用该工具一样摧毁它们，因此木镐将摧毁钻石矿石，但不会掉落任何物品。

### interact-with-cauldron

如果启用，将允许发射器填充和清空炼药锅。

### puts-discs-in-jukebox

如果启用，发射器将能够插入或交换音乐唱片到唱片机中。

### shears-shear-pumpkin

如果启用，当剪刀被发射并且发射器前方有南瓜时，将使用剪刀，制作雕刻南瓜。

## dye-boss-bars

如果启用，玩家可以通过右键点击带着染料物品的boss来染色boss的生命条。

## furnace

### burn-time

如果启用，乘数字段将用于修改熔炉中燃料燃烧时间。

## gameplay-settings

### cancel-damage-from-pet-owner

如果启用，宠物主人将无法伤害自己的宠物。

### fall-damage-when-jump-boost-applied

切换是否给予具有跳跃提升效果的实体摔落伤害。

### open-iron-doors-with-hand

允许使用手打开铁门，就像打开木门一样。可以通过`purpurextras.openirondoors`权限进行控制（默认为true）。

### open-iron-trapdoors-with-hand

允许使用手打开铁活板门，就像打开木活板门一样。可以通过`purpurextras.openirontrapdoors`权限进行控制（默认为true）。

### respawn-anchor-needs-charges

如果为false，使重生锚永远不会用尽次数。

### run-faster-on-paths

如果`speed-multiplier`值大于0，玩家将获得该数值级别的速度药水效果。这只接受整数值。哪些方块被视为路径可以通过在`path-blocks`列表中列出它们来进行配置。

### spawner-placement-requires-specific-permission

玩家将需要`purpurextras.spawnerplace.<mobtype>`权限来放置该类型的刷怪笼。

## grindstone

### gives-enchants-back

如果启用，并且玩家在磨石中解除附魔物品时背包中有书籍，书籍将被消耗，将从物品中移除的附魔返回给玩家。这样做时不会掉落经验。

## items

### beehive-lore

如果为true，将向捡起的蜂巢添加有关蜜蜂数量和蜂蜜的描述。

## leash-snap

如果启用，当牵引绳由于距离过大而断开时会播放声音。

### pitch

播放声音的音调。这是一个介于-1和1之间的浮点数。

### sound

牵引绳断开时播放的声音。可以在[这里](https://minecraft.wiki/w/Sounds.json)找到声音列表。

### volume

播放声音的音量。这是一个大于0的整数。

## loom

### max-layers

可以添加到旗帜的最大层数。默认情况下为6。客户端可能一次不会显示超过6层。

## lightning-transforms-entities

如果启用，左侧具有类型的实体将被转换为右侧类型的实体。这将覆盖原版的转换。使用原版的mob id来识别怪物。也有特殊情况：

- `killer_bunny` - 凶兔
- `jeb_sheep` - 彩色羊
- `johnny` - 对大多数怪物具有攻击性的报复者
- `toast` - 兔子的特殊变种

## mobs

### sheep

#### jeb-shear-random-color

剪羊毛时，名为`jeb_`的羊将掉落带有随机颜色的羊毛块。

### snow_golem

#### drop-pumpkin-when-sheared

如果设置为false，阻止雪傀儡在被剪毛时当它们头上戴着南瓜时掉落雕刻南瓜。

## protect-blocks-with-loot

使具有战利品表的方块免受破坏。默认情况下，它们可以在潜行时被破坏，但可进行配置。可以通过`purpurextras.lootblockprotectionbypass`权限绕过。可以配置显示的消息。可以配置[消息类型](#message-types)。

## raid-totem-drops

### enabled

如果启用，可以配置围攻中唤魔者掉落图腾的掉落率。

### chance

围攻中唤魔者掉落图腾的几率。这是一个介于0和1之间的浮点数。

## rideables

### mob-needs-to-be-nametagged-to-ride

如果启用，只有被命名标签的生物才能使用Purpur的可骑乘选项骑乘/操纵。

## shields

### cooldown

在用斧头爆击盾牌后的冷却时间（1/20秒）。默认情况下为100 ticks（5秒）。

### damage-reduction

0到1之间的值。这是使用盾牌进行防御提供的伤害减少的百分比。默认情况下，盾牌减少100%的伤害（1.0）。

## stonecutter-damage-filter

如果启用，允许过滤哪些实体类型不会受到石切机对其造成伤害的影响，如果启用了[石切机造成伤害](https://purpurmc.org/docs/Configuration/stonecutter_1) Purpur功能。

## totem

### work-on-void-death

如果启用，不死图腾将在虚空中拯救玩家免于死亡，并将其传送到最后一次接触地面的位置。如果找不到该位置，他们将被传送到世界生成点。

## twerk-to-reduce-burn-time

### amount

减少燃烧时间的百分比。

### chance

减少燃烧时间的twert成功几率。这是一个介于0和1之间的浮点数。

## unlock-all-recipes-on-join

解锁所有可用配方。玩家可以通过拒绝`purpurextras.unlockallrecipesonjoin`权限来豁免。

## use-notarget-permissions

如果启用，拥有`target.bypass.<mojang_mob_name>`权限的玩家不会被该类型的怪物瞄准。

## 消息类型

### CHAT
常规系统聊天消息

### ACTION_BAR
动作栏消息