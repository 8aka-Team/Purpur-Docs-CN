这个页面详细介绍了Purpur在purpur.yml文件中公开的各种配置设置。如果您想了解paper.yml、spigot.yml、bukkit.yml和server.properties中的设置信息，您应该查看它们各自的文档页面。

* [服务器配置（server.properties）](https://minecraft.wiki/w/Server.properties)

* [Bukkit配置（bukkit.yml）](https://bukkit.fandom.com/wiki/Bukkit.yml)

* [Spigot配置（spigot.yml）](https://www.spigotmc.org/wiki/spigot-configuration/)

* [Paper配置（paper.yml）](https://docs.papermc.io/paper/reference/paper-global-configuration)

* [Pufferfish配置（pufferfish.yml）](https://docs.pufferfish.host/setup/pufferfish-fork-configuration/)

???+ warning "警告"
配置值有时会经常更改。这里的信息可能是不完整的。如果您找不到您需要的信息，或者认为有错误，请通过我们的[Discord]({{ social[0].link }})服务器联系我们。

## 全局设置

全局设置会影响服务器上所有世界以及核心服务器功能本身。

### verbose

- **默认值**：false
- **描述**：设置服务器是否在启动时将所有配置值转储到服务器日志中

### config-version

* **无论出于何种原因，请勿更改此项！** Purpur在内部使用它来帮助自动更新您的配置

### command

* #### uptime
    * ##### format
        - **默认值**："&lt;days>&lt;hours>&lt;minutes>&lt;seconds>"
        - **描述**：`<uptime>`占位符在[`uptime-command-output`](#uptime-command-output)中使用的格式
    * ##### day
        - **默认值**："％02d 天，"
        - **描述**：[command.uptime.format](#format)选项中`<day>`占位符的输出
    * ##### days
        - **默认值**："％02d 天，"
        - **描述**：[command.uptime.format](#format)选项中`<days>`占位符的输出
    * ##### hour
        - **默认值**："％02d 小时，"
        - **描述**：[command.uptime.format](#format)选项中`<hour>`占位符的输出
    * ##### hours
        - **默认值**："％02d 小时，"
        - **描述**：[command.uptime.format](#format)选项中`<hours>`占位符的输出
    * ##### minute
        - **默认值**："％02d 分钟，和"
        - **描述**：[command.uptime.format](#format)选项中`<minute>`占位符的输出
    * ##### minutes
        - **默认值**："％02d 分钟，和"
        - **描述**：[command.uptime.format](#format)选项中`<minutes>`占位符的输出
    * ##### second
        - **默认值**："％02d 秒"
        - **描述**：[command.uptime.format](#format)选项中`<second>`占位符的输出
    * ##### seconds
        - **默认值**："％02d 秒"
        - **描述**：[command.uptime.format](#format)选项中`<seconds>`占位符的输出
* #### gamemode
    * ##### requires-specific-permission
        - 需要[`minecraft.command.gamemode.<gamemode>`](permissions#minecraftcommandgamemodegamemode)权限
        - **默认值**：false
        - **描述**：对于每种游戏模式，设置为true以要求其拥有自己的权限
* #### tpsbar
    * ##### title
      `<tps>` - 当前的TPS

      `<mspt>` - 当前的MSPT

      `<ping>` - 当前的ping

        - **默认值**：&lt;gray>TPS&lt;yellow>:&lt;/yellow> &lt;tps> MSPT&lt;yellow>:&lt;/yellow>
          &lt;mspt> Ping&lt;yellow>:&lt;/yellow> &lt;ping>ms
        - **描述**：服务器运行`/tpsbar`命令时的bossbar格式

    * ##### overlay
        - **默认值**：NOTCHED_20
        - **描述**：设置Bossbar的叠加类型
          可用选项：`PROGRESS`，`NOTCHED_6`，`NOTCHED_10`，`NOTCHED_12`，`NOTCHED_20`
    * ##### fill-mode
        - **默认值**：MSPT
        - **描述**：BossBar应显示什么
          可用选项：`TPS`，`MSPT`，`PING`
    * ##### progress-color
      可用选项：`PINK`，`BLUE`，`RED`，`GREEN`，`YELLOW`，`PURPLE`，`WHITE`
        * ###### good
            - **默认值**：GREEN
            - **描述**：当`fill-mode`为"good"时应显示的颜色
        * ###### medium
            - **默认值**：YELLOW
            - **描述**：当`fill-mode`为"medium"时应显示的颜色
        * ###### low
            - **默认值**：RED
            - **描述**：当`fill-mode`为"low"时应显示的颜色
    * ##### text-color
      `<text>` - 来自[`settings.command.tpsbar.title`](#title)的格式
        * ###### good
            - **默认值**：&lt;gradient:#55ff55:#00aa00>&lt;text>&lt;/gradient>
            - **描述**：当`fill-mode`为"good"时的`<text>`渐变
        * ###### medium
            - **默认值**：&lt;gradient:#ffff55:#ffaa00>&lt;text>&lt;/gradient>
            - **描述**：当`fill-mode`为"medium"时的`<text>`渐变
        * ###### low
            - **默认值**：&lt;gradient:#ff5555:#aa0000>&lt;text>&lt;/gradient>
            - **描述**：当`fill-mode`为"low"时的`<text>`渐变
    * ##### tick-interval
        - **默认值**：20
        - **描述**：bossbar更新频率
* #### rambar
    * ##### title
      `<used>` - 当前使用的内存量。

      `<xmx>` - 设置的最大Xmx。

      `<percent>` - 使用的内存百分比。

        - **默认值**：'"&lt;gray>Ram&lt;yellow>:&lt;/yellow> &lt;used>/&lt;xmx> (&lt;percent>)"'
        - **描述**：服务器运行`/rambar`命令时的bossbar格式

    * ##### overlay
        - **默认值**：NOTCHED_20
        - **描述**：设置Bossbar的叠加类型
          可用选项：`PROGRESS`，`NOTCHED_6`，`NOTCHED_10`，`NOTCHED_12`，`NOTCHED_20`
    * ##### progress-color
      可用选项：`PINK`，`BLUE`，`RED`，`GREEN`，`YELLOW`，`PURPLE`，`WHITE`
        * ###### good
            - **默认值**：GREEN
            - **描述**：当使用的内存量为"good"时应显示的颜色
        * ###### medium
            - **默认值**：YELLOW
            - **描述**：当使用的内存量为"medium"时应显示的颜色
        * ###### low
            - **默认值**：RED
            - **描述**：当使用的内存量为"low"时应显示的颜色
    * ##### text-color
      `<text>` - 来自[`settings.command.tpsbar.title`](#title)的格式
        * ###### good
            - **默认值**：&lt;gradient:#55ff55:#00aa00>&lt;text>&lt;/gradient>
            - **描述**：当使用的内存量为"good"时的`<text>`渐变
        * ###### medium
            - **默认值**：&lt;gradient:#ffff55:#ffaa00>&lt;text>&lt;/gradient>
            - **描述**：当使用的内存量为"medium"时的`<text>`渐变
        * ###### low
            - **默认值**：&lt;gradient:#ff5555:#aa0000>&lt;text>&lt;/gradient>
            - **描述**：当使用的内存量为"low"时的`<text>`渐变
    * ##### tick-interval
      - **默认值**: 20
      - **描述**: Bossbar 应该更新的频率
* #### compass
    * ##### title
        - **默认值**: "S  ·  ◈  ·  ◈  ·  ◈  ·  SW  ·  ◈  ·  ◈  ·  ◈  ·  W  ·  ◈  ·  ◈  ·  ◈  ·  NW  ·  ◈  ·  ◈  ·  ◈  ·  N  ·  ◈  ·  ◈  ·  ◈  ·  NE  ·  ◈  ·  ◈  ·  ◈  ·  E  ·  ◈  ·  ◈  ·  ◈  ·  SE  ·  ◈  ·  ◈  ·  ◈  ·  
          S  ·  ◈  ·  ◈  ·  ◈  ·  SW  ·  ◈  ·  ◈  ·  ◈  ·  W  ·  ◈  ·  ◈  ·  ◈  ·  NW  ·  ◈  ·  ◈  ·  ◈  ·  N  ·  ◈  ·  ◈  ·  ◈  ·  NE  ·  ◈  ·  ◈  ·  ◈  ·  E  ·  ◈  ·  ◈  ·  ◈  ·  SE  ·  ◈  ·  ◈  ·  ◈  ·  "
        - **描述**: 当服务器运行[`/compass`](commands#compass)命令时，bossbar 的格式

    * ##### overlay
        - **默认值**: PROGRESS
        - **描述**:
          设置 Bossbar 的叠加类型
          可用选项: `PROGRESS`, `NOTCHED_6`, `NOTCHED_10`, `NOTCHED_12`, `NOTCHED_20`
    * ##### progress-color
      可用选项: `PINK`, `BLUE`, `RED`, `GREEN`, `YELLOW`, `PURPLE`, `WHITE`
        - **默认值**: GREEN
        - **描述**: Bossbar 的颜色
    * ##### percent
        - **默认值**: 1.0
        - **描述**: Bossbar 的填充程度，范围从 0.0 到 1.0
    * ##### tick-interval
        - **默认值**: 5
        - **描述**: Bossbar 应该更新的频率
* #### hide-hidden-players-from-entity-selector
    - **默认值**: false
    - **描述**: 设置为 true 以在实体选择器中隐藏玩家

### allow-water-placement-in-the-end

- **默认值**: true
- **描述**: 允许在末地放置水

### use-alternate-keepalive

- **默认值**: false
- **描述**: 使用不同的保持连接 ping 超时方法。启用此功能会每秒向玩家发送一个保持连接数据包，只有在 30 秒内没有响应任何数据包时才会踢掉玩家。以任何顺序响应其中任何一个数据包都会保持玩家连接。也就是说，它不会因为在传输过程中某个数据包丢失而踢掉玩家

### tps-catchup

- **默认值**: true
- **描述**: 控制 TPS 追赶

???+ note "注意"
TPS 追赶在任何低于 20 的时间段之后使服务器的 tick 比 20 TPS 快。这是为了尽可能保持平均 TPS 接近 20，但也会带来一系列副作用，例如在卡顿时玩家被怪物瞬间击杀

### server-mod-name
- **默认值**: Purpur
- **描述**: 修改客户端过时或某人打开调试界面 [F3] 时显示的服务器名称

### fix-projectile-looting-transfer
- **默认值**: false
- **描述**: 通过防止战利品应用于由抛射物造成的死亡，解决了 MC-3304。除非插件更改了战利品修饰符，否则不会将战利品应用于死亡

### blast-resistance-overrides
- **默认值**: {}
- **描述**: 修改以更改方块的爆炸抗性。示例:
``` yaml
  blast-resistance-overrides:
    minecraft:oak_leaves: 55
    minecraft:obsidian: 1.5
```

### clamp-attributes
- **默认值**: true
- **描述**: 控制属性是否应该被限制在其值范围内。

### limit-armor
- **默认值**: true
- **描述**: 控制盔甲是否应该限制其减少伤害的能力。

### username-valid-characters
- **默认值**: ^[a-zA-Z0-9_.]*$
- **描述**: 可以在用户名中使用的字符。可通过正则表达式进行配置。

### lagging-threshold
- **默认值**: 19.0
- **描述**: Purpur会跟踪服务器何时出现卡顿，以便根据情况改变行为。当您希望考虑服务器出现卡顿时的阈值。~~目前仅用于mob.villager.brain-ticks设置~~

### fix-network-serialized-items-in-creative
- **默认值**: false
- **描述**: 设置为true以修复由NetworkItemSerializeEvent修改的物品，尽管它们是客户端的，但由于创造性客户端使用创造性库存操作而持久存在。

### disable-give-dropping
- **默认值**: false
- **描述**: 设置为true以禁用/give命令在玩家库存已满时将物品掉落到地面。

### player-deaths-always-show-item
- **默认值**: false
- **描述**: 设置为true以始终显示用于杀死玩家的物品在玩家死亡消息中。

### register-minecraft-debug-commands
- **默认值**: false
- **描述**: 设置为true以注册未使用/隐藏的Minecraft命令。以下命令变得可用（以及它们的`minecraft.command.<command_name>`权限对应项）：`debugconfig`、`serverpack`、`spawn_armor_trims`、`warden_spawn_tracker`、`debugmobspawning`、`debugpath`和`raid`。这个列表可能会根据它们是否在更新的Minecraft版本中被移除或添加而不完整。

### startup-commands
将`Purpur.IReallyDontWantStartupCommands`系统属性设置为`true`以禁用此功能。

- **默认值**: []
- **描述**: 允许您设置一个在服务器启动时运行的控制台命令列表。对于没有访问控制台的服务器所有者来说非常有用。灵感来自[Vintagestory的"StartupCommands"配置选项](https://wiki.vintagestory.at/index.php/Setting_up_a_Multiplayer_Server#Acquiring_server_admin_rights)。

### bee-count-payload
- **默认值**: false
- **描述**: 设置为true以允许客户端使用自定义负载数据包请求蜂箱的蜜蜂数量。（主要由[PurpurClient](https://modrinth.com/mod/PurpurClient)模组使用）

### messages

#### afk-broadcast-away
需要[`kick-if-idle`](#kick-if-idle)设置为`false`

- **默认值**: &lt;yellow>&lt;italic>%s is now AFK
- **描述**: 当用户进入AFK状态时广播的消息（必须将`player-idle-timeout`设置为大于0且[kick-if-idle](#kick-if-idle)设置为false）

#### afk-broadcast-back
需要[`kick-if-idle`](#kick-if-idle)设置为`false`

- **默认值**: &lt;yellow>&lt;italic>%s is no longer AFK
- **描述**: 当用户不再处于AFK状态时广播的消息（必须将`player-idle-timeout`设置为大于0且[kick-if-idle](#kick-if-idle)设置为false）

### afk-broadcast-use-display-name
需要[`kick-if-idle`](#kick-if-idle)设置为`false`
需要[`afk-broadcast-away`](#afk-broadcast-away)或[`afk-broadcast-back`](#afk-broadcast-back)具有非空值

- **默认值**: false
- **描述**: 在AFK广播中使用玩家的显示名称的纯文本版本，而不是他们的用户名。
- **注意**: 此选项不会设置玩家的TAB名称

#### afk-tab-list-prefix
需要[`kick-if-idle`](#kick-if-idle)设置为`false`

- **默认值**: "[AFK] "
- **描述**: 当玩家处于AFK状态时在玩家列表中显示在其名称之前的前缀

#### afk-tab-list-suffix
需要[`kick-if-idle`](#kick-if-idle)设置为`false`

- **默认值**: ""
- **描述**: 当玩家处于AFK状态时在玩家列表中显示在其名称之后的后缀

#### cannot-ride-mob
需要[`allow.ride.<mob_id>`](permissions#allowridemob_id)权限

- **默认值**: &lt;red>You cannot mount that mob
- **描述**: 当有人试图骑乘他们无权骑乘的生物时显示的消息。

#### dont-run-with-scissors
需要启用[`damage-if-sprinting`](#damage-if-sprinting)选项

- **默认值**: &lt;red>&lt;italic>Don't run with scissors!
- **描述**: 当有人试图拿着剪刀跑时显示的动作栏消息

#### ping-command-output
需要[`bukkit.command.ping`](permissions#bukkitcommandping)权限

- **默认值**: &lt;green>%s's ping is %sms
- **描述**: 运行`/ping <user>`时的输出。

#### uptime-command-output
需要[`bukkit.command.uptime`](permissions#bukkitcommanduptime)权限
`<uptime>` - 来自[`<global>.command.uptime.format`](#format)的格式

- **默认值**: &lt;green>Server uptime is &lt;uptime>
- **描述**: 运行`/uptime`命令时显示的消息。

#### demo-command-output
需要[`bukkit.command.demo`](permissions#bukkitcommanddemo)权限

- **默认值**: &lt;green>%s has been shown the demo screen
- **描述**: 使用`/demo`命令为用户启用演示屏幕时显示的消息。

#### credits-command-output
需要[`bukkit.command.credits`](permissions#bukkitcommandcredits)权限

- **默认值**: &lt;green>%s has been shown the end credits
- **描述**: 使用`/credits`命令为用户启用结束信用时显示的消息。

#### tpsbar-command-output
需要[`bukkit.command.tpsbar`](permissions#bukkitcommandtpsbar)权限

- **默认值**: &lt;green>Tpsbar toggled &lt;onoff> for &lt;target>
- **描述**: 使用`/tpsbar`命令为用户启用tpsbar时显示的消息。

#### ram-command-output

- **默认值**: '&lt;green>Ram Usage: &lt;used>/&lt;xmx> (&lt;percent>)'
- **描述**: 当有人使用`/ram`命令时显示的内存使用消息。

#### rambar-command-output

- **默认值**: &lt;green>Rambar toggled &lt;onoff> for &lt;target>
- **描述**: 使用`/rambar`命令为用户启用rambar时显示的消息。

#### unverified-username
- **默认值**: default
- **描述**: 当玩家因为具有未经验证的用户名（用户处于离线模式）而被踢出时显示的消息。设置为"default"将显示默认消息"Failed to verify username!"

#### sleep-skipping-night
- **默认值**: 默认
- **描述**: 当跳过夜晚时出现的动作栏消息。设置为“default”以让客户端使用自己的可翻译组件。设置为空字符串以禁用它。

#### sleeping-players-percent
- **默认值**: 默认
- **描述**: 当玩家正在睡觉时出现的动作栏消息。设置为“default”以让客户端使用自己的可翻译组件。设置为空字符串以禁用它。可用的占位符: `<count>` - 当前正在睡觉的玩家数量, `<total>` - 需要睡觉的玩家总数

#### sleep-not-possible
- **默认值**: 默认
- **描述**: 当玩家尝试睡觉，但`playersSleepingPercentage`游戏规则设置为大于100时出现的动作栏消息。设置为“default”以让客户端使用自己的可翻译组件。设置为空字符串以禁用它。

#### death-message
* ##### stonecutter
    - **默认值**: &lt;player> has sawed themself in half
    - **描述**: 当玩家因站在石切机上而被杀死时出现的死亡消息
* ##### run-with-scissors
    - **默认值**: &lt;player> slipped and fell on their shears
    - **描述**: 当玩家因持剪刀奔跑而被杀死时出现的死亡消息

### 网络
#### kick-for-out-of-order-chat
- **默认值**: true
- **描述**: 将其设置为false以阻止服务器因聊天顺序错误而踢出玩家
#### upnp-port-forwarding
- **默认值**: false
- **描述**: 服务器启动时尝试使用UPnP自动进行端口转发
#### max-joins-per-second
- **默认值**: false
- **描述**: 将其设置为true，使`paper.yml`中的`max-joins-per-tick`设置每秒使用而不是每刻使用

### 方块

#### barrel
* ##### rows
    - **默认值**: 3
    - **描述**: 桶应该拥有的行数。最小值: 1，最大值: 6
#### beehive
* ##### max-bees-inside
    - **默认值**: 3
    - **描述**: 允许在蜂巢/蜜蜂巢内的蜜蜂的最大数量
#### grindstone
* ##### ignored-enchants
    - **默认值**:
        ``` yaml
        - minecraft:binding_curse
        - minecraft:vanishing_curse
        ```
    - **描述**: 不会从磨石上移除的附魔
* ##### remove-attributes
    - **默认值**: false
    - **描述**: 将其设置为true以允许磨石从物品中移除属性
* ##### remove-name-and-lore
    - **默认值**: false
    - **描述**: 将其设置为true以允许磨石从物品中移除名称和描述
#### ender_chest
* ##### six-rows
    - **默认值**: false
    - **描述**: 启用时，末影箱应具有六行的库存空间
* ##### use-permissions-for-rows
    - 需要[`ender_chest.six-rows`](#six-rows)为true
    - 需要[`purpur.enderchest.rows.<number>`](permissions#purpurenderchestrowsnumber)权限
    - **默认值**: false
    - **描述**: 使用权限节点确定行数。启用此设置后，默认情况下，所有玩家都有`six`行，除非使用权限另行指定。

#### crying_obsidian
* ##### valid-for-portal-frame
    - **默认值**: false
    - **描述**: 将其设置为true，以便您可以使用哭泣的黑曜石创建传送门
#### twisting_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大生长年龄
#### weeping_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大生长年龄
#### cave_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大生长年龄
#### kelp
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大生长年龄
#### anvil
* ##### cumulative-cost
    - **默认值**: true
    - **描述**: 如果使用砧时应用累积成本
#### lightning_rod
* ##### range
    - **默认值**: 128
    - **描述**: 更改闪电棒重定向闪电的范围
#### magma-block
* ##### reverse-bubble-column-flow
    - **默认值**: false
    - **描述**: 将其设置为true，使岩浆块放置/生成在水源方块下时，会生成向上的气泡柱而不是向下的气泡柱。
#### soul-sand
* ##### reverse-bubble-column-flow
    - **默认值**: false
    - **描述**: 将其设置为true，使灵魂沙放置/生成在水源方块下时，会生成向下的气泡柱而不是向上的气泡柱。

### 广播

#### 进度

##### only-broadcast-to-affected-player
- **默认值**: false
- **描述**: 仅将进度消息广播到受影响的玩家

#### 死亡

##### only-broadcast-to-affected-player
- **默认值**: false
- **描述**: 仅将死亡消息广播到受影响的玩家

### 记录器

#### suppress-init-legacy-material-errors
- **默认值**: false
- **描述**: 抑制有关插件初始化传统材料API的警告
#### suppress-ignored-advancement-warnings
- **默认值**: false
- **描述**: 抑制有关控制台和日志中未知属性的警告
#### suppress-unrecognized-recipe-errors
- **默认值**: false
- **描述**: 抑制有关尝试加载未识别配方的警告
#### suppress-setblock-in-far-chunk-errors
- **默认值**: false
- **描述**: 抑制检测到在远处区块中使用setBlock引发的错误
#### suppress-library-loader
- **默认值**: false
- **描述**: 抑制与库加载器相关的日志

### 食物属性
- **默认值**: {}
- **描述**: 修改以更改食物属性。以下是一个使用所有设置并附带解释的示例：
``` yaml
spider_eye:                # 要编辑的食物
  nutrition: 2              # 恢复的饱食度点数
  saturation-modifier: 0.8  # 恢复的饱和度。使用的方程式为“nutrition * saturation-modifier * 2”
  is-meat: false            # 将食物标记为狼可食用
  can-always-eat: false     # 标记此食物即使在饱食度已满时也可以食用
  fast-food: false          # 吃食物所需时间（false：32个刻，true：16个刻）
  effects:                  # 在食用时应用的所有效果列表（可以有多个效果）
    poison:                 # 要应用的效果
      duration: 100         # 效果持续时间（以刻为单位）
      chance: 1.0           # 应用效果的概率（0.0 - 1.0）
      visible: true         # 显示粒子
      amplifier: 1          # 效果的放大
      ambient: false        # 将其设置为true以使屏幕上的粒子不那么显眼（类似信标效果）
      show-icon: true       # 在HUD上显示效果图标
``````

### 实体

#### 末影人（Enderman）
* ##### 矮身高（short-height）
    - **默认值**：false
    - **描述**：如果启用，允许末影人适应两格高的空间。由于客户端的碰撞箱保持不变，你仍然可以打到它们的头部。

### 附魔

* ##### 允许在剪刀上使用抢夺附魔（allow-looting-on-shears）
    - **默认值**：false
    - **描述**：允许在剪刀上使用抢夺附魔
* ##### 允许使用不安全的附魔命令（allow-unsafe-enchant-command）
    - **默认值**：false
    - **描述**：允许通过命令将附魔增加到超过最大等级
* ##### 限制等级（clamp-levels）
    - **默认值**：true
    - **描述**：将此设置为`false`允许等级达到`32767`，通过将等级存储为shorts而不是bytes。

???+ note "注意"
客户端不会显示高于`255`的等级

#### 铁砧（Anvil）
* ##### 允许应用不适用的附魔（allow-inapplicable-enchants）
    - **默认值**：false
    - **描述**：允许在通常不适用的工具或盔甲上应用附魔。例如，在镐上使用锋利附魔。
* ##### 允许应用不兼容的附魔（allow-incompatible-enchants）
    - **默认值**：false
    - **描述**：允许同时应用通常不兼容的附魔。例如，保护和火焰保护或时运和精准采集。
* ##### 允许更高等级的附魔（allow-higher-enchants-levels）
    - **默认值**：false
    - **描述**：允许增加附魔超过其最大等级。例如，效率V + 效率V = 效率VI。
* ##### 替换不兼容的附魔（replace-incompatible-enchants）
    - **默认值**：false
    - **描述**：当应用通常不兼容的附魔时，不使用基础物品中的附魔，而是用次要物品中的附魔替换。

## 世界设置

世界设置是基于每个世界的。子节点`default`用于所有没有自己特定设置的世界。

要更清楚地了解配置文件中世界设置部分的内容，请随时阅读Paper的解释：[https://docs.papermc.io/paper/per-world-configuration](https://docs.papermc.io/paper/per-world-configuration)

### 饥饿

#### 饥饿伤害（starvation-damage）
- **默认值**：1.0
- **描述**：饥饿造成的伤害量

### 设置

#### 实体
* #### 共享随机（shared-random）
- **默认值**：true
- **描述**：将此设置为false允许随机数操纵。Paper通过使用共享的（并锁定的）随机源来修补随机数操纵。这带来了性能增益，但技术玩家可能更喜欢关闭此功能以便操纵随机数。

???+ warning "警告"
共享随机设置未经Purpur团队测试，可能存在安全风险。（共享随机设计为多线程安全。撤销此补丁*可能*导致在某些情况下触发ConcurrentModificationExceptions，无论是否使用插件。并增加内存使用。）

### 方块

#### 铁砧（Anvil）
* ##### 使用迷你信息（use-mini-message）
    - 需要[`purpur.anvil.minimessage`](permissions#purpuranvilminimessage)权限
    - **默认值**：false
    - **描述**：允许玩家在铁砧中使用迷你信息标签。
* ##### 允许颜色（allow-colors）
    - 需要[`purpur.anvil.color`](permissions#purpuranvilcolor)权限
    - **默认值**：false
    - **描述**：允许玩家在铁砧中使用颜色代码。
* ##### 用于修复的铁锭数量（iron-ingots-used-for-repair）
    - **默认值**：0
    - **描述**：修复铁砧所需的铁锭数量
* ##### 用于损坏的黑曜石数量（obsidian-used-for-damage）
    - **默认值**：0
    - **描述**：损坏铁砧所需的黑曜石数量
#### 丛林山丁香（Azalea）
* ##### 生长几率（growth-chance）
    - **默认值**：0.0
    - **描述**：丛林山丁香自然生长成树的几率
#### 光束（Beacon）
* ##### 允许在着色玻璃上产生效果（allow-effects-with-tinted-glass）
    - **默认值**：false
    - **描述**：是否允许光束效果在被着色玻璃覆盖时激活
* ##### 效果范围（effect-range）
    * ###### 等级1
        - **默认值**：20
        - **描述**：该等级的效果范围达到的方块数量
    * ###### 等级2
        - **默认值**：30
        - **描述**：该等级的效果范围达到的方块数量
    * ###### 等级3
        - **默认值**：40
        - **描述**：该等级的效果范围达到的方块数量
    * ###### 等级4
        - **默认值**：50
        - **描述**：该等级的效果范围达到的方块数量
#### 床（Bed）
* ##### 爆炸（explode）
    - **默认值**：true
    - **描述**：床是否会爆炸。将其设置为false只会使床消失。
* ##### 睡觉时爆炸（explode-on-villager-sleep）
    - **默认值**：false
    - **描述**：村民睡在床上时，床是否会爆炸。
* ##### 爆炸威力（explosion-power）
    - **默认值**：5.0
    - **描述**：爆炸的爆炸半径。（作为比较，TNT为4.0，充能的苦力怕为6.0）
* ##### 爆炸火焰（explosion-fire）
    - **默认值**：true
    - **描述**：爆炸是否会引起火灾
* ##### 爆炸效果（explosion-effect）
    - **默认值**：BLOCK
    - **描述**：受爆炸影响的方块如何处理。

      ???+ note "可用值"
      所有值都会破坏方块

            - `TNT` - 所有物品都会掉落，除非`tntExplosionDropDecay`游戏规则设置为`true`
            - `MOB` - 一些物品会掉落，除非`mobExplosionDropDecay`游戏规则设置为`false`
            - `BLOCK` - 一些物品会掉落，除非`blockExplosionDropDecay`游戏规则设置为`false`
            - `NONE` - 所有物品都会掉落

#### 蓝冰（Blue Ice）
* ##### 允许生物生成（allow-mob-spawns）
    - **默认值**：true
    - **描述**：设置为false以阻止在蓝冰上生成生物
* ##### 允许积雪形成（allow-snow-formation）
    - **默认值**：true
    - **描述**：设置为false以阻止蓝冰上的积雪形成
#### 仙人掌（Cactus）
* ##### 受邻接固体方块影响（breaks-from-solid-neighbors）
    - **默认值**：true
    - **描述**：仙人掌是否会因其旁边有固体方块而破坏


* ##### 受骨粉影响（affected-by-bonemeal）
    - **默认值**：false
    - **描述**：将其设置为true以使仙人掌可以使用骨粉施肥

#### campfire
* ##### 放置时点燃（lit-when-placed）
    - **默认值**：true
    - **描述**：将其设置为false可阻止放置时点燃篝火
#### cauldron
* ##### 填充几率（fill-chances）
    * ###### 雨水（rain）
        - **默认值**：0.05
        - **描述**：铁锅装满雨水的速度（取决于随机刻）
    * ###### 粉雪（powder-snow）
        - **默认值**：0.1
        - **描述**：铁锅装满粉雪的速度（取决于随机刻）
    * ###### 滴水石水（dripstone-water）
        - **默认值**：0.17578125
        - **描述**：位于下方尖锥滴水石下的铁锅，上方放置水后铁锅装满水的速度（取决于随机刻）
    * ###### 滴水石岩浆（dripstone-lava）
        - **默认值**：0.05859375
        - **描述**：位于下方尖锥滴水石下的铁锅，上方放置岩浆后铁锅装满岩浆的速度（取决于随机刻）
#### chest
* ##### 顶部有实体方块时可打开（open-with-solid-block-on-top）
    - **默认值**：false
    - **描述**：允许即使顶部有实体方块，也能打开箱子
#### composter
* ##### 潜行批量处理（sneak-to-bulk-process）
    - **默认值**：false
    - **描述**：将其设置为true，可以通过手持物品潜行右键点击进行食物/植物物品的批量处理
#### conduit
* ##### 有效环块（valid-ring-blocks）
    - **默认值**：
        ``` yaml
        - minecraft:prismarine
        - minecraft:prismarine_bricks
        - minecraft:sea_lantern
        - minecraft:dark_prismarine
        ```
    - **描述**：可用于建造导管的方块
* ##### 效果范围（effect-distance）
    - **默认值**：16
    - **描述**：导管的有效半径，每七个框架方块增加一次范围
* ##### 生物伤害（mob-damage）
    * ###### 距离（distance）
        - **默认值**：8
        - **描述**：伤害敌对生物的距离（方块）
    * ###### 伤害量（damage-amount）
        - **默认值**：4
        - **描述**：如果敌对生物与水/雨接触，每2秒造成的伤害量
#### coral
* ##### 在非水中死亡（die-outside-water）
    - **默认值**：true
    - **描述**：将其设置为false可使珊瑚在陆地上放置时保持存活
#### dispenser
* ##### 附魔的装备槽中应用诅咒（apply-cursed-to-armor-slots）
    - **默认值**：true
    - **描述**：如果附魔了束缚诅咒，是否应用装备到装备槽中
* ##### 放置铁砧（place-anvils）
    - **默认值**：false
    - **描述**：允许发射器放置铁砧
#### door
* ##### 需要红石（requires-redstone）
    - **默认值**：[]
    - **描述**：允许设置需要红石操作的门（橡木门、云杉门等）
#### dragon_egg
* ##### 传送（teleport）
    - **默认值**：true
    - **描述**：控制龙蛋被击中时是否传送
#### enchantment-table
* ##### lapis保留（lapis-persists）
    - **默认值**：false
    - **描述**：将其设置为true可使青金石留在附魔台槽中，这样你可以将青金石留在台里
#### end-crystal
* ##### 压缩数量（cramming-amount）
    - **默认值**：0
    - **描述**：控制相同碰撞箱空间内可以占据的末影水晶数量。设置为特定数字后，任何额外的水晶都会引发爆炸。

* ##### 无基座（baseless）
    * ###### 爆炸（explode）
        - **默认值**：true
        - **描述**：将其设置为false可阻止水晶爆炸
    * ###### 爆炸威力（explosion-power）
        - **默认值**：6.0
        - **描述**：末影水晶爆炸的威力
    * ###### 爆炸火焰（explosion-fire）
        - **默认值**：false
        - **描述**：将其设置为true可在末影水晶爆炸时放置火焰
    * ###### 爆炸效果（explosion-effect）
        - **默认值**：BLOCK
        - **描述**：受爆炸影响的方块的处理方式。

          ???+ note "可用值"
          所有值都会破坏方块

                - `TNT` - 所有物品都会掉落，除非游戏规则`tntExplosionDropDecay`设置为`true`
                - `MOB` - 一些物品会掉落，除非游戏规则`mobExplosionDropDecay`设置为`false`
                - `BLOCK` - 一些物品会掉落，除非游戏规则`blockExplosionDropDecay`设置为`false`
                - `NONE` - 所有物品都会掉落

* ##### 基座（base）
    * ###### 爆炸（explode）
        - **默认值**：true
        - **描述**：将其设置为false可阻止水晶爆炸
    * ###### 爆炸威力（explosion-power）
        - **默认值**：6.0
        - **描述**：末影水晶爆炸的威力
    * ###### 爆炸火焰（explosion-fire）
        - **默认值**：false
        - **描述**：将其设置为true可在末影水晶爆炸时放置火焰
    * ###### 爆炸效果（explosion-effect）
        - **默认值**：BLOCK
        - **描述**：受爆炸影响的方块的处理方式。

            ???+ note "可用值"
                所有值都会破坏方块

                - `TNT` - 所有物品都会掉落，除非游戏规则`tntExplosionDropDecay`设置为`true`
                - `MOB` - 一些物品会掉落，除非游戏规则`mobExplosionDropDecay`设置为`false`
                - `BLOCK` - 一些物品会掉落，除非游戏规则`blockExplosionDropDecay`设置为`false`
                - `NONE` - 所有物品都会掉落

#### 耕地（farmland）
* ##### 从下方变湿（gets-moist-from-below）
    - **默认值**：false
    - **描述**：允许土壤从正下方的水源变湿
* ##### 使用阿尔法耕地（use-alpha-farmland）
    - **默认值**：false
    - **描述**：如果在耕地正下方放置栅栏或石墙，则阻止耕地被践踏
* ##### 绕过生物破坏（bypass-mob-griefing）
    - **默认值**：false
    - **描述**：设置为true以使耕地绕过生物破坏游戏规则
* ##### 只有玩家踩踏（only-players-trample）
    - **默认值**：false
    - **描述**：如果只有玩家可以踩踏耕地，则设置为true
* ##### 禁用踩踏（disable-trampling）
    - **默认值**：false
    - **描述**：设置为true以完全禁用踩踏
* ##### 踩踏高度（trample-height）
    - **默认值**：-1.0
    - **描述**：设置玩家/实体需要掉落的高度以踩踏耕地

???+ note "注意"
        踩踏高度以方块高度或确切距离为单位。在测试中发现，掉落距离的值非常不一致。测试结果如下：
        设置值 -> 实际需要掉落的距离以踩踏
        1.0 -> 1.25
        1.5 -> 1.75
        2.0 -> 2.25
        2.5 -> 2.87
        3.0 -> 3.5
        3.5 -> 4.25
        4.0 -> 4.25
        4.5 -> 5.0
        5.0 -> 5.87
        5.5 -> 5.87
        6.0 -> 6.75

* ##### 羽毛掉落距离影响踩踏（feather-fall-distance-affects-trampling）
    - **默认值**：false
    - **描述**：设置为true以阻止实体掉落距离等于其羽毛掉落等级加上第一次踩踏所需的额外方块的情况。羽毛掉落1需要掉落3个以上的方块才能踩踏。羽毛掉落2需要4个以上，依此类推。

#### 开花杜鹃（flowering_azalea）
* ##### 生长概率（growth-chance）
    - **默认值**：0.0
    - **描述**：开花杜鹃自然生长成树的概率
#### 熔炉（furnace）
* ##### 使用下方的岩浆（use-lava-from-underneath）
    - **默认值**：false
    - **描述**：允许熔炉通过放置在其下方的岩浆获得无限能量
#### 岩浆（lava）
* ##### 无限所需源数（infinite-required-sources）
    - **默认值**：2
    - **描述**：获得无限岩浆所需的源数量
* ##### 速度
    * ###### 下界
        - **默认值**：10
        - **描述**：物理/流动之间的延迟时间（数值越低速度越快）
    * ###### 非下界
        - **默认值**：30
        - **描述**：物理/流动之间的延迟时间（数值越低速度越快）

#### 岩浆块（magma-block）
* ##### 潜行时受伤（damage-when-sneaking）
    - **默认值**：false
    - **描述**：设置为true以潜行时受伤
* ##### 霜行者时受伤（damage-with-frost-walker）
    - **默认值**：false
    - **描述**：穿着附魔霜行者的靴子行走时受伤

#### 地狱疣（nether_wart）
* ##### 受骨粉影响（affected-by-bonemeal）
    - **默认值**：false
    - **描述**：设置为true以使地狱疣受骨粉影响
#### 观察者（observer）
* ##### 禁用时钟（disable-clock）
    - **默认值**：false
    - **描述**：设置为true以禁用观察者时钟
#### 压缩冰（packed_ice）
* ##### 允许生物生成（allow-mob-spawns）
    - **默认值**：true
    - **描述**：设置为false以阻止生物在压缩冰上生成
#### 活塞（piston）
* ##### 方块推动限制（block-push-limit）
    - **默认值**：12
    - **描述**：活塞可以推动的方块数量
#### 粉雪（powder_snow）
* ##### 绕过生物破坏（bypass-mob-griefing）
    - **默认值**：false
    - **描述**：设置为true使粉雪绕过生物破坏规则
#### 动力铁轨（powered-rail）
* ##### 激活范围（activation-range）
    - **默认值**：8
    - **描述**：单个红石源激活的动力铁轨数量
#### 重生锚（respawn_anchor）
* ##### 爆炸（explode）
    - **默认值**：true
    - **描述**：重生锚是否会爆炸。将其设置为false会使重生锚消失
* ##### 爆炸威力（explosion-power）
    - **默认值**：5.0
    - **描述**：爆炸的爆炸半径。（作为参考，TNT为4.0，充能苦力怕为6.0）
* ##### 爆炸火焰（explosion-fire）
    - **默认值**：true
    - **描述**：爆炸是否会引起火灾
* ##### 爆炸效果（explosion-effect）
    - **默认值**：BLOCK
    - **描述**：受爆炸影响的方块应该如何处理

      ???+ note "可用数值"
      所有数值都会破坏方块

            - `TNT` - 所有物品都会掉落，除非`tntExplosionDropDecay`规则设置为`true`
            - `MOB` - 一些物品会掉落，除非`mobExplosionDropDecay`规则设置为`false`
            - `BLOCK` - 一些物品会掉落，除非`blockExplosionDropDecay`规则设置为`false`
            - `NONE` - 所有物品都会掉落

#### 音叶尖叫者（sculk_shrieker）
* ##### 默认可召唤（can-summon-default）
    - **默认值**：false
    - **描述**：设置为true在放置时将`can_summon`设置为`true`
#### 虚空箱（shulker_box）
* ##### 允许超量堆叠（allow-oversized-stacks）
    - **默认值**：false
    - **描述**：控制虚空箱中是否允许超量堆叠的物品（默认修复了超量堆叠的问题 PaperMC/Paper#4748）
#### 看板（sign）
* ##### 允许颜色（allow-colors）
    - 需要[`purpur.sign.color`](permissions#purpursigncolor)、[`purpur.sign.style`](permissions#purpursignstyle)和/或[`purpur.sign.magic`](permissions#purpursignmagic)权限
    - **默认值**：false
    - **描述**：允许玩家在看板上使用颜色代码
#### 台阶（slab）
* ##### 潜行时独立破坏台阶（break-individual-slabs-when-sneaking）
    - **默认值**：false
    - **描述**：设置为true以允许在潜行时独立破坏双层台阶中的单个台阶
#### 刷怪笼（spawner）
* ##### 红石激活停用（deactivate-by-redstone）
    - **默认值**：false
    - **描述**：允许刷怪笼被红石停用
* ##### 修复MC-238526（fix-mc-238526）
    - **默认值**：false
    - **描述**：修复刷怪笼未正确生成水生动物的问题；MC-238526
#### 海绵（sponge）
* ##### 吸收岩浆（absorbs-lava）
    - **默认值**：false
    - **描述**：设置为true以允许海绵吸收岩浆
* ##### 吸收
    * ###### 区域
        - **默认值**：64
        - **描述**：海绵吸收水的方块区域
    * ###### 半径
        - **默认值**：6
        - **描述**：海绵吸收水的方块半径
#### 石匠台（stonecutter）
* ##### 伤害
    - **默认值**：0.0
    - **描述**：如果设置了数值，生物也会避免经过石匠台
#### 甘蔗（sugar_cane）
* ##### 受骨粉影响（affected-by-bonemeal）
    - **默认值**：false
    - **描述**：设置为true以使甘蔗受骨粉影响
#### 海龟蛋（turtle_egg）
* ##### 从经验球破坏（break-from-exp-orbs）
    - **默认值**：false
    - **描述**：允许经验球破坏/破坏海龟蛋
* ##### 从物品破坏（break-from-items）
    - **默认值**：false
    - **描述**：允许掉落的物品破坏/破坏海龟蛋
* ##### 从矿车破坏（break-from-minecarts）
    - **默认值**：false
    - **描述**：允许矿车破坏/破坏海龟蛋
* ##### 绕过生物破坏（bypass-mob-griefing）
    - **默认值**：false
    - **描述**：设置为true使海龟蛋绕过生物破坏规则
* ##### 随机滴落破裂几率（random-tick-crack-chance）
    - **默认值**：500
    - **描述**：海龟蛋破裂的几率
* ##### 羽落距离影响践踏（feather-fall-distance-affects-trampling）
    - **默认值**：false
    - **描述**：设置为true以停止践踏，如果实体下落的距离等于其羽落等级，再加上第一次践踏所需的额外方块。羽落1需要下落3+个方块才会践踏。羽落2需要4+，以此类推。

#### water
* ##### infinite-required-sources
    - **default**: 2
    - **description**: The amount of sources required to have infinite water


### mobs

#### allay
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it won't eject you)
* ##### respect-nbt
    - **default**: []
    - **description**: It ensures that Allays respect the NBT from the items they pick up. If you add stored enchantments to the list to respect, then if you give an Allay a sword with an enchantment, it will only pick up swords with the same enchantments.
#### axolotl
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 14.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### bat
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### attributes
    * ###### follow_range
        - **default**: 16.0
        - **description**: Follow range attribute
    * ###### knockback_resistance
        - **default**: 0.0
        - **description**: Knockback resistance attribute
    * ###### movement_speed
        - **default**: 0.6
        - **description**: Movement speed attribute
    * ###### flying_speed
        - **default**: 0.6
        - **description**: Flying speed attribute
    * ###### armor
        - **default**: 0.0
        - **description**: Armor attribute
    * ###### armor_toughness
        - **default**: 0.0
        - **description**: Armor toughness attribute
    * ###### attack_knockback
        - **default**: 0.0
        - **description**: Attack knockback attribute
    * ###### max_health
        - **default**: 6.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### bee
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: true
    - **description**: Set to false for this mob to stop taking damage from water
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### can-work-at-night
    - **default**: false
    - **description**: Controls whether bees can work during the night
* ##### can-work-in-rain
    - **default**: false
    - **description**: Controls whether bees can work during rainy weather
* ##### can-instantly-start-drowning
    - **default**: true
    - **description**: If disabled, bees will stop instantly taking damage the moment they begin touching water. Bees will still be able to "drown" when they run out of air while underwater.
* ##### dies-after-sting
    - **default**: true
    - **description**: Set whether a bee should die after stinging
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### blaze
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### takes-damage-from-water
    - **default**: true
    - **description**: Set to false for this mob to stop taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### camel
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        * min
            - **default**: 32.0
            - **description**: Min health attribute
        * max
            - **default**: 32.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.42
            - **description**: Min jump strength attribute
        * max
            - **default**: 0.42
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.09
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.09
            - **description**: Max movement speed attribute
#### cat
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### default-collar-color
    - **default**: RED
    - **description**: Set the default collar color when a cat is tamed. [Available Colors]({{ project.javadoc }}/org/bukkit/Color.html)
* ##### spawn-delay
    - **default**: 1200
    - **description**: Number of ticks between attempting to naturally spawn a cat
* ##### scan-range-for-other-cats
    * ###### swamp-hut
        - **default**: 16
        - **description**: Do not spawn a cat if another cat is found within this range. Set to 0 to disable
    * ###### village
        - **default**: 48
        - **description**: Do not spawn a cat if another cat is found within this range. Set to 0 to disable
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### cave_spider
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 12.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### chicken
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### retaliate
    - **default**: false
    - **description**: If a chicken is hit, it will attack back
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 4.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### cod
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 3.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### cow
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### feed-mushrooms-for-mooshroom
    - **default**: 0
    - **description**: Number of mushrooms to feed a cow to make it transform into a mooshroom. Value of 0 disables feature
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### naturally-aggressive-to-players
    * ###### chance
        - **default**: 0.0
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn aggressive towards players
    * ###### damage
        - **default**: 2.0
        - **description**: The amount of damage it will do to players
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### creaking
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### attributes
    * ###### max_health
        - **default**: 1.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
#### creeper
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### encircle-target
    - **default**: false
    - **description**: Set to true for this mob to circle around the player as it ignites
* ##### allow-griefing
    - **default**: true
    - **description**: Set to false to stop the creeper from griefing.
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for creepers to bypass the mob griefing gamerule
* ##### naturally-charged-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0 - 1.0) creepers are charged (powered) when spawning
* ##### explode-when-killed
    - **default**: false
    - **description**: Makes the creeper explode when killed
* ##### health-impacts-explosion
    - **default**: false
    - **description**: Makes the creeper's explosion be proportionate to the amount of health it has (lower health, weaker explosion)
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### head-visibility-percent
    - **default**: 0.5
    - **description**: Increase or decrease the percentage to make the detection range of the mob smaller or larger when a player is wearing the mobs corresponding head
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### dolphin
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### naturally-aggressive-to-players-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0 - 1.0) this mob will spawn aggressive towards players
* ##### disable-treasure-searching
    - **default**: false
    - **description**: Stops the dolphin from treasure hunting
* ##### spit
    * ###### cooldown
        - **default**: 20
        - **description**: The cooldown of the dolphin spit
    * ###### speed
        - **default**: 1.0
        - **description**: The speed of the dolphin spit
    * ###### damage
        - **default**: 2.0
        - **description**: The damage of the dolphin spit
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### donkey
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 30.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.5
            - **description**: Min jump strength attribute
        * max
            - **default**: 0.5
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.175
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.175
            - **description**: Max movement speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### drowned
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### can-break-doors
    - **default**: false
    - **description**: Set to true to allow drowned to break doors
* ##### jockey
    * ###### only-babies
        - **default**: true
        - **description**: Only babies can ride chickens
    * ###### chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) of riding a chicken when spawned
    * ###### try-existing-chickens
        - **default**: true
        - **description**: Scan for existing chickens to spawn on
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### spawn_reinforcements
        - **default**: 0.1
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn reinforcements
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### elder_guardian
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 80.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### ender_dragon
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### always-drop-full-exp
    - **default**: false
    - **description**: When true all valid ender dragon deaths will drop the full amount of experience orbs as if it were the first dragon death
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for the ender dragon to bypass the mob griefing gamerule
* ##### can-ride-vehicles
    - **default**: false
    - **description**: Set to true for the ender dragon to gain the ability to ride vehicles
* ##### attributes
    * ###### max_health
        - **default**: 200.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
#### enderman
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### allow-griefing
    - **default**: true
    - **description**: Set to false to stop the enderman from griefing
* ##### can-despawn-with-held-block
    - **default**: false
    - **description**: Makes the enderman despawn even if it's holding a block
* ##### ignore-projectiles
    - **default**: false
    - **description**: Stops the enderman from being immune to projectiles
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for enderman to bypass the mob griefing gamerule
* ##### takes-damage-from-water
    - **default**: true
    - **description**: Set to false for this mob to stop taking damage from water
* ##### aggressive-towards-endermites
    - **default**: true
    - **description**: Set to false to stop enderman from being aggro towards *all* types of spawned endermites 
* ##### aggressive-towards-endermites-only-spawned-by-player-thrown-ender-pearls
    - **default**: false
    - **description**: Set to true to make enderman aggro towards endermites *only* if they've been spawned by a player thrown ender pearl. This option does nothing if `aggressive-towards-endermites` is false
* ##### ignore-players-wearing-dragon-head
    - **default**: false
    - **description**: Set to true to make enderman ignore players that wear the dragon head
* ##### disable-player-stare-aggression
    - **default**: false
    - **description**: Set to true to stop an enderman from going aggro by a player looking into the enderman's eyes
* ##### attributes
    * ###### max_health
        - **default**: 40.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### endermite
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 8.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### evoker
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for evokers to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 24.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### fox
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### tulips-change-type
    - **default**: false
    - **description**: Feeding a white/orange tulip changes type snow/regular
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for foxes to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### frog
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### ridable-jump-height
    - **default**: 0.65
    - **description**: The height this mob can jump when riding it (in blocks)
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
#### ghast
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### giant
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### step-height
    - **default**: 2.0
    - **description**: How many blocks giants can walk up without having to jump
* ##### jump-height
    - **default**: 1.0
    - **description**: Jump height modifier. Default value of 1.0 makes giants jump about as high as their waist
* ##### movement-speed
    - **default**: 0.5
    - **description**: Movement speed attribute
* ##### attack-damage
    - **default**: 50.0
    - **description**: Attack damage (in half hearts)
* ##### have-ai
    - **default**: false
    - **description**: Control if giant zombies have AI instead of just standing there
* ##### have-hostile-ai
    - **default**: false
    - **description**: Control if giant zombies have hostile AI also
* ##### attributes
    * ###### max_health
        - **default**: 100.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### glow_squid
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### can-fly
    - **default**: false
    - **description**: Makes it so squids can fly, Oh my!
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### goat
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### guardian
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 30.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### hoglin
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 40.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### horse
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 30.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.4
            - **description**: Min jump strength attribute
        * max
            - **default**: 1.0
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.1125
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.3375
            - **description**: Max movement speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### husk
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### jockey
    * ###### only-babies
        - **default**: true
        - **description**: Only babies can ride chickens
    * ###### chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) of riding a chicken when spawned
    * ###### try-existing-chickens
        - **default**: true
        - **description**: Scan for existing chickens to spawn on
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### spawn_reinforcements
        - **default**: 0.1
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn reinforcements
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### illusioner
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### naturally-spawn
    - **default**: false
    - **description**: Control if illusioners naturally spawn in the game
* ##### movement-speed
    - **default**: 0.5
    - **description**: Movement speed attribute
* ##### follow-range
    - **default**: 18.0
    - **description**: Follow range attribute
* ##### attributes
    * ###### max_health
        - **default**: 32.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### iron_golem
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### healing-calms-anger
    - **default**: false
    - **description**: Calms the iron golem when it's healed if it's angry
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### can-spawn-in-air
    - **default**: false
    - **description**: Set whether iron golems can spawn in the air, like in 1.12 and below
* ##### can-swim
    - **default**: false
    - **description**: Set whether iron golems can swim or not
* ##### poppy-calms-anger
    - **default**: false
    - **description**: Giving the iron golem a poppy calms it down when it's angry
* ##### attributes
    * ###### max_health
        - **default**: 100.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### llama
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable. Llama's must be tamed and saddled (with carpet) to be WASD controllable.
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### join-caravans
    - **default**: true
    - **description**: Set to false to disable the [llama caravan feature](https://minecraft.wiki/w/Llama#Caravans)
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 30.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.5
            - **description**: Min jump strength attribute
        * max
            - **default**: 0.5
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.175
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.175
            - **description**: Max movement speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### magma_cube
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: "size * size"
        - **description**: The Max health equation used to calculate the max health
    * ###### attack_damage
        - **default**: "size"
        - **description**: The base value to set for the attack damage of the magma cube
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### mooshroom
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### mule
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 30.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.5
            - **description**: Min jump strength attribute
        * max
            - **default**: 0.5
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.175
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.175
            - **description**: Max movement speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### ocelot
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### spawn-below-sea-level
    - **default**: false
    - **description**: Set to true for this mob to spawn below the sea level
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### panda
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### parrot
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### can-breed
    - **default**: false
    - **description**: Gives parrots the ability to breed using any type of seeds (baby parrots don't exist D:, so "adult" parrots pop out)
* ##### attributes
    * ###### max_health
        - **default**: 6.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### phantom
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attacked-by-crystal-range
    - **default**: 0.0
    - **description**: Radius crystals scan for phantoms to attack. Value of 0 disables feature
* ##### attacked-by-crystal-damage
    - **default**: 1.0
    - **description**: Amount of damage per second crystals deal to phantoms. Value of 1.0 is half a heart
* ##### orbit-crystal-radius
    - **default**: 0.0
    - **description**: Radius which phantoms scan for crystals to orbit. Value of 0 disables feature
* ##### burn-in-light
    - **default**: 0
    - **description**: What light level the phantoms will burn at
* ##### burn-in-daylight
    - **default**: true
    - **description**: Whether phantoms burn in daylight or not
* ##### flames-on-swoop
    - **default**: false
    - **description**: Set to true for phantoms to shoot flames on swoop
* ##### ignore-players-with-torch
    - **default**: false
    - **description**: Whether phantoms avoid players with a torch in their hand
* ##### allow-griefing
    - **default**: false
    - **description**: Whether a phantom's flames can burn items
* ###### size
    * min
        - **default**: 0
        - **description**: Minimum size to randomly choose from when spawning naturally
    * max
        - **default**: 0
        - **description**: Maximum size to randomly choose from when spawning naturally
* ##### spawn
    * ###### min-sky-darkness
        - **default**: 5
        - **description**: The amount of darkness in the sky (5 is dark enough for thunderstorms, but not regular rain)
    * ###### only-above-sea-level
        - **default**: true
        - **description**: Only spawn on players above sea level
    * ###### only-with-visible-sky
        - **default**: true
        - **description**: Only spawn on players that have visible sky above them
    * ###### local-difficulty-chance
        - **default**: 3.0
        - **description**: Local difficulty must be greater than a random value chosen between 0.0 and this value
    * ###### per-attempt
        * min
            - **default**: 1
            - **description**: Minimum number of phantoms to spawn per attempt
        * max
            - **default**: -1
            - **description**: Maximum number of phantoms to spawn per attempt (Use -1 to base this off of world difficulty)
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### attack_damage
        - **default**: "6 + size"
        - **description**: The base value to set for the attack damage of the phantom
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### pig
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### give-saddle-back
    - **default**: false
    - **description**: Sneak and right-click a pig with a saddle on it's back to remove it with this option enabled
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### piglin
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for piglins to bypass the mob griefing gamerule
* ##### portal-spawn-modifier
    - **default**: 2000
    - **description**: Allows changing the modifier for the piglin spawn chance from a portal block
based on the world difficulty. [Read more here]({{ project.source }}/blob/61fc0a557fc0eedececd63d44d43ce6431bc23bb/patches/server/0167-Piglin-portal-spawn-modifier.patch)
* ##### attributes
    * ###### max_health
        - **default**: 16.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### head-visibility-percent
    - **default**: 0.5
    - **description**: Increase or decrease the percentage to make the detection range of the mob smaller or larger when a player is wearing the mobs corresponding head
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### piglin_brute
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 50.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### pillager
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for pillagers to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 24.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### polar_bear
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breedable-item
    - **default**: ""
    - **description**: Item to tempt/feed polar bears and make them breed
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 30.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### pufferfish
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 3.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### rabbit
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### spawn-killer-rabbit-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0-1.0) the killer rabbit naturally spawns
* ##### spawn-toast-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0-1.0) to naturally spawn a rabbit named Toast
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for rabbits to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 3.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### ravager
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for ravagers to bypass the mob griefing gamerule
* ##### griefable-blocks
    - **default**:
        ``` yaml
        - minecraft:oak_leaves
        - minecraft:spruce_leaves
        - minecraft:birch_leaves
        - minecraft:jungle_leaves
        - minecraft:acacia_leaves
        - minecraft:dark_oak_leaves
        - minecraft:beetroots
        - minecraft:carrots
        - minecraft:potatoes
        - minecraft:wheat
        ```
    - **description**: Whitelist of blocks that can be broken by the ravager
* ##### attributes
    * ###### max_health
        - **default**: 100.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
* ##### avoid-rabbits
    - **default**: false
    - **description**: Set to true if this mob should avoid rabbits, similar to how creepers avoid cats
#### salmon
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 3.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### sheep
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for sheep to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 8.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### shulker
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### change-color-with-dye
    - **default**: false
    - **description**: Lets you change the color of the shulker by right-clicking it with a dye
* ##### spawn-from-bullet:
    * ###### base-chance
        - **default**: 1.0
        - **description**: Base chance
    * ###### require-open-lid
        - **default**: true
        - **description**: Require shulkers to have their lid open to spawn from bullet
    * ###### nearby-range
        - **default**: 8.0
        - **description**: The nearby range to check for shulkers
    * ###### nearby-equation
        - **default**: `(nearby - 1) / 5.0`
        - **description**: The equation to use for calculating a shulker spawning from a bullet (`nearby` is the amount of shulker entities nearby) Make this blank to always spawn if there's a shulker nearby
    * ###### random-color
        - **default**: false
        - **description**: Set the shulker to a random color when spawned from a bullet
* ##### attributes
    * ###### max_health
        - **default**: 30.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute. Cannot be higher than 3.0
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### silverfish
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for silverfish to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 8.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### movement_speed
        - **default**: 0.25
        - **description**: Movement speed attribute
    * ###### attack_damage
        - **default**: 1.0
        - **description**: Attack damage attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### skeleton
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 8.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### head-visibility-percent
    - **default**: 0.5
    - **description**: Increase or decrease the percentage to make the detection range of the mob smaller or larger when a player is wearing the mobs corresponding head
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
* ##### feed-wither-roses
    - **default**: 0
    - **description**: Right-clicking a skeleton while holding a wither rose will convert the skeleton into a wither skeleton. With the value being how many wither roses you would need to convert the skeleton, and 0 meaning the feature is disabled.
* ##### bow-accuracy
    - **default**: 14 - difficulty * 4
    - **description**: Change the accuracy with which Skeletons shoot. The outcome of the formula is the divergence (spread). The higher the value, the less accurate the shot is.
      ``` yaml
      easy:   14 - 1 * 4 = 10
      normal: 14 - 2 * 4 = 6
      hard:   14 - 3 * 4 = 2
      ```
#### skeleton_horse
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### can-swim
    - **default**: false
    - **description**: Can skeleton horses swim in water. False makes them sink to the bottom (vanilla default)
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 15.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.4
            - **description**: Min jump_strength attribute
        * max
            - **default**: 1.0
            - **description**: Max jump_strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.2
            - **description**: Min movement_speed attribute
        * max
            - **default**: 0.2
            - **description**: Max movement_speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### slime
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### attributes
    * ###### max_health
        - **default**: "size * size"
        - **description**: The Max health equation used to calculate the max health
    * ###### attack_damage
        - **default**: "size"
        - **description**: The base value to set for the attack damage of the slime
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### sniffer
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
    - **default**: 14.0
    - **description**: Max health attribute
#### snow_golem
???+ info "The formula used to determine the amount of ticks between shots"
    ``` sh
    ((sqrt(distanceToTarget) / attack-distance) / snow-ball-modifier) * (max-shoot-interval-ticks - min-shoot-interval-ticks) + min-shoot-interval-ticks
    ```
    If `min-shoot-interval-ticks` and `max-shoot-interval-ticks` are both set to 0, snow golems won't shoot any snowballs.

* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### leave-trail-when-ridden
    - **default**: false
    - **description**: Leaves a trail where a snowman walks when being ridden
* ##### pumpkin-can-be-added-back
    - **default**: false
    - **description**: Control if pumpkins can be placed back onto snowmen
* ##### min-shoot-interval-ticks
    - **default**: 20
    - **description**: Min amount of interval ticks that get shot
* ##### max-shoot-interval-ticks
    - **default**: 20
    - **description**: Max amount of interval ticks that get shot
* ##### snow-ball-modifier
    - **default**: 10.0
    - **description**: The modifier value of snow-ball projectiles
* ##### attack-distance
    - **default**: 1.25
    - **description**: The distance at which the snow golem will attack
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for snow golems to bypass the mob griefing gamerule
* ##### takes-damage-from-water
    - **default**: true
    - **description**: Set to false for this mob to stop taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 4.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### spider
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 16.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### squid
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### immune-to-EAR
    - **default**: true
    - **description**: Makes this mob immune to EAR (Entity Activation Range - See spigot.yml)
* ##### water-offset-check
    - **default**: 0.0
    - **description**: Stops squids from floating on top of water
* ##### can-fly
    - **default**: false
    - **description**: Makes it so squids can fly, Oh my!
* ##### attributes
    * ###### max_health
        - **default**: 10.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### stray
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### strider
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### give-saddle-back
    - **default**: false
    - **description**: Sneak and right-click a strider with a saddle on it's back to remove it with this option enabled
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### takes-damage-from-water
    - **default**: true
    - **description**: Set to false for this mob to stop taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### tadpole
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
#### trader_llama
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable.
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable. Trader llama's must be tamed to be WASD controllable. Being saddled (carpet) is not a requirement since it technically always has a carpet.
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 30.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.5
            - **description**: Min jump strength attribute
        * max
            - **default**: 0.5
            - **description**: Max jump strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.175
            - **description**: Min movement speed attribute
        * max
            - **default**: 0.175
            - **description**: Max movement speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### tropical_fish
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 3.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### turtle
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 30.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### vex
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### attributes
    * ###### max_health
        - **default**: 14.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### villager
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Ignores the `mobGriefing` gamerule and allows the villagers to drop items, allowing them to breed
* ##### can-be-leashed
    - **default**: false
    - **description**: Allow players to use leads on villagers (trader not included)
* ##### follow-emerald-blocks
    - **default**: false
    - **description**: Villagers will be tempted by emerald blocks and follow players holding them
* ##### allow-trading
    - **default**: true
    - **description**: Set to false to disable trading with villagers
* ##### display-trade-item
    - **default**: true
    - **description**: Set to false to stop the villager from displaying the trade item
* ##### lobotomize
    * ###### enabled
        - **default**: false
        - **description**: Lobotomizes the villager if it cannot move (Does not disable trading)
    * ###### check-interval
        - **default**: 100
        - **description**: The interval in ticks to check if a villager is lobotomized 
    * ###### wait-until-trade-locked
        - **default**: false
        - **description**: Wait until a villager has been traded with before lobotomizing
* ##### minimum-demand
    - **default**: 0
    - **description**: Addresses MC-163962 where villager demand decreases indefinitely. Paper adds a patch to fix this by preventing demand from going below zero. This option allows the minimum demand to be configurable.
* ##### can-breed
    - **default**: true
    - **description**: Whether villagers can breed or not
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### clerics-farm-warts
    - **default**: false
    - **description**: Set to true for clerics to farm nether wart
* ##### cleric-wart-farmers-throw-warts-at-villagers
    - **default**: true
    - **description**: Set to false for clerics to not throw nether wart at other villagers
* ##### spawn-iron-golem
    * ###### radius
        - **default**: 0
        - **description**: Radius villagers search for existing iron golems before spawning more. Value of 0 disables features
    * ###### limit
        - **default**: 0
        - **description**: Maximum amount of iron golems villagers can spawn in configured radius
* ##### search-radius
    * ###### acquire-poi
        - **default**: 48
        - **description**: Radius within which villagers search to acquire POI.
    * ###### nearest-bed-sensor
        - **default**: 48
        - **description**: Radius within which villagers search to detect the nearest bed.
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### tempt_range
        - **default**: 10.0
        - **description**: Tempt range attribute. Only works when `follow-emerald-blocks` is enabled.
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### vindicator
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### johnny
    * ###### spawn-chance
        - **default**: 0.0
        - **description**: Percent chance (0.0 - 1.0) a vindicator named "Johnny" will spawn instead of a vindicator
* ##### attributes
    * ###### max_health
        - **default**: 24.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### wandering_trader
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### can-be-leashed
    - **default**: false
    - **description**: Allow players to use leads on villagers (trader not included)
* ##### allow-trading
    - **default**: true
    - **description**: Set to false to disable trading with wandering traders
* ##### follow-emerald-blocks
    - **default**: false
    - **description**: Villagers will be tempted by emerald blocks and follow players holding them
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### tempt_range
        - **default**: 10.0
        - **description**: Tempt range attribute. Only works when `follow-emerald-blocks` is enabled.
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### warden
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
#### witch
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 26.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### wither
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### ridable-max-y
    - **default**: 256
    - **description**: Maximum height this mob can fly to while being ridden
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### can-ride-vehicles
    - **default**: false
    - **description**: Set to true for the wither to gain the ability to ride vehicles
* ##### play-spawn-sound
    - **default**: true
    - **description**: Play the wither's spawn sound globally when it is spawned
* ##### explosion-radius
    - **default**: 1.0
    - **description**: The explosion radius of a wither's projectile attack
* ##### health-regen-amount
    - **default**: 1.0
    - **description**: The regen amount of the wither
* ##### health-regen-delay
    - **default**: 20
    - **description**: How long to delay the health regen
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for withers to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 300.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### wither_skeleton
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### wolf
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### milk-cures-rabid-wolves
    - **default**: true
    - **description**: Set to false for rabid wolves to not be cured by milk
* ##### spawn-rabid-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0 - 1.0) that a wolf will spawn as rabid
* ##### default-collar-color
    - **default**: RED
    - **description**: Set the default collar color when a wolf is tamed. [Available Colors]({{ project.javadoc }}/org/bukkit/Color.html)
* ##### breeding-delay-ticks
    - **default**: 6000
    - **description**: The amount of ticks to wait before being able to breed again
* ##### attributes
    * ###### max_health
        - **default**: 8.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### zoglin
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### attributes
    * ###### max_health
        - **default**: 40.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### zombie
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### jockey
    * ###### only-babies
        - **default**: true
        - **description**: Only babies can ride chickens
    * ###### chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) of riding a chicken when spawned
    * ###### try-existing-chickens
        - **default**: true
        - **description**: Scan for existing chickens to spawn on
* ##### aggressive-towards-villager-when-lagging
    - **default**: true
    - **description**: Set to false to stop zombie aggressiveness towards villagers when lagging
* ##### bypass-mob-griefing
    - **default**: false
    - **description**: Set to true for zombies to bypass the mob griefing gamerule
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### spawn_reinforcements
        - **default**: 0.1
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn reinforcements
* ##### head-visibility-percent
    - **default**: 0.5
    - **description**: Increase or decrease the percentage to make the detection range of the mob smaller or larger when a player is wearing the mobs corresponding head
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### zombie_horse
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: false
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### spawn-chance
    - **default**: 0.0
    - **description**: Percent chance (0.0 - 1.0) a zombie horse will spawn instead of a skeleton horse (natural spawns during thunderstorms)
* ##### attributes
    * ###### max_health
        * min
            - **default**: 15.0
            - **description**: Min health attribute
        * max
            - **default**: 15.0
            - **description**: Max health attribute
    * ###### jump_strength
        * min
            - **default**: 0.4
            - **description**: Min jump_strength attribute
        * max
            - **default**: 1.0
            - **description**: Max jump_strength attribute
    * ###### movement_speed
        * min
            - **default**: 0.2
            - **description**: Min movement_speed attribute
        * max
            - **default**: 0.2
            - **description**: Max movement_speed attribute
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### zombie_villager
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### cure
    * ###### enabled
        - **default**: true
        - **description**: Set to false to stop zombie villagers from being curable 
* ##### curing_time
    * ###### min
        - **default**: 3600
        - **description**: The minimum amount of ticks to randomly choose from when curing
    * ###### max
        - **default**: 6000
        - **description**: The maximum amount of ticks to randomly choose from when curing
* ##### jockey
    * ###### only-babies
        - **default**: true
        - **description**: Only babies can ride chickens
    * ###### chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) of riding a chicken when spawned
    * ###### try-existing-chickens
        - **default**: true
        - **description**: Scan for existing chickens to spawn on
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### spawn_reinforcements
        - **default**: 0.1
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn reinforcements
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience
#### zombified_piglin
* ##### ridable
    - **default**: false
    - **description**: Makes this mob mountable
* ##### controllable
    - **default**: true
    - **description**: Makes this mob WASD controllable
* ##### ridable-in-water
    - **default**: true
    - **description**: Makes this mob mountable in water (it wont eject you)
* ##### takes-damage-from-water
    - **default**: false
    - **description**: Set to true for this mob to start taking damage from water
* ##### count-as-player-kill-when-angry
    - **default**: true
    - **description**: Set to false to stop zombified piglins from dropping XP if they were angered (but not killed) by a player
* ##### jockey
    * ###### only-babies
        - **default**: true
        - **description**: Only babies can ride chickens
    * ###### chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) of riding a chicken when spawned
    * ###### try-existing-chickens
        - **default**: true
        - **description**: Scan for existing chickens to spawn on
* ##### attributes
    * ###### max_health
        - **default**: 20.0
        - **description**: Max health attribute
    * ###### scale
        - **default**: 1.0
        - **description**: Scale attribute
    * ###### spawn_reinforcements
        - **default**: 0.0
        - **description**: Percent chance (0.0 - 1.0) this mob will spawn reinforcements
* ##### always-drop-exp
    - **default**: false
    - **description**: Set to true if this mob should always drop experience

### gameplay-mechanics

#### always-tame-in-creative
- **default**: false
- **description**: Set to true to have 100% chance of taming a mob
#### animal-breeding-cooldown-seconds
- **default**: 0
- **description**: Adds a cooldown to breeding animals per animal type
#### armorstand
* ##### step-height
    - **default**: 0.0
    - **description**: Set the default step height of armorstands. Useful for plugins that utilize armorstands as vehicles to be able to drive over blocks without jumping, etc
* ##### set-name-visible-when-placing-with-custom-name
    - **default**: false
    - **description**: Makes the name visible when placing with a custom name
* ##### fix-nametags
    - **default**: false
    - **description**: Makes the name visible when using a Name Tag on an Armor Stand
* ##### place-with-arms-visible
    - **default**: false
    - **description**: Makes the arms visible when placed
* ##### can-movement-tick
    - **default**: true
    - **description**: Set to false to disallow armorstands from moving
* ##### can-move-in-water
    - **default**: true
    - **description**: Set to false to disallow armorstands from moving in water
* ##### can-move-in-water-over-fence
    - **default**: true
    - **description**: Set to false to disallow armorstands from moving in water over a fence
#### arrow
* ##### movement-resets-despawn-counter
    - **default**: true
    - **description**: Setting this to false prevents keeping arrows alive indefinitely (such as when the block the arrow is stuck in gets removed, like a piston head going up/down).
#### boat
* ##### eject-players-on-land
    - **default**: false
    - **description**: Set to true for boats to eject players when on land
* ##### do-fall-damage
    - **default**: false
    - **description**: Set to false for boats to not do fall damage to players
#### clamp-explosion-radius
- **default**: true
- **description**: Set to false to allow setting a negative `ExplosionRadius` value on explosions
#### daylight-cycle-ticks
* ##### daytime
    - **default**: 12000
    - **description**: Set how long the daylight cycle is ticked
* ##### nighttime
    - **default**: 12000
    - **description**: Set how long the nighttime cycle is ticked
#### disable-drops-on-cramming-death
- **default**: false
- **description**: Stops entities from dropping loot on death, if killed by cramming gamerule
#### disable-oxidation-proximity-penalty
- **default**: false
- **description**: Set to true to remove the slowdown of oxidation caused by nearby unoxidized copper blocks
#### drowning
* ##### air-ticks
    - **default**: 300
    - **description**: How long you can breathe underwater before you start drowning
* ##### ticks-per-damage
    - **default**: 20
    - **description**: Amount of ticks between the drowning damage
* ##### damage-from-drowning
    - **default**: 2.0
    - **description**: Amount of damage done while drowning
#### elytra
* ##### damage-per-second
    - **default**: 1
    - **description**: How much damage an elytra's durability takes during flight each second
* ##### damage-multiplied-by-speed
    - **default**: 0.0
    - **description**: Damage is multiplied by speed if flight is faster than set speed. Value of 0 disables this multiplier
* ##### kinetic-damage
    - **default**: true
    - **description**: Should players take damage when flying into a wall
* ##### ignore-unbreaking
    - **default**: false
    - **description**: Should elytras ignore the unbreaking enchantment
* ##### damage-per-boost
    * ###### firework
        - **default**: 0
        - **description**: How much damage to deal to the elytra when firework boost activates
    * ###### trident
        - **default**: 0
        - **description**: How much damage to deal to the elytra when trident riptide boost activates
#### entities-can-use-portals
- **default**: true
- **description**: Set to false to stop entities from being able to use portals
#### entities-pick-up-loot-bypass-mob-griefing
- **default**: false
- **description**: Mobs that can pick up loot will continue to pick up loot even if the `mobGriefing` gamerule is disabled
#### entity-blindness-multiplier
- **default**: 1
- **description**: How blind a mob is when affected with the blindness potion effect
#### entity-left-handed-chance
- **default**: 0.05
- **description**: Percent chance (0.0 - 1.0) an entity will spawn left-handed
#### entity-lifespan
- **default**: 0
- **description**: Disabled by default (0), Amount of ticks an entity will live before disappearing. Interacting with a player resets the timer
#### fireballs-bypass-mob-griefing
- **default**: false
- **description**: Set to true for fireballs to bypass the mob griefing gamerule
#### halloween
* ##### force
    - **default**: false
    - **description**: Set to true to force the world into halloween
* ##### head-chance
    - **default**: 0.25
    - **description**: Percent chance (0.0 - 1.0) a zombie or skeleton will spawn with a jack o' lantern/carved pumpkin on it's head
#### impose-teleport-restrictions-on-end-portals
- **default**: false
- **description**: Set to true to impose teleport restrictions on end portals. This broadcasts the `EntityTeleportHinderedEvent` event which gives the ability to retry teleports if they fail due to having passengers/being vehicles
#### impose-teleport-restrictions-on-gateways
- **default**: false
- **description**: Set to true to impose teleport restrictions on gateways. This broadcasts the `EntityTeleportHinderedEvent` event which gives the ability to retry teleports if they fail due to having passengers/being vehicles
#### impose-teleport-restrictions-on-nether-portals
- **default**: false
- **description**: Set to true to impose teleport restrictions on nether portals. This broadcasts the `EntityTeleportHinderedEvent` event which gives the ability to retry teleports if they fail due to having passengers/being vehicles
#### infinity-bow
* ##### works-without-arrows
    - **default**: false
    - **description**: Set to true for the infinity bow to work without arrows
#### item
* ##### end-crystal
    * ###### place-anywhere
        - **default**: false
        - **description**: Allows you to place an end crystal on any block, not just obsidian and bedrock
* ##### shears
    * ###### damage-if-sprinting
        - **default**: false
        - **description**: Holding shears while sprinting will randomly damage the player (Don't run with scissors!) Will not activate for shears that have an `item_model` component or `custom_model_data` component
    * ###### damage-if-sprinting-item-model
        - **default**: "purpurmc:scissors"
        - **description**: The resource location of the [`item_model`](https://minecraft.wiki/w/Data_component_format#item_model) to use for shears alongside the `damage-if-sprinting` option.
    * ###### ignore-in-water
        - **default**: false
        - **description**: Should damage be ignored while in water if `damage-if-sprinting` is enabled
    * ###### ignore-in-lava
        - **default**: false
        - **description**: Should damage be ignored while in lava if `damage-if-sprinting` is enabled
    * ###### sprinting-damage
        - **default**: 1
        - **description**: The amount of damage to give if `damage-if-sprinting` is enabled
    * ###### defuse-tnt-chance
        - **default**: 0.0
        - **description**: Percent chance (0.0 - 1.0) that right-clicking primed TNT will defuse it
* ##### snowball
    * ###### extinguish
        * ###### fire
            - **default**: false
            - **description**: Whether snowballs, when thrown, should extinguish fires
        * ###### candles
            - **default**: false
            - **description**: Whether snowballs, when thrown, should extinguish candles
        * ###### campfires
            - **default**: false
            - **description**: Whether snowballs, when thrown, should extinguish campfires
* ##### shulker_box
    * ###### drop-contents-when-destroyed
        - **default**: true
        - **description**: Whether the shulker box should drop it's contents when it's been destroyed
* ##### compass
    * ###### holding-shows-bossbar
        - **default**: false
        - **description**: If the bossbar from the [`/compass`](commands#compass) command should show when holding a compass
* ##### glow_berries
    * ###### eat-glow-duration
        - **default**: 0
        - **description**: Amount of ticks the player will glow after eating a glow berry. Set to 0 to disable
* ##### ender-pearl
    * ###### damage
        - **default**: 5
        - **description**: The amount of damage to take after teleporting using an ender pearl
    * ###### cooldown
        - **default**: 20
        - **description**: The cooldown after using an ender pearl (in ticks)
    * ###### creative-cooldown
        - **default**: 20
        - **description**: The cooldown after using an ender pearl while in creative (in ticks)
    * ###### endermite-spawn-chance
        - **default**: 0.05
        - **description**: Percent chance (0.0 - 1.0) an endermite will spawn after teleporting using an ender pearl
* ##### immune
    * ###### explosion
        - **default**: []
        - **description**: List of items that are immune to explosions
    * ###### fire
        - **default**: []
        - **description**: List of items that are immune to fire
    * ###### lightning
        - **default**: []
        - **description**: List of items that are immune to lightning
    * ###### cactus
        - **default**: []
        - **description**: List of items that are immune to cactus
    ???+ note "Example of item immune list:"
        ``` yaml
        explosion:
          - minecraft:diamond
          - minecraft:diamond_block
          - minecraft:diamond_sword
        ```

???+ warning "Warning"
    These item immune lists can cause client desync issues, such as invisible items on the ground! There is nothing that can be done about that from the server-side code.

#### mending-multiplier
- **default**: 1.0
- **description**: How effective mending is at repairing items, higher values mean less xp is used to repair items. (1.0 = 100%)
#### milk-clears-beneficial-effects
- **default**: true
- **description**: Set to false to have milk clear only negative status effects
#### milk-cures-bad-omen
- **default**: true
- **description**: Allow players to drink milk to cure bad omen status effect
#### minecart
* ##### max-speed
    - **default**: 0.4
    - **description**: Max speed of a minecart when controlled
* ##### place-anywhere
    - **default**: false
    - **description**: Whether minecarts can be placed anywhere, not just on rails
* ##### powered-rail
    * ###### boost-modifier
        - **default**: 0.06
        - **description**: the speed boost that minecarts gain from hitting a powered rail (Doesn't affect furnace minecarts)
* ##### controllable
    * ###### enabled
        - **default**: false
        - **description**: Whether minecarts can be controlled when not on rails
    * ###### fall-damage
        - **default**: true
        - **description**: Set to true to give fall damage to the player while in a minecart
    * ###### step-height
        - **default**: 1.0
        - **description**: The step height in which a minecarts can go up to the next block without jumping
    * ###### hop-boost
        - **default**: 0.5
        - **description**: Jump power when pressing spacebar on a controllable minecart
    * ###### base-speed
        - **default**: 0.1
        - **description**: Base speed of minecart when controlled
    * ###### block-speed
        - **default**:
            ``` yaml
            grass_block: 0.3
            stone: 0.5
            ```
        - **description**: List of speed overrides per block type
#### mob-effects
* ##### health-regen-amount
    - **default**: 1.0
    - **description**: The amount at which this effect affects entities
* ##### minimal-health-poison-amount
    - **default**: 1.0
    - **description**: The amount at which this effect affects entities
* ##### poison-degeneration-amount
    - **default**: 1.0
    - **description**: The amount at which this effect affects entities
* ##### wither-degeneration-amount
    - **default**: 1.0
    - **description**: The amount at which this effect affects entities
* ##### hunger-exhaustion-amount
    - **default**: 0.005
    - **description**: The amount at which this effect affects entities
* ##### saturation-regen-amount
    - **default**: 1.0
    - **description**: The amount at which this effect affects entities
#### mob-last-hurt-by-player-time
- **default**: 100
- **description**: Allows you to change the amount of ticks required for a mob's death to count as a player kill after being hurt by the player (projectile or directly)
#### mob-spawning
* ##### village-cats
    - **default**: default
    - **description**: Set to true to spawn in the world that this option is a part of
* ##### raid-patrols
    - **default**: default
    - **description**: Set to true to spawn in the world that this option is a part of
* ##### phantoms
    - **default**: default
    - **description**: Set to true to spawn in the world that this option is a part of
* ##### wandering-traders
    - **default**: default
    - **description**: Set to true to spawn in the world that this option is a part of
* ##### village-sieges
    - **default**: default
    - **description**: Set to true to spawn in the world that this option is a part of
* ##### ignore-creative-players
    - **default**: false
    - **description**: Option to choose whether or not to ignore creative players when spawning mobs.
#### mobs-ignore-rails
- **default**: false
- **description**: Set to true to allow mobs to walk over rails
#### note-block-ignore-above
- **default**: false
- **description**: Set to true for note blocks to continue making sound even if there is a block above it
#### persistent-droppable-entity-display-names
- **default**: true
- **description**: Set to true to make entity's display names and lores persist after breaking (ex. named armor stands retain their name)
#### persistent-tileentity-display-name
- **default**: true
- **description**: Set to false to disable TE's display names being persistant after breaking (ex. named custom player heads stop retaining their name)
#### persistent-tileentity-lore
- **default**: false
- **description**: Set to true to make TE's lores persist after breaking (ex. custom player heads with lore will retain their lore)
#### player
* ##### exp-pickup-delay-ticks
    - **default**: 2
    - **description**: The delay a player can pick up experience after it is dropped
* ##### shift-right-click-repairs-mending-points
    - **default**: 0
    - **description**: The amount of experience points to use from the player's bar for repairing items enchanted with mending in the player's inventory
* ##### spawn-invulnerable-ticks
    - **default**: 60
    - **description**: Gives you the ability to control how long a player is invulnerable when they first spawn in.
* ##### invulnerable-while-accepting-resource-pack
    - **default**: false
    - **description**: Sets the player as invulnerable while they download the resource pack.
* ##### teleport-if-outside-border
    - **default**: false
    - **description**: Teleports you to spawn if you somehow get outside the world border
* ##### teleport-on-nether-ceiling-damage
    - **default**: false
    - **description**: Teleports you to spawn if you take damage while on top of the nether ceiling
* ##### allow-void-trading
    - **default**: false
    - **description**: Allows the ability to continuously trade with a villager through an End Gateway exploit.
* ##### totem-of-undying-works-in-inventory
    - **default**: false
    - **description**: Allows the totem of undying to work anywhere in your inventory, not just your offhand
* ##### ridable-in-water
    - **default**: false
    - **description**: Lets mobs/players ride on players if the player is in the water
* ##### fix-stuck-in-portal
    - **default**: false
    - **description**: If the player is stuck inside a portal with no way of getting out, walking to another block will reset the portal cooldown, allowing them to teleport back through the portal
* ##### one-punch-in-creative
    - **default**: false
    - **description**: If the player is in creative and hits an entity with an empty hand, the entity instantly dies
* ##### sleep-ignore-nearby-mobs
    - **default**: false
    - **description**: Set to true to allow sleep even if there are mobs nearby
* ##### can-skip-night
    - **default**: true
    - **description**: Set to false to disable the players' ability to skip the night by sleeping
* ##### critical-damage-multiplier
    - **default**: 1.5
    - **description**: The percentage of damage a critical attack adds to the base damage
* ##### burp-when-full
    - **default**: false
    - **description**: Plays a burp sound after a player fills the hunger bar completely by eating
* ##### burp-delay
    - **default**: 10
    - **description**: Amount of ticks to delay sound; `burp-when-full` option must be enabled
* ##### curse-of-binding
    * ###### remove-with-weakness
        - **default**: false
        - **description**: Allows the player to remove curse of binding armor when they have a weakness effect applied to them
* ##### idle-timeout
    * ###### kick-if-idle
        - **default**: true
        - **description**: Kick players if they become idle (see server.properties for player-idle-timeout time)
    * ###### tick-nearby-entities
        - **default**: true
        - **description**: Should entities tick normally when nearby players are AFK. False will require at least 1 non-AFK player in order to tick
    * ###### mobs-target
        - **default**: true
        - **description**: Should mobs target nearby AFK players
    * ###### count-as-sleeping
        - **default**: false
        - **description**: Should AFK players count as sleeping? (allows active players to skip night by sleeping, even if AFK players are not in bed)
    * ###### update-tab-list
        - **default**: false
        - **description**: Should AFK players have their name updated in the tab list (puts `[AFK]` in front of their name)
* ##### exp-dropped-on-death
    * ###### equation
        - **default**: expLevel * 7
        - **description**: How much exp to drop on death. Available NMS variables are `expLevel`, `expTotal`, and `exp`
    * ###### maximum
        - **default**: 100
        - **description**: Maximum amount of exp value to drop on death
* ##### netherite-fire-resistance
    * ###### duration
        - **default**: 0
        - **description**: Set how long the fire resistance lasts. Set to 0 to disable
    * ###### amplifier
        - **default**: 0
        - **description**: Set the amplifier for the fire resistance effect
    * ###### ambient
        - **default**: false
        - **description**: Set to true for the particle effects to be less intrusive on the screen
    * ###### show-particles
        - **default**: false
        - **description**: Set to true for the fire resistance potion effect to show particles
    * ###### show-icon
        - **default**: true
        - **description**: Set to false for the fire resistance effect to not display it's icon
#### projectile-damage
* ##### snowball
    - **default**: -1
    - **description**: Set how much damage a snowball does (-1 will make damage be 3 for blazes & 0 for all other entities which is default)
#### projectile-offset
* ##### bow
    - **default**: 1.0
    - **description**: The projectile offset of a bow
* ##### crossbow
    - **default**: 1.0
    - **description**: The projectile offset of a crossbow
* ##### egg
    - **default**: 1.0
    - **description**: The projectile offset of an egg
* ##### ender-pearl
    - **default**: 1.0
    - **description**: The projectile offset of an ender-pearl
* ##### throwable-potion
    - **default**: 1.0
    - **description**: The projectile offset of a throwable-potion
* ##### trident
    - **default**: 1.0
    - **description**: The projectile offset of a trident
* ##### snowball
    - **default**: 1.0
    - **description**: The projectile offset of a snowball
#### projectiles-bypass-mob-griefing
* **default**: false
* **description**: Set to true for projectiles to bypass the mob griefing gamerule
#### raid-cooldown-seconds
- **default**: 0
- **description**: How long you should wait before another raid can be initiated
#### rain-stops-after-sleep
- **default**: true
- **description**: Set to false to make rain continue even after a player sleeps
#### shovel-turns-block-to-grass-path
- **default**:
    ``` yaml
    - minecraft:coarse_dirt
    - minecraft:dirt
    - minecraft:grass_block
    - minecraft:mycelium
    - minecraft:podzol
    - minecraft:rooted_dirt
    ```
- **description**: List of blocks that can be turned into a grass path when right-clicked with a shovel
#### silk-touch
Requires the [`purpur.drop.spawners`](permissions#purpurdropspawners) and [`purpur.place.spawners`](permissions#purpurplacespawners) permissions

* ##### enabled
    - **default**: false
    - **description**: Makes it so you can mine spawners using a tool with silk touch
* ##### minimal-level
    - **default**: 1
    - **description**: The minimal level of the Silktouch enchantment required to pick up mined spawners
* ##### tools
    - **default**:
    ``` yaml
    - minecraft:iron_pickaxe
    - minecraft:golden_pickaxe
    - minecraft:diamond_pickaxe
    - minecraft:netherite_pickaxe
    ```
    - **description**: Whitelist of tools that can mine spawners with silk touch
* ##### spawner-name
    - **default**: "&lt;reset>&lt;white>Monster Spawner"
    - **description**: The name of the spawner
* ##### spawner-lore
    - **default**:
        ``` yaml
        - Spawns a <mob>
        ```
    - **description**: The lore of the spawner
#### thunder-stops-after-sleep
- **default**: true
- **description**: Set to false to make thunder continue even after a player sleeps
#### tick-fluids
- **default**: true
- **description**: Set to false to stop fluids from ticking. [Screenshot of a simple plugin that uses this option](images/freezefluids-chat-screenshot.png)
#### trident-loyalty-void-return-height
- **default**: 0.0
- **description**: The void height at which a trident with loyalty will return to it's thrower. A value of 0.0 or higher disables this feature.
#### use-better-mending
- **default**: false
- **description**: Set to true for mending enchantment to always repair the most damaged equipment first

### ridable-settings

#### babies-are-ridable
- **default**: true
- **description**: Set to false to stop babies from being ridable
#### untamed-tamables-are-ridable
- **default**: true
- **description**: Set to false to stop untamed tamables from being ridable
#### use-dismounts-underwater-tag
- **default**: true
- **description**: Set to false to use `<mob>.ridable-in-water` options instead of the [`DISMOUNTS_UNDERWATER`](https://minecraft.wiki/w/Tag#Entity_types) tag
#### use-night-vision
- **default**: false
- **description**: Set to true to give night vision to riders while on a ridable
