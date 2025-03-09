本页详细介绍了 Purpur 在 `purpur.yml` 文件中暴露的各种配置设置。

如果你想了解 `paper.yml`、`spigot.yml`、`bukkit.yml` 和 `server.properties` 中的设置，应该查看它们各自的文档页面。

* [服务器配置 (server.properties)](https://minecraft.wiki/w/Server.properties)

* [Bukkit 配置 (bukkit.yml)](https://bukkit.fandom.com/wiki/Bukkit.yml)

* [Spigot 配置 (spigot.yml)](https://www.spigotmc.org/wiki/spigot-configuration/)

* [Paper 配置 (paper.yml)](https://docs.papermc.io/paper/reference/paper-global-configuration)

* [Pufferfish 配置 (pufferfish.yml)](https://docs.pufferfish.host/setup/pufferfish-fork-configuration/)

???+ warning "警告"
配置值可能会频繁变化，页面中的信息可能不完整。如果你找不到需要的信息或认为某些内容有误，请通过我们的 [Discord]({{ social[0].link }}) 服务器联系我们。

## 全局设置

全局设置影响服务器上的所有世界以及核心服务器功能本身。

### verbose

- **默认值**: false
- **描述**: 设置是否在服务器启动时将所有配置值输出到服务器日志中。

### config-version

* **请勿更改此项！** Purpur 在内部使用该项来帮助自动更新你的配置。

### command

* #### uptime
    * ##### format
        - **默认值**: "&lt;days>&lt;hours>&lt;minutes>&lt;seconds>"
        - **描述**: 在 [`uptime-command-output`](#uptime-command-output) 中 `<uptime>` 占位符的格式。
    * ##### day
        - **默认值**: "%02d day, "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<day>` 占位符的输出格式。
    * ##### days
        - **默认值**: "%02d days, "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<days>` 占位符的输出格式。
    * ##### hour
        - **默认值**: "%02d hour, "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<hour>` 占位符的输出格式。
    * ##### hours
        - **默认值**: "%02d hours, "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<hours>` 占位符的输出格式。
    * ##### minute
        - **默认值**: "%02d minute, and "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<minute>` 占位符的输出格式。
    * ##### minutes
        - **默认值**: "%02d minutes, and "
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<minutes>` 占位符的输出格式。
    * ##### second
        - **默认值**: "%02d second"
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<second>` 占位符的输出格式。
    * ##### seconds
        - **默认值**: "%02d seconds"
        - **描述**: 在 [command.uptime.format](#format) 选项中 `<seconds>` 占位符的输出格式。
* #### gamemode
    * ##### requires-specific-permission
        - 需要 [`minecraft.command.gamemode.<gamemode>`](permissions#minecraftcommandgamemodegamemode) 权限
        - **默认值**: false
        - **描述**: 如果为 true，那么切换每种游戏模式都需要相应的权限。
* #### tpsbar
    * ##### title
      `<tps>` - 当前的 TPS

      `<mspt>` - 当前的 MSPT

      `<ping>` - 当前的延迟（ping）

        - **默认值**: &lt;gray>TPS&lt;yellow>:&lt;/yellow> &lt;tps> MSPT&lt;yellow>:&lt;/yellow>
          &lt;mspt> Ping&lt;yellow>:&lt;/yellow> &lt;ping>ms
        - **描述**: 当服务器运行 `/tpsbar` 命令时 Bossbar 的格式。

    * ##### overlay
        - **默认值**: NOTCHED_20
        - **描述**: 设置 Bossbar 的叠加类型  
          可选项：`PROGRESS`、`NOTCHED_6`、`NOTCHED_10`、`NOTCHED_12`、`NOTCHED_20`
    * ##### fill-mode
        - **默认值**: MSPT
        - **描述**: 设置 Bossbar 显示的内容  
          可选项：`TPS`、`MSPT`、`PING`
    * ##### progress-color
      可选项：`PINK`（粉色）、`BLUE`（蓝色）、`RED`（红色）、`GREEN`（绿色）、`YELLOW`（黄色）、`PURPLE`（紫色）、`WHITE`（白色）
        * ###### good
            - **默认值**: GREEN（绿色）
            - **描述**: 当 `fill-mode` 为 "good" 时显示的颜色。
        * ###### medium
            - **默认值**: YELLOW（黄色）
            - **描述**: 当 `fill-mode` 为 "medium" 时显示的颜色。
        * ###### low
            - **默认值**: RED（红色）
            - **描述**: 当 `fill-mode` 为 "low" 时显示的颜色。
    * ##### text-color
      `<text>` - 来自 [`settings.command.tpsbar.title`](#title) 的格式
        * ###### good
            - **默认值**: &lt;gradient:#55ff55:#00aa00>&lt;text>&lt;/gradient>
            - **描述**: 当 `fill-mode` 为 "good" 时 `<text>` 的渐变效果。
        * ###### medium
            - **默认值**: &lt;gradient:#ffff55:#ffaa00>&lt;text>&lt;/gradient>
            - **描述**: 当 `fill-mode` 为 "medium" 时 `<text>` 的渐变效果。
        * ###### low
            - **默认值**: &lt;gradient:#ff5555:#aa0000>&lt;text>&lt;/gradient>
            - **描述**: 当 `fill-mode` 为 "low" 时 `<text>` 的渐变效果。
    * ##### tick-interval
        - **默认值**: 20
        - **描述**: Bossbar 更新的频率。
* #### rambar
    * ##### title
      `<used>` - 当前使用的内存量。

      `<xmx>` - 设置的最大 Xmx 值。

      `<percent>` - 使用的内存百分比。

        - **默认值**: '"&lt;gray>内存&lt;yellow>:&lt;/yellow> &lt;used>/&lt;xmx> (&lt;percent>)"'
        - **描述**: 当服务器运行 `/rambar` 命令时 Bossbar 的格式。

    * ##### overlay
        - **默认值**: NOTCHED_20
        - **描述**:
          设置 Bossbar 的叠加类型  
          可选项：`PROGRESS`、`NOTCHED_6`、`NOTCHED_10`、`NOTCHED_12`、`NOTCHED_20`
    * ##### progress-color
      可选项：`PINK`（粉色）、`BLUE`（蓝色）、`RED`（红色）、`GREEN`（绿色）、`YELLOW`（黄色）、`PURPLE`（紫色）、`WHITE`（白色）
        * ###### good
            - **默认值**: GREEN（绿色）
            - **描述**: 当剩余内存量为 “良好” 时显示的颜色。
        * ###### medium
            - **默认值**: YELLOW（黄色）
            - **描述**: 当剩余内存量为 “中等” 时显示的颜色。
        * ###### low
            - **默认值**: RED（红色）
            - **描述**: 当剩余内存量为 “低” 时显示的颜色。
    * ##### text-color
      `<text>` - 来自 [`settings.command.tpsbar.title`](#title) 的格式
        * ###### good
            - **默认值**: &lt;gradient:#55ff55:#00aa00>&lt;text>&lt;/gradient>
            - **描述**: 当剩余内存量为 “良好” 时 `<text>` 的渐变效果
        * ###### medium
            - **默认值**: &lt;gradient:#ffff55:#ffaa00>&lt;text>&lt;/gradient>
            - **描述**: 当剩余内存量为 “中等” 时 `<text>` 的渐变效果
        * ###### low
            - **默认值**: &lt;gradient:#ff5555:#aa0000>&lt;text>&lt;/gradient>
            - **描述**: 当剩余内存量为 “低” 时 `<text>` 的渐变效果
    * ##### tick-interval
        - **默认值**: 20
        - **描述**: Bossbar 更新的频率
* #### compass
    * ##### title
        - **默认值**: "S  ·  ◈  ·  ◈  ·  ◈  ·  SW  ·  ◈  ·  ◈  ·  ◈  ·  W  ·  ◈  ·  ◈  ·  ◈  ·  NW  ·  ◈  ·  ◈  ·  ◈  ·  N  ·  ◈  ·  ◈  ·  ◈  ·  NE  ·  ◈  ·  ◈  ·  ◈  ·  E  ·  ◈  ·  ◈  ·  ◈  ·  SE  ·  ◈  ·  ◈  ·  ◈  ·  
          S  ·  ◈  ·  ◈  ·  ◈  ·  SW  ·  ◈  ·  ◈  ·  ◈  ·  W  ·  ◈  ·  ◈  ·  ◈  ·  NW  ·  ◈  ·  ◈  ·  ◈  ·  N  ·  ◈  ·  ◈  ·  ◈  ·  NE  ·  ◈  ·  ◈  ·  ◈  ·  E  ·  ◈  ·  ◈  ·  ◈  ·  SE  ·  ◈  ·  ◈  ·  ◈  ·  "
        - **描述**: 当服务器运行 [`/compass`](commands#compass) 命令时 Bossbar 的格式。

    * ##### overlay
        - **默认值**: PROGRESS
        - **描述**:
          设置 Bossbar 的叠加类型  
          可选项：`PROGRESS`、`NOTCHED_6`、`NOTCHED_10`、`NOTCHED_12`、`NOTCHED_20`
    * ##### progress-color
      可选项：`PINK`（粉色）、`BLUE`（蓝色）、`RED`（红色）、`GREEN`（绿色）、`YELLOW`（黄色）、`PURPLE`（紫色）、`WHITE`（白色）
        - **默认值**: GREEN（绿色）
        - **描述**: Bossbar 的颜色
    * ##### percent
        - **默认值**: 1.0
        - **描述**: Bossbar 的填充程度，范围从 0.0 到 1.0
    * ##### tick-interval
        - **默认值**: 5
        - **描述**: Bossbar 更新的频率
* #### hide-hidden-players-from-entity-selector
    - **默认值**: false
    - **描述**: 如果为 true，那么隐藏在实体选择器中的被隐藏玩家。

### allow-water-placement-in-the-end

- **默认值**: true
- **描述**: 允许在末地放置水源。

### use-alternate-keepalive

- **默认值**: false
- **描述**: 使用不同的方法来处理保持连接的超时。启用此选项后，会每秒向玩家发送一个保持连接的数据包，只有在 30 秒内没有任何回应时才会踢出玩家。只要响应其中任何一个包，玩家就会保持连接。也就是说，如果某个包在传输过程中丢失，玩家不会被踢出。

### tps-catchup

- **默认值**: true
- **描述**: 是否打开 TPS 自稳（TPS Catchup）。

???+ note "注意"
TPS 自稳（TPS Catchup）会使服务器的 TPS 超过 20，试图在任何低于 20 的时间段后，尽量将平均 TPS 保持在接近 20 的水平，但也会带来一些副作用。例如，在网络延迟高峰期，玩家可能会被怪物瞬间击杀。

### server-mod-name
- **默认值**: Purpur
- **描述**: 修改客户端显示的服务器名称，当客户端版本过旧或打开调试屏幕 [F3] 时会显示该名称。

### fix-projectile-looting-transfer
- **默认值**: false
- **描述**: 解决 MC-3304 问题，防止由于弹射物造成的死亡被应用于掉落物，除非有插件修改了掉落物修正。

### blast-resistance-overrides
- **默认值**: {}
- **描述**: 修改以改变方块的爆炸抗性。示例：
``` yaml
  blast-resistance-overrides:
    minecraft:oak_leaves: 55
    minecraft:obsidian: 1.5
```

### clamp-attributes
- **默认值**: true
- **描述**: 控制是否限制属性的最大值。

### limit-armor
- **默认值**: true
- **描述**: 控制护甲是否限制其能够减少的伤害量。

### username-valid-characters
- **默认值**: ^[a-zA-Z0-9_.]*$
- **描述**: 可以在用户名中使用的字符。可以使用正则表达式配置。

### lagging-threshold
- **默认值**: 19.0
- **描述**: Purpur 将会检查何时出现延迟，以便根据情况调整行为。此值为当服务器开始出现延迟时的阈值。~~目前仅用于 `mob.villager.brain-ticks` 设置~~

### fix-network-serialized-items-in-creative
- **默认值**: false
- **描述**: 如果为 true，那么将会修复通过 `NetworkItemSerializeEvent` 修改的物品，这些物品即使是客户端侧的也会持久化，原因是创造模式客户端使用了创造模式的物品操作。

### disable-give-dropping
- **默认值**: false
- **描述**: 如果为 true，那么当玩家的背包已满时，`/give` 命令将不会在地面上产生掉落物品。

### player-deaths-always-show-item
- **默认值**: false
- **描述**: 如果为 true，那么在玩家死亡消息中总是显示用来击杀玩家的物品。

### register-minecraft-debug-commands
- **默认值**: false
- **描述**: 如果为 true，那么将会注册未使用/隐藏的 Minecraft 命令。以下命令将变为可用（并带有其对应的 `minecraft.command.<command_name>` 权限节点）：`debugconfig`、`serverpack`、`spawn_armor_trims`、`warden_spawn_tracker`、`debugmobspawning`、`debugpath` 和 `raid`。此列表可能不完整，具体取决于这些命令是否被删除或是否有新命令添加到 Minecraft 的新版本中。

### startup-commands
设置 `Purpur.IReallyDontWantStartupCommands` 系统属性为 `true` 以禁用此功能。

- **默认值**: []
- **描述**: 允许设置一组控制台命令，当服务器启动时会执行这些命令。对于没有访问控制台权限的服务器管理员非常有用。灵感来源于 [Vintagestory 的 "StartupCommands" 配置选项](https://wiki.vintagestory.at/index.php/Setting_up_a_Multiplayer_Server#Acquiring_server_admin_rights)。

### bee-count-payload
- **默认值**: false
- **描述**: 如果为 true，那么将会允许客户端通过自定义数据包获取蜂巢的蜜蜂数量。（主要由 [PurpurClient](https://modrinth.com/mod/PurpurClient) 模组使用）

### messages

#### afk-broadcast-away
需要将 [`kick-if-idle`](#kick-if-idle) 设置为 `false`

- **默认值**: &lt;yellow>&lt;italic>%s 现在处于离开状态
- **描述**: 当用户进入离开状态时，广播此消息（必须将 `player-idle-timeout` 设置为大于 0，并且 [`kick-if-idle`](#kick-if-idle) 为 false）

#### afk-broadcast-back
需要将 [`kick-if-idle`](#kick-if-idle) 设置为 `false`

- **默认值**: &lt;yellow>&lt;italic>%s 不再处于离开状态
- **描述**: 当用户不再处于离开状态时，广播此消息（必须将 `player-idle-timeout` 设置为大于 0，并且 [`kick-if-idle`](#kick-if-idle) 如果为 false，那么）

### afk-broadcast-use-display-name
需要将 [`kick-if-idle`](#kick-if-idle) 设置为 `false`  
需要 [`afk-broadcast-away`](#afk-broadcast-away) 或 [`afk-broadcast-back`](#afk-broadcast-back) 有非空值

- **默认值**: false
- **描述**: 在离开状态广播中使用玩家的显示名称（纯文本），而不是用户名。
- **注意**: 此选项不会设置玩家的 TAB 名称。

#### afk-tab-list-prefix
需要将 [`kick-if-idle`](#kick-if-idle) 设置为 `false`

- **默认值**: "[AFK] "
- **描述**: 当玩家处于离开状态时，显示在玩家列表中的名前缀。

#### afk-tab-list-suffix
需要将 [`kick-if-idle`](#kick-if-idle) 设置为 `false`

- **默认值**: ""
- **描述**: 当玩家处于离开状态时，显示在玩家列表中的名字后缀。

#### cannot-ride-mob
需要 [`allow.ride.<mob_id>`](permissions#allowridemob_id) 权限

- **默认值**: &lt;red>你不能骑乘这个生物
- **描述**: 当玩家尝试骑乘他们没有权限骑乘的生物时显示的消息。

#### dont-run-with-scissors
需要启用 [`damage-if-sprinting`](#damage-if-sprinting) 选项

- **默认值**: &lt;red>&lt;italic>不要拿着剪刀跑！
- **描述**: 当玩家尝试拿着剪刀奔跑时，小标题中显示的消息。

#### ping-command-output
需要 [`bukkit.command.ping`](permissions#bukkitcommandping) 权限

- **默认值**: &lt;green>%s 的延迟为 %sms
- **描述**: 当运行 `/ping <user>` 命令时的输出。

#### uptime-command-output
需要 [`bukkit.command.uptime`](permissions#bukkitcommanduptime) 权限  
`<uptime>` - 来自 [`<global>.command.uptime.format`](#format)

- **默认值**: &lt;green>服务器已运行 &lt;uptime>
- **描述**: 当运行 `/uptime` 命令时显示的消息。

#### demo-command-output
需要 [`bukkit.command.demo`](permissions#bukkitcommanddemo) 权限

- **默认值**: &lt;green>%s 已查看演示屏幕
- **描述**: 当使用 `/demo` 命令为玩家启用演示屏幕时显示的消息。

#### credits-command-output
需要 [`bukkit.command.credits`](permissions#bukkitcommandcredits) 权限

- **默认值**: &lt;green>%s 已查看结束字幕
- **描述**: 当使用 `/credits` 命令为玩家启用结束字幕时显示的消息。

#### tpsbar-command-output
需要 [`bukkit.command.tpsbar`](permissions#bukkitcommandtpsbar) 权限

- **默认值**: &lt;green>Tpsbar 为 &lt;target> 切换了 &lt;onoff>
- **描述**: 当使用 `/tpsbar` 命令为玩家启用 TPS 条时显示的消息。

#### ram-command-output

- **默认值**: '&lt;green>内存使用情况: &lt;used>/&lt;xmx> (&lt;percent>)'
- **描述**: 当使用 `/ram` 命令时显示的内存使用情况聊天消息。

#### rambar-command-output

- **默认值**: &lt;green>Rambar toggled &lt;onoff> for &lt;target>
- **描述**: 当通过 `/rambar` 命令为某个用户启用 rambar 时显示的消息。

#### unverified-username
- **默认值**: default
- **描述**: 当玩家因用户名未验证（玩家处于离线模式）而被踢出时显示的消息。设置为 "default"将会将显示默认消息 "Failed to verify username!"

#### sleep-skipping-night
- **默认值**: default
- **描述**: 当跳过夜晚时显示的 actionbar 消息。设置为 "default" 让客户端使用自己的可翻译组件。设置为空字符串则禁用该消息。

#### sleeping-players-percent
- **默认值**: default
- **描述**: 当玩家正在睡觉时显示的 actionbar 消息。设置为 "default" 让客户端使用自己的可翻译组件。设置为空字符串则禁用该消息。可用占位符：`<count>` - 当前正在睡觉的玩家数量，`<total>` - 需要睡觉的玩家总数。

#### sleep-not-possible
- **默认值**: default
- **描述**: 当玩家尝试睡觉，但 `playersSleepingPercentage` 游戏规则被设置为大于 100 时显示的 actionbar 消息。设置为 "default" 让客户端使用自己的可翻译组件。设置为空字符串则禁用该消息。

#### death-message
* ##### stonecutter
    - **默认值**: &lt;player> has sawed themself in half
    - **描述**: 当玩家因站在石匠切割台上而死亡时显示的死亡消息。
* ##### run-with-scissors
    - **默认值**: &lt;player> slipped and fell on their shears
    - **描述**: 当玩家因拿着剪刀奔跑而死亡时显示的死亡消息。

### network
#### kick-for-out-of-order-chat
- **默认值**: true
- **描述**: 如果为 false，那么将会服务器不会因为聊天顺序错误而踢出玩家。

#### upnp-port-forwarding
- **默认值**: false
- **描述**: 在服务器启动时尝试使用 UPnP 自动进行端口转发。

#### max-joins-per-second
- **默认值**: false
- **描述**: 如果为 true，那么将会使 `max-joins-per-tick` 配置在 `paper.yml` 中按秒而非按刻进行使用。

### blocks

#### barrel
* ##### rows
    - **默认值**: 3
    - **描述**: 一个桶（barrel）应该有的行数。最小值：1，最大值：6。

#### beehive
* ##### max-bees-inside
    - **默认值**: 3
    - **描述**: 蜂巢/蜂窝中允许的最大蜜蜂数量。

#### grindstone
* ##### ignored-enchants
    - **默认值**:
        ``` yaml
        - minecraft:binding_curse
        - minecraft:vanishing_curse
        ```
    - **描述**: 在研磨石（grindstone）中不会被移除的附魔。

* ##### remove-attributes
    - **默认值**: false
    - **描述**: 如果为 true，那么 允许研磨石移除物品的属性。

* ##### remove-name-and-lore
    - **默认值**: false
    - **描述**: 如果为 true，那么 允许研磨石移除物品的名称和传说。

#### ender_chest
* ##### six-rows
    - **默认值**: false
    - **描述**: 启用时，末影箱应该有六行背包空间。

* ##### use-permissions-for-rows
    - 需要 [`ender_chest.six-rows`](#six-rows) 如果为 true，那么
    - 需要 [`purpur.enderchest.rows.<number>`](permissions#purpurenderchestrowsnumber) 权限
    - **默认值**: false
    - **描述**: 使用权限节点来决定行数。默认情况下，启用此设置时，所有玩家都拥有六行背包空间，除非使用权限另行指定。

#### crying_obsidian
* ##### valid-for-portal-frame
    - **默认值**: false
    - **描述**: 如果为 true，那么将会可以用哭泣的黑曜石（crying obsidian）制作传送门框架。

#### twisting_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大年龄。

#### weeping_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大年龄。

#### cave_vines
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大年龄。

#### kelp
* ##### max-growth-age
    - **默认值**: 25
    - **描述**: 植物可以生长的最大年龄。

#### anvil
* ##### cumulative-cost
    - **默认值**: true
    - **描述**: 是否应用累计成本，当物品在铁砧（anvil）中使用时。

#### lightning_rod
* ##### range
    - **默认值**: 128
    - **描述**: 改变雷电棒（lightning rod）引导雷电的范围。

#### magma-block
* ##### reverse-bubble-column-flow
    - **默认值**: false
    - **描述**: 如果为 true，那么将会当在水源方块下方放置或生成熔岩方块时，会生成向上的气泡柱，而不是向下的气泡柱。

#### soul-sand
* ##### reverse-bubble-column-flow
    - **默认值**: false
    - **描述**: 如果为 true，那么将会当在水源方块下方放置或生成灵魂沙时，会生成向下的气泡柱，而不是向上的气泡柱。
### broadcasts

#### advancement

##### only-broadcast-to-affected-player
- **默认值**: false
- **描述**: 只将成就广播消息发送到受影响的玩家聊天框中。

#### death

##### only-broadcast-to-affected-player
- **默认值**: false
- **描述**: 只将死亡消息广播到受影响的玩家聊天框中。

### logger

#### suppress-init-legacy-material-errors
- **默认值**: false
- **描述**: 抑制有关插件初始化旧版材料 API 的警告。

#### suppress-ignored-advancement-warnings
- **默认值**: false
- **描述**: 抑制控制台和日志中关于未知属性的警告。

#### suppress-unrecognized-recipe-errors
- **默认值**: false
- **描述**: 抑制有关尝试加载未识别配方的警告。

#### suppress-setblock-in-far-chunk-errors
- **默认值**: false
- **描述**: 抑制在远距离区块中检测到的 `setBlock` 错误。

#### suppress-library-loader
- **默认值**: false
- **描述**: 抑制与库加载器相关的日志。

### food-properties
- **默认值**: {}
- **描述**: 修改食物属性。以下是使用所有设置的示例，并附带说明：
``` yaml
spider_eye:                # 要编辑的食物
  nutrition: 2              # 恢复的饥饿点数
  saturation-modifier: 0.8  # 恢复的饱和度，计算公式为 "nutrition * saturation-modifier * 2"
  is-meat: false            # 标记食物是否适合狼食用
  can-always-eat: false     # 标记该食物是否在满饥饿时仍可食用
  fast-food: false          # 食用食物所需时间 (false: 32 ticks, true: 16 ticks)
  effects:                  # 食用时应用的效果列表 (可以有多个效果)
    poison:                 # 应用的效果
      duration: 100         # 效果持续时间（以 ticks 为单位）
      chance: 1.0           # 效果应用的概率 (0.0 - 1.0)
      visible: true         # 是否显示粒子效果
      amplifier: 1          # 效果的增幅
      ambient: false        # 如果为 true，那么 使粒子效果更不显眼（如信标效果）
      show-icon: true       # 在 HUD 上显示效果图标
```

### entity

#### enderman
* ##### short-height
    - **默认值**: false
    - **描述**: 如果启用，末影人可以进入 2 格高的空间。由于客户端的碰撞箱保持不变，你仍然可以攻击它们的头部。

### enchantment

* ##### allow-looting-on-shears
    - **默认值**: false
    - **描述**: 允许剪刀带有掠夺附魔。

* ##### allow-unsafe-enchant-command
    - **默认值**: false
    - **描述**: 允许通过命令将附魔等级提升到最大级别以上。

* ##### clamp-levels
    - **默认值**: true
    - **描述**: 设置为 `false`将会允许附魔等级达到 `32767`，通过将等级存储为短整型（short）而非字节（byte）实现。

???+ note "注意"
客户端不会显示超过 `255` 的附魔等级。

#### anvil
* ##### allow-inapplicable-enchants
    - **默认值**: false
    - **描述**: 允许对通常不适用的工具或盔甲应用附魔。例如，对镐子附加锋利附魔。

* ##### allow-incompatible-enchants
    - **默认值**: false
    - **描述**: 允许对通常不兼容的附魔同时应用。例如，保护和火焰保护，或幸运和丝绸触摸。

* ##### allow-higher-enchants-levels
    - **默认值**: false
    - **描述**: 允许将附魔等级提升到最大等级以上。例如，效率 V + 效率 V = 效率 VI。

* ##### replace-incompatible-enchants
    - **默认值**: false
    - **描述**: 在应用不兼容的附魔时，代替基础物品中的附魔，将其替换为副手物品上的附魔。

## world-settings

世界设置是基于每个世界的。子节点 `default` 用于没有特定设置的所有世界。

有关世界设置部分的更清晰解释，请阅读 Paper 的解释： https://docs.papermc.io/paper/per-world-configuration

### hunger

#### starvation-damage
- **默认值**: 1.0
- **描述**: 饥饿造成的伤害量。

### settings

#### entity
* #### shared-random
- **默认值**: true
- **描述**: 如果为 false，那么 时允许 RNG 操作。Paper 通过使用共享（并且锁定的）随机源来修补 RNG 操作。这带来了性能提升，但技术玩家可能更喜欢关闭它以便能操作 RNG。

???+ warning "警告"
共享随机设置未经 Purpur 团队测试，可能被认为是不安全的。（共享随机设计为线程安全。撤销此修补程序可能会在某些情况下导致 ConcurrentModificationExceptions 错误，无论是否有插件，并且可能增加内存使用。）

### blocks

#### anvil
* ##### use-mini-message
    - 需要 [`purpur.anvil.minimessage`](permissions#purpuranvilminimessage) 权限
    - **默认值**: false
    - **描述**: 允许玩家在铁砧中使用 MiniMessage 标签。

* ##### allow-colors
    - 需要 [`purpur.anvil.color`](permissions#purpuranvilcolor) 权限
    - **默认值**: false
    - **描述**: 允许玩家在铁砧中使用颜色代码。

* ##### iron-ingots-used-for-repair
    - **默认值**: 0
    - **描述**: 修复铁砧所需的铁锭数量。

* ##### obsidian-used-for-damage
    - **默认值**: 0
    - **描述**: 使铁砧受损所需的黑曜石数量。

#### azalea
* ##### growth-chance
    - **默认值**: 0.0
    - **描述**: 紫藤自然生长成树木的概率。

#### beacon
* ##### allow-effects-with-tinted-glass
    - **默认值**: false
    - **描述**: 是否允许当信标被有色玻璃覆盖时，信标效果仍然激活。

* ##### effect-range
    * ###### level-1
        - **默认值**: 20
        - **描述**: 该等级的效果范围。

    * ###### level-2
        - **默认值**: 30
        - **描述**: 该等级的效果范围。

    * ###### level-3
        - **默认值**: 40
        - **描述**: 该等级的效果范围。

    * ###### level-4
        - **默认值**: 50
        - **描述**: 该等级的效果范围。

#### bed
* ##### explode
    - **默认值**: true
    - **描述**: 床是否会爆炸。如果为 false，那么将会床会消失。

* ##### explode-on-villager-sleep
    - **默认值**: false
    - **描述**: 当村民睡觉时床是否会爆炸。

* ##### explosion-power
    - **默认值**: 5.0
    - **描述**: 爆炸的半径。（作为比较，TNT 是 4.0，充能苦力怕是 6.0）

* ##### explosion-fire
    - **默认值**: true
    - **描述**: 爆炸是否会引起火灾。

* ##### explosion-effect
    - **默认值**: BLOCK
    - **描述**: 爆炸影响的方块处理方式。

      ???+ note "可用值"
      所有值都会摧毁方块。

            - `TNT` - 所有物品都会掉落，除非设置 `tntExplosionDropDecay` 游戏规则为 `true`。
            - `MOB` - 一些物品会掉落，除非设置 `mobExplosionDropDecay` 游戏规则为 `false`。
            - `BLOCK` - 一些物品会掉落，除非设置 `blockExplosionDropDecay` 游戏规则为 `false`。
            - `NONE` - 所有物品都会掉落。

#### blue_ice
* ##### allow-mob-spawns
    - **默认值**: true
    - **描述**: 如果为 false，那么将会不允许在蓝冰上生成怪物。

* ##### allow-snow-formation
    - **默认值**: true
    - **描述**: 如果为 false，那么将会不允许在蓝冰上形成雪。

#### cactus
* ##### breaks-from-solid-neighbors
    - **默认值**: true
    - **描述**: 如果为 true，那么将会仙人掌会因邻近的实心方块而破裂。

* ##### affected-by-bonemeal
    - **默认值**: false
    - **描述**: 如果为 true，那么将会仙人掌可以使用骨粉。

#### campfire
* ##### lit-when-placed
    - **默认值**: true
    - **描述**: 如果为 false，那么将会放置篝火时不会点燃。
#### cauldron
* ##### fill-chances
    * ###### rain
        - **默认值**: 0.05
        - **说明**: 坩埚因降雨（取决于随机刻）而填充水的速度
    * ###### powder-snow
        - **默认值**: 0.1
        - **说明**: 坩埚因粉末雪（取决于随机刻）而填充的速度
    * ###### dripstone-water
        - **默认值**: 0.17578125
        - **说明**: 位于一个朝下的尖锥滴水石下方（其上方放置有水的方块）的坩埚填充水的速度（取决于随机刻）
    * ###### dripstone-lava
        - **默认值**: 0.05859375
        - **说明**: 位于一个朝下的尖锥滴水石下方（其上方放置有熔岩的方块）的坩埚填充熔岩的速度（取决于随机刻）
#### chest
* ##### open-with-solid-block-on-top
    - **默认值**: false
    - **说明**: 允许箱子在上方有实体方块时仍可打开
#### composter
* ##### sneak-to-bulk-process
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，可通过手持物品时蹲下并右键点击批量处理食物/植物类物品
#### conduit
* ##### valid-ring-blocks
    - **默认值**:
        ``` yaml
        - minecraft:prismarine
        - minecraft:prismarine_bricks
        - minecraft:sea_lantern
        - minecraft:dark_prismarine
        ```
    - **说明**: 可用于构建传导器 (Conduit) 的方块
* ##### effect-distance
    - **默认值**: 16
    - **说明**: 框架中每七个方块提供的传导器有效作用范围
* ##### mob-damage
    * ###### distance
        - **默认值**: 8
        - **说明**: 对敌对生物造成伤害的距离（单位：方块）
    * ###### damage-amount
        - **默认值**: 4
        - **说明**: 若敌对生物与水/雨接触，每 2 秒施加的伤害值
#### coral
* ##### die-outside-water
    - **默认值**: true
    - **说明**: 如果为 false，那么 (假) 可使珊瑚在陆地上放置时保持存活
#### dispenser
* ##### apply-cursed-to-armor-slots
    - **默认值**: true
    - **说明**: 当发射器发放附有绑定诅咒的护甲时，是否自动将其装入护甲槽
* ##### place-anvils
    - **默认值**: false
    - **说明**: 允许发射器放置铁砧
#### door
* ##### requires-redstone
    - **默认值**: []
    - **说明**: 允许设置需要红石信号才能操作的门（例如橡木、云杉等）
#### dragon_egg
* ##### teleport
    - **默认值**: true
    - **说明**: 控制龙蛋在受到撞击时是否传送
#### enchantment-table
* ##### lapis-persists
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，青金石将保留在附魔台槽中，从而可将青金石留在附魔台上
#### end-crystal
* ##### cramming-amount
    - **默认值**: 0
    - **说明**: 控制同一碰撞盒内可容纳多少个末影水晶；超过设定数量的水晶会引发爆炸
* ##### baseless
    * ###### explode
        - **默认值**: true
        - **说明**: 如果为 false，那么 (假) 可防止水晶爆炸
    * ###### explosion-power
        - **默认值**: 6.0
        - **说明**: 末影水晶爆炸的威力
    * ###### explosion-fire
        - **默认值**: false
        - **说明**: 如果为 true，那么  后，在末影水晶爆炸时会产生火焰
    * ###### explosion-effect
        - **默认值**: BLOCK (BLOCK【方块】)
        - **说明**: 爆炸作用于方块时的处理方式

          ???+ note "Available Values"  
          所有选项均会破坏方块

                - `TNT` - 除非将 `tntExplosionDropDecay` 游戏规则设为 `true`，否则所有物品都会掉落  
                - `MOB` - 除非将 `mobExplosionDropDecay` 游戏规则设为 `false`，否则部分物品会掉落  
                - `BLOCK` - 除非将 `blockExplosionDropDecay` 游戏规则设为 `false`，否则部分物品会掉落  
                - `NONE` - 所有物品都会掉落
* ##### base
    * ###### explode
        - **默认值**: true
        - **说明**: 如果为 false，那么 (假) 可防止水晶爆炸
    * ###### explosion-power
        - **默认值**: 6.0
        - **说明**: 末影水晶爆炸的威力
    * ###### explosion-fire
        - **默认值**: false
        - **说明**: 如果为 true，那么  后，在末影水晶爆炸时会产生火焰
    * ###### explosion-effect
        - **默认值**: BLOCK (BLOCK【方块】)
        - **说明**: 爆炸作用于方块时的处理方式

          ???+ note "Available Values"  
          所有选项均会破坏方块

                - `TNT` - 除非将 `tntExplosionDropDecay` 游戏规则设为 `true`，否则所有物品都会掉落  
                - `MOB` - 除非将 `mobExplosionDropDecay` 游戏规则设为 `false`，否则部分物品会掉落  
                - `BLOCK` - 除非将 `blockExplosionDropDecay` 游戏规则设为 `false`，否则部分物品会掉落  
                - `NONE` - 所有物品都会掉落
#### farmland
* ##### gets-moist-from-below
    - **默认值**: false
    - **说明**: 允许土壤直接从下方的水中吸收湿气
* ##### use-alpha-farmland
    - **默认值**: false
    - **说明**: 当下方直接放置栅栏或圆石墙时，防止耕地被践踏
* ##### bypass-mob-griefing
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，耕地将忽略生物破坏规则
* ##### only-players-trample
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，仅允许玩家践踏耕地
* ##### disable-trampling
    - **默认值**: false
    - **说明**: 如果为 true，那么  后可完全禁用践踏效果
* ##### trample-height
    - **默认值**: -1.0
    - **说明**: 设置玩家或实体下落到一定高度后才会践踏耕地

???+ note "Note"  
践踏高度以方块高度或精确距离表示。测试中发现 fallDistance 的数值非常不一致，测试结果如下：  
Value set -> Actual fall distance needed to trample  
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
* ##### feather-fall-distance-affects-trampling
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，如果实体下落的距离等于其“缓落”附魔等级所抵消的距离加上首次践踏所需的额外方块数，则不会践踏耕地。（例如：缓落 I 要求下落超过 3 个方块才会践踏，缓落 II 要求 4 个方块，以此类推）
#### flowering_azalea
* ##### growth-chance
    - **默认值**: 0.0
    - **说明**: 花开杜鹃自然生长为树的几率
#### furnace
* ##### use-lava-from-underneath
    - **默认值**: false
    - **说明**: 允许熔炉通过下方放置的熔岩实现无限供能
#### lava
* ##### infinite-required-sources
    - **默认值**: 2
    - **说明**: 无限熔岩所需的源方块数量
* ##### speed
    * ###### nether
        - **默认值**: 10
        - **说明**: 物理/流动更新之间的刻数延迟（数值越低越快，适用于下界）
    * ###### not-nether
        - **默认值**: 30
        - **说明**: 物理/流动更新之间的刻数延迟（数值越低越快，适用于非下界）
#### magma-block
* ##### damage-when-sneaking
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，蹲下时会造成伤害
* ##### damage-with-frost-walker
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，穿戴附有冰霜行者附魔的靴子行走时会受到伤害
#### nether_wart
* ##### affected-by-bonemeal
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，地狱疣可被骨粉加速生长
#### observer
* ##### disable-clock
    - **默认值**: false
    - **说明**: 如果为 true，那么  后禁用观察者的时钟功能
#### packed_ice
* ##### allow-mob-spawns
    - **默认值**: true
    - **说明**: 如果为 false，那么 (假) 后禁止生物在密冰上生成
#### piston
* ##### block-push-limit
    - **默认值**: 12
    - **说明**: 活塞可推动的方块数量上限
#### powder_snow
* ##### bypass-mob-griefing
    - **默认值**: false
    - **说明**: 如果为 true，那么  后，粉末雪将忽略生物破坏规则
#### powered-rail
* ##### activation-range
    - **默认值**: 8
    - **说明**: 单个红石信号可激活的动力轨数量
#### respawn_anchor
* ##### explode
    - **默认值**: true
    - **描述**: 是否让重生锚爆炸。将此项如果为 false，那么 会使重生锚从存在中消失。
* ##### explosion-power
    - **默认值**: 5.0
    - **描述**: 爆炸的爆炸半径。（以 TNT 为例，TNT 爆炸力为 4.0，充能爬行者为 6.0）
* ##### explosion-fire
    - **默认值**: true
    - **描述**: 爆炸是否能引发火灾。
* ##### explosion-effect
    - **默认值**: BLOCK
    - **描述**: 爆炸对方块的影响。

      ???+ note "可用值"
      所有值都会摧毁方块。

            - `TNT` - 所有物品会掉落，除非设置了 `tntExplosionDropDecay` gamerule 为 `true`
            - `MOB` - 一些物品会掉落，除非设置了 `mobExplosionDropDecay` gamerule 为 `false`
            - `BLOCK` - 一些物品会掉落，除非设置了 `blockExplosionDropDecay` gamerule 为 `false`
            - `NONE` - 所有物品都会掉落。

#### sculk_shrieker
* ##### can-summon-default
    - **默认值**: false
    - **描述**: 如果为 true，那么将会放置时会将 `can_summon` 设置为 `true`。

#### shulker_box
* ##### allow-oversized-stacks
    - **默认值**: false
    - **描述**: 控制是否允许在潜影盒中放置超大堆叠物品（默认解决了 PaperMC/Paper#4748 的区块禁止问题）。

#### sign
* ##### allow-colors
    - 需要 [`purpur.sign.color`](permissions#purpursigncolor)、[`purpur.sign.style`](permissions#purpursignstyle) 和/或 [`purpur.sign.magic`](permissions#purpursignmagic) 权限。
    - **默认值**: false
    - **描述**: 允许玩家在告示牌上使用颜色代码。

#### slab
* ##### break-individual-slabs-when-sneaking
    - **默认值**: false
    - **描述**: 如果为 true，那么将会玩家在蹲下时可以打破双层板中的单个木板。

#### spawner
* ##### deactivate-by-redstone
    - **默认值**: false
    - **描述**: 允许红石使刷怪笼停用。
* ##### fix-mc-238526
    - **默认值**: false
    - **描述**: 修复刷怪笼未能正确生成水生生物的问题；MC-238526。

#### sponge
* ##### absorbs-lava
    - **默认值**: false
    - **描述**: 如果为 true，那么将会海绵可以吸收岩浆。
* ##### absorption
    * ###### area
        - **默认值**: 64
        - **描述**: 海绵吸水的方块区域。
    * ###### radius
        - **默认值**: 6
        - **描述**: 海绵吸水的半径。

#### stonecutter
* ##### damage
    - **默认值**: 0.0
    - **描述**: 如果设置了此值，生物会避免走到石切机上。

#### sugar_cane
* ##### affected-by-bonemeal
    - **默认值**: false
    - **描述**: 如果为 true，那么将会糖果甘蔗可以使用骨粉生长。

#### turtle_egg
* ##### break-from-exp-orbs
    - **默认值**: false
    - **描述**: 允许经验 orb 损坏/破坏海龟蛋。
* ##### break-from-items
    - **默认值**: false
    - **描述**: 允许掉落物损坏/破坏海龟蛋。
* ##### break-from-minecarts
    - **默认值**: false
    - **描述**: 允许矿车损坏/破坏海龟蛋。
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么将会海龟蛋可以绕过生物破坏规则（mob griefing）。
* ##### random-tick-crack-chance
    - **默认值**: 500
    - **描述**: 海龟蛋破裂的随机机会。
* ##### feather-fall-distance-affects-trampling
    - **默认值**: false
    - **描述**: 如果为 true，那么将会如果实体从高处掉落，等同于其羽毛掉落等级，且超过足够的高度，便会踏碎海龟蛋。羽毛掉落 1 需要从 3+ 方块高处掉落才能踏碎，羽毛掉落 2 需要从 4+ 方块高处掉落，以此类推。

#### water
* ##### infinite-required-sources
    - **默认值**: 2
    - **描述**: 使水源无限流动所需的水源数。

### mobs

#### allay
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可以骑乘。
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物可以在水中骑乘（不会将玩家弹出）。
* ##### respect-nbt
    - **默认值**: []
    - **描述**: 确保悦灵尊重其拾取物品的 NBT 数据。如果将存储的附魔添加到列表中，给悦灵一把带附魔的剑时，它将仅拾取相同附魔的剑。

#### axolotl
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可以骑乘。
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制。
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么将会该生物会受到水的伤害。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 可再次繁殖前需要等待的 ticks 数量。
* ##### attributes
    * ###### max_health
        - **默认值**: 14.0
        - **描述**: 最大生命属性。
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 规模属性。
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么将会该生物总是掉落经验。

#### bat
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可以骑乘。
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物可以在水中骑乘（不会将玩家弹出）。
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么将会该生物会受到水的伤害。
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 该生物在骑乘时最大可飞行的高度。
* ##### attributes
    * ###### follow_range
        - **默认值**: 16.0
        - **描述**: 跟随范围属性。
    * ###### knockback_resistance
        - **默认值**: 0.0
        - **描述**: 击退抵抗属性。
    * ###### movement_speed
        - **默认值**: 0.6
        - **描述**: 移动速度属性。
    * ###### flying_speed
        - **默认值**: 0.6
        - **描述**: 飞行速度属性。
    * ###### armor
        - **默认值**: 0.0
        - **描述**: 护甲属性。
    * ###### armor_toughness
        - **默认值**: 0.0
        - **描述**: 护甲韧性属性。
    * ###### attack_knockback
        - **默认值**: 0.0
        - **描述**: 攻击击退属性。
    * ###### max_health
        - **默认值**: 6.0
        - **描述**: 最大生命属性。
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 规模属性。
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么将会该生物总是掉落经验。

#### bee
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可以骑乘。
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物可以在水中骑乘（不会将玩家弹出）。
* ##### takes-damage-from-water
    - **默认值**: true
    - **描述**: 如果为 false，那么将会该生物停止受到水的伤害。
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 该生物在骑乘时最大可飞行的高度。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 可再次繁殖前需要等待的 ticks 数量。
* ##### can-work-at-night
    - **默认值**: false
    - **描述**: 控制蜜蜂是否可以在夜间工作。
* ##### can-work-in-rain
    - **默认值**: false
    - **描述**: 控制蜜蜂是否可以在雨天工作。
* ##### can-instantly-start-drowning
    - **默认值**: true 
    - **描述**: 如果禁用，蜜蜂将不会在触碰到水的瞬间立即开始受到伤害。蜜蜂仍然能够在水下因缺氧而“溺水”。
* ##### dies-after-sting
    - **默认值**: true 
    - **描述**: 设置蜜蜂是否在刺伤后死亡。
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### blaze
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true 
    - **描述**: 使此怪物在水中可骑乘（不会把你弹出）。
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 此怪物在被骑乘时可飞行的最大高度。
* ##### takes-damage-from-water
    - **默认值**: true 
    - **描述**: 如果为 false，那么 (否)将会此怪物将停止受到水的伤害。
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### camel
* ##### ridable-in-water
    - **默认值**: false (否)
    - **描述**: 使此怪物在水中可骑乘（不会把你弹出）。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待多少个 tick 后才能再次繁殖。
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 32.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 32.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.42
            - **描述**: 最小跳跃力量属性
        * max
            - **默认值**: 0.42
            - **描述**: 最大跳跃力量属性
    * ###### movement_speed
        * min
            - **默认值**: 0.09
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.09
            - **描述**: 最大移动速度属性
#### cat
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true 
    - **描述**: 使此怪物在水中可骑乘（不会把你弹出）。
* ##### takes-damage-from-water
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会此怪物会开始受到水的伤害。
* ##### default-collar-color
    - **默认值**: RED (红色)
    - **描述**: 设置当猫被驯服时的默认项圈颜色。[可用颜色]({{ project.javadoc }}/org/bukkit/Color.html)
* ##### spawn-delay
    - **默认值**: 1200
    - **描述**: 尝试自然生成猫之间的 tick 数量。
* ##### scan-range-for-other-cats
    * ###### swamp-hut
        - **默认值**: 16
        - **描述**: 如果在此范围内找到另一只猫，则不生成猫。设置为 0 (禁用)。
    * ###### village
        - **默认值**: 48
        - **描述**: 如果在此范围内找到另一只猫，则不生成猫。设置为 0 (禁用)。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待多少个 tick 后才能再次繁殖。
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### cave_spider
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true 
    - **描述**: 使此怪物在水中可骑乘（不会把你弹出）。
* ##### takes-damage-from-water
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会此怪物会开始受到水的伤害。
* ##### attributes
    * ###### max_health
        - **默认值**: 12.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### chicken
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: false (否)
    - **描述**: 使此怪物在水中不可骑乘（不会把你弹出）。
* ##### takes-damage-from-water
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会此怪物会开始受到水的伤害。
* ##### retaliate
    - **默认值**: false (否)
    - **描述**: 如果鸡被击中，它会反击。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待多少个 tick 后才能再次繁殖。
* ##### attributes
    * ###### max_health
        - **默认值**: 4.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### cod
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### takes-damage-from-water
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会此怪物会开始受到水的伤害。
* ##### attributes
    * ###### max_health
        - **默认值**: 3.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 体型属性
* ##### always-drop-exp
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会怪物会总是掉落经验。

#### cow
* ##### ridable
    - **默认值**: false (否)
    - **描述**: 使此怪物可骑乘。
* ##### controllable
    - **默认值**: true 
    - **描述**: 使此怪物可使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: true 
    - **描述**: 使此怪物在水中可骑乘（不会把你弹出）。
* ##### takes-damage-from-water
    - **默认值**: false (否)
    - **描述**: 如果为 true，那么 将会此怪物会开始受到水的伤害。
* ##### feed-mushrooms-for-mooshroom
    - **默认值**: 0
    - **描述**: 喂食多少个蘑菇给牛，才能让它变成蘑菇牛。值为 0 (禁用) 时此功能被禁用。
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待多少个 tick 后才能再次繁殖。
* ##### naturally-aggressive-to-players
    * ###### chance
        - **默认值**: 0.0
        - **描述**: 该生物生成时，向玩家表现出攻击性（0.0 - 1.0）的几率百分比
    * ###### damage
        - **默认值**: 2.0
        - **描述**: 该生物对玩家造成的伤害量
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### creaking
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### attributes
    * ###### max_health
        - **默认值**: 1.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
#### creeper
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### encircle-target
    - **默认值**: false
    - **描述**: 如果该生物点燃时围绕玩家旋转，如果为 true，那么
* ##### allow-griefing
    - **默认值**: true
    - **描述**: 如果为 false，那么 以阻止苦力怕破坏
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 以使苦力怕绕过生物破坏规则
* ##### naturally-charged-chance
    - **默认值**: 0.0
    - **描述**: 苦力怕生成时变为充能（激活状态）的几率百分比（0.0 - 1.0）
* ##### explode-when-killed
    - **默认值**: false
    - **描述**: 使苦力怕在被杀死时爆炸
* ##### health-impacts-explosion
    - **默认值**: false
    - **描述**: 使苦力怕的爆炸威力与其生命值成正比（生命值越低，爆炸越弱）
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### head-visibility-percent
    - **默认值**: 0.5
    - **描述**: 增加或减少该值，以使玩家佩戴生物头颅时的检测范围更小或更大
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### dolphin
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### naturally-aggressive-to-players-chance
    - **默认值**: 0.0
    - **描述**: 该生物生成时，向玩家表现出攻击性（0.0 - 1.0）的几率百分比
* ##### disable-treasure-searching
    - **默认值**: false
    - **描述**: 停止海豚寻宝
* ##### spit
    * ###### cooldown
        - **默认值**: 20
        - **描述**: 海豚吐痰的冷却时间
    * ###### speed
        - **默认值**: 1.0
        - **描述**: 海豚吐痰的速度
    * ###### damage
        - **默认值**: 2.0
        - **描述**: 海豚吐痰的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### donkey
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 再次繁殖之前要等待的 tick 数量
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 30.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.5
            - **描述**: 最小跳跃力量属性
        * max
            - **默认值**: 0.5
            - **描述**: 最大跳跃力量属性
    * ###### movement_speed
        * min
            - **默认值**: 0.175
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.175
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### drowned
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### can-break-doors
    - **默认值**: false
    - **描述**: 如果为 true，那么 允许溺尸破坏门
* ##### jockey
    * ###### only-babies
        - **默认值**: true
        - **描述**: 只有小型溺尸能骑乘小鸡
    * ###### chance
        - **默认值**: 0.05
        - **描述**: 溺尸生成时骑乘小鸡的几率百分比（0.0 - 1.0）
    * ###### try-existing-chickens
        - **默认值**: true
        - **描述**: 检查现有的小鸡是否可供骑乘
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### spawn_reinforcements
        - **默认值**: 0.1
        - **描述**: 该生物生成援军的几率百分比（0.0 - 1.0）
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### elder_guardian
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### attributes
    * ###### max_health
        - **默认值**: 80.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果该生物应始终掉落经验，如果为 true，那么
#### ender_dragon
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使此生物可用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 骑乘此生物时，生物能够飞行的最大高度
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果该生物会受到水的伤害，如果为 true，那么
* ##### always-drop-full-exp
    - **默认值**: false
    - **描述**: 如果为 true，所有有效的末影龙死亡事件将掉落完整的经验球数量，就像是第一次击败末影龙一样
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 让末影龙绕过生物破坏规则
* ##### can-ride-vehicles
    - **默认值**: false
    - **描述**: 如果为 true，那么 让末影龙能够骑乘载具
* ##### attributes
    * ###### max_health
        - **默认值**: 200.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
#### enderman
* ##### ridable
    - **默认值**: false
    - **描述**: 使此生物可骑乘
* ##### controllable
    - **默认值**: true
        - **描述**: 使此生物可用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
        - **描述**: 使此生物可在水中骑乘（不会将你弹出）
* ##### attributes
    * ###### max_health
        - **默认值**: 8.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### evoker
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使劫掠者绕过生物破坏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 24.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### fox
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### tulips-change-type
    - **默认值**: false
    - **描述**: 喂食白色/橙色郁金香改变类型为雪花/常规
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 在再次繁殖之前等待的刻数
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使狐狸绕过生物破坏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### frog
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### ridable-jump-height
    - **默认值**: 0.65
    - **描述**: 骑乘时该生物的跳跃高度（单位：方块）
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 在再次繁殖之前等待的刻数
#### ghast
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 骑乘时该生物可以飞到的最大高度
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### giant
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### step-height
    - **默认值**: 2.0
    - **描述**: 巨人可以不跳跃的情况下走过的方块数
* ##### jump-height
    - **默认值**: 1.0
    - **描述**: 跳跃高度修改器。默认值为 1.0 使巨人跳得大约与腰部同高
* ##### movement-speed
    - **默认值**: 0.5
    - **描述**: 移动速度属性
* ##### attack-damage
    - **默认值**: 50.0
    - **描述**: 攻击伤害（单位：半颗心）
* ##### have-ai
    - **默认值**: false
    - **描述**: 控制巨型僵尸是否有 AI，而不仅仅是站着不动
* ##### have-hostile-ai
    - **默认值**: false
    - **描述**: 控制巨型僵尸是否具有敌对 AI
* ##### attributes
    * ###### max_health
        - **默认值**: 100.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### glow_squid
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### can-fly
    - **默认值**: false
    - **描述**: 使鱿鱼可以飞行，天哪！
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### goat
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 在再次繁殖之前等待的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### guardian
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 30.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### hoglin
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 在再次繁殖之前等待的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 40.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### horse
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 在再次繁殖之前等待的刻数
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 30.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.4
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 1.0
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.1125
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.3375
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### husk
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### jockey
    * ###### only-babies
        - **默认值**: true
        - **描述**: 只有小鸡才能骑乘鸡
    * ###### chance
        - **默认值**: 0.05
        - **描述**: 生成时骑乘鸡的百分比几率（0.0 - 1.0）
    * ###### try-existing-chickens
        - **默认值**: true
        - **描述**: 扫描现有的鸡来生成
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
    * ###### spawn_reinforcements
        - **默认值**: 0.1
        - **描述**: 生成增援的百分比几率（0.0 - 1.0）
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### illusioner
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### naturally-spawn
    - **默认值**: false
    - **描述**: 控制幻术师是否自然生成
* ##### movement-speed
    - **默认值**: 0.5
    - **描述**: 移动速度属性
* ##### follow-range
    - **默认值**: 18.0
    - **描述**: 跟随范围属性
* ##### attributes
    * ###### max_health
        - **默认值**: 32.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### iron_golem
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### healing-calms-anger
    - **默认值**: false
    - **描述**: 当铁傀儡受到治疗时，如果它愤怒，它会冷静下来
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### can-spawn-in-air
    - **默认值**: false
    - **描述**: 设置铁傀儡是否可以像 1.12 及之前版本那样在空中生成
* ##### can-swim
    - **默认值**: false
    - **描述**: 设置铁傀儡是否可以游泳
* ##### poppy-calms-anger
    - **默认值**: false
    - **描述**: 给铁傀儡一朵罂粟花可以在它愤怒时安抚它

* ##### attributes
    * ###### max_health
        - **默认值**: 100.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### llama
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制。骆驼必须经过驯服并加上鞍（配有地毯）才能使用 WASD 控制。
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### join-caravans
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁用 [骆驼队列功能](https://minecraft.wiki/w/Llama#Caravans)
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 30.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.5
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 0.5
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.175
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.175
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### magma_cube
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: "size * size"
        - **描述**: 计算最大生命值的公式
    * ###### attack_damage
        - **默认值**: "size"
        - **描述**: 设置熔岩立方体的攻击伤害基准值
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### mooshroom
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### mule
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 30.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.5
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 0.5
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.175
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.175
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### ocelot
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### spawn-below-sea-level
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物生成在海平面以下
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### panda
* ##### ridable
    - **默认值**: false
    - **描述**: 使该生物可骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使该生物可以使用 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使该生物在水中可骑乘（不会将你弹出）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使该生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命值属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 尺寸属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果该生物应始终掉落经验
#### parrot
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 这个生物骑乘时能飞行的最大高度
* ##### can-breed
    - **默认值**: false
    - **描述**: 使鹦鹉能够使用任何种子繁殖（鹦鹉不会变成小鹦鹉，D:，所以会生成“成年”鹦鹉）
* ##### attributes
    * ###### max_health
        - **默认值**: 6.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### phantom
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attacked-by-crystal-range
    - **默认值**: 0.0
    - **描述**: 水晶扫描攻击幻翼的半径。0 的值禁用此功能
* ##### attacked-by-crystal-damage
    - **默认值**: 1.0
    - **描述**: 水晶每秒对幻翼造成的伤害量。1.0 的值表示半颗心
* ##### orbit-crystal-radius
    - **默认值**: 0.0
    - **描述**: 幻翼扫描水晶进行环绕的半径。0 的值禁用此功能
* ##### burn-in-light
    - **默认值**: 0
    - **描述**: 幻翼在何种光照下燃烧
* ##### burn-in-daylight
    - **默认值**: true
    - **描述**: 幻翼是否在白天燃烧
* ##### flames-on-swoop
    - **默认值**: false
    - **描述**: 如果为 true，那么 使幻翼在俯冲时发射火焰
* ##### ignore-players-with-torch
    - **默认值**: false
    - **描述**: 幻翼是否避开手持火把的玩家
* ##### allow-griefing
    - **默认值**: false
    - **描述**: 幻翼的火焰是否可以烧毁物品
* ###### size
    * min
        - **默认值**: 0
        - **描述**: 自然生成时随机选择的最小大小
    * max
        - **默认值**: 0
        - **描述**: 自然生成时随机选择的最大大小
* ##### spawn
    * ###### min-sky-darkness
        - **默认值**: 5
        - **描述**: 天空中的黑暗度（5 是雷暴天气的黑暗度，但不适用于普通雨天）
    * ###### only-above-sea-level
        - **默认值**: true
        - **描述**: 只在海平面以上的玩家处生成
    * ###### only-with-visible-sky
        - **默认值**: true
        - **描述**: 只在玩家上方有可见天空时生成
    * ###### local-difficulty-chance
        - **默认值**: 3.0
        - **描述**: 当地的难度必须大于一个在 0.0 和该值之间选择的随机数
    * ###### per-attempt
        * min
            - **默认值**: 1
            - **描述**: 每次尝试生成幻翼的最小数量
        * max
            - **默认值**: -1
            - **描述**: 每次尝试生成幻翼的最大数量（使用 -1 基于世界难度设置）
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### attack_damage
        - **默认值**: "6 + size"
        - **描述**: 幻翼的攻击伤害基础值
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### pig
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### give-saddle-back
    - **默认值**: false
    - **描述**: 按下蹲伏并右击一只背上有鞍的猪，可以移除鞍
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### piglin
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使猪灵绕过生物破坏游戏规则
* ##### portal-spawn-modifier
    - **默认值**: 2000
    - **描述**: 允许根据世界难度更改猪灵通过传送门生成的几率修正值。[更多内容请阅读这里]({{ project.source }}/blob/61fc0a557fc0eedececd63d44d43ce6431bc23bb/patches/server/0167-Piglin-portal-spawn-modifier.patch)
* ##### attributes
    * ###### max_health
        - **默认值**: 16.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### head-visibility-percent
    - **默认值**: 0.5
    - **描述**: 增加或减少百分比，以使得生物检测范围在玩家佩戴相应头部时变小或变大
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### piglin_brute
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 50.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### pillager
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使掠夺者绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 24.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### polar_bear
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### breedable-item
    - **默认值**: ""
    - **描述**: 用来诱使/喂养北极熊并让它们繁殖的物品
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 30.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### pufferfish
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 3.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果这个生物应该始终掉落经验

#### rabbit
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### spawn-killer-rabbit-chance
    - **默认值**: 0.0
    - **描述**: 杀手兔自然生成的几率（0.0-1.0）
* ##### spawn-toast-chance
    - **默认值**: 0.0
    - **描述**: 自然生成名为 Toast 的兔子的几率（0.0-1.0）
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使兔子绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 3.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果这个生物应该始终掉落经验

#### ravager
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使破坏者绕过生物破坏游戏规则
* ##### griefable-blocks
    - **默认值**:
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
    - **描述**: 破坏者可以破坏的方块白名单
* ##### attributes
    * ###### max_health
        - **默认值**: 100.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
* ##### avoid-rabbits
    - **默认值**: false
    - **描述**: 如果为 true，那么 如果这个生物应该避免兔子，类似于苦力怕避开猫的行为
#### salmon
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 3.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### sheep
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使羊绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 8.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### shulker
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### change-color-with-dye
    - **默认值**: false
    - **描述**: 通过右键点击染料来改变潜影贝的颜色
* ##### spawn-from-bullet:
    * ###### base-chance
        - **默认值**: 1.0
        - **描述**: 基础几率
    * ###### require-open-lid
        - **默认值**: true
        - **描述**: 如果为 true，那么 要求潜影贝的盖子打开才能从子弹中生成
    * ###### nearby-range
        - **默认值**: 8.0
        - **描述**: 检查潜影贝的附近范围
    * ###### nearby-equation
        - **默认值**: `(nearby - 1) / 5.0`
        - **描述**: 计算潜影贝从子弹生成的公式（`nearby` 是附近的潜影贝数量），如果将此留空，则附近有潜影贝时总是生成
    * ###### random-color
        - **默认值**: false
        - **描述**: 从子弹生成时，潜影贝的颜色随机
* ##### attributes
    * ###### max_health
        - **默认值**: 30.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性。最大不能超过 3.0
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### silverfish
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使银鱼绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 8.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### movement_speed
        - **默认值**: 0.25
        - **描述**: 移动速度属性
    * ###### attack_damage
        - **默认值**: 1.0
        - **描述**: 攻击伤害属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### skeleton
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 8.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### head-visibility-percent
    - **默认值**: 0.5
    - **描述**: 增加或减少该生物的头部可见范围，玩家佩戴相应的生物头时，检测范围变得更小或更大
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
* ##### feed-wither-roses
    - **默认值**: 0
    - **描述**: 右键点击骷髅时持有凋零玫瑰会将骷髅转化为凋零骷髅。值表示需要多少凋零玫瑰来转化骷髅，0 表示该功能被禁用
* ##### bow-accuracy
    - **默认值**: 14 - difficulty * 4
    - **描述**: 改变骷髅射箭的准确度。公式的结果是发散度（散布）。数值越高，射击越不准确。
      ``` yaml
      easy:   14 - 1 * 4 = 10
      normal: 14 - 2 * 4 = 6
      hard:   14 - 3 * 4 = 2
      ```
#### skeleton_horse
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### can-swim
    - **默认值**: false
    - **描述**: 骷髅马是否能在水中游泳。如果为 false，那么将会它们会沉到水底（原版默认）
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命属性
        * max
            - **默认值**: 15.0
            - **描述**: 最大生命属性
    * ###### jump_strength
        * min
            - **默认值**: 0.4
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 1.0
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.2
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.2
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### slime
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### attributes
    * ###### max_health
        - **默认值**: "size * size"
        - **描述**: 用于计算最大生命的公式
    * ###### attack_damage
        - **默认值**: "size"
        - **描述**: 用于计算史莱姆攻击伤害的基础数值
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### sniffer
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
    - **默认值**: 14.0
    - **描述**: 最大生命属性
#### snow_golem
???+ info "用于确定射击之间的刻数公式"
``` sh
((sqrt(distanceToTarget) / attack-distance) / snow-ball-modifier) * (max-shoot-interval-ticks - min-shoot-interval-ticks) + min-shoot-interval-ticks
```
如果 `min-shoot-interval-ticks` 和 `max-shoot-interval-ticks` 都设置为 0，雪人将不会射击雪球。

* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### leave-trail-when-ridden
    - **默认值**: false
    - **描述**: 骑乘时，雪人行走时会留下轨迹
* ##### pumpkin-can-be-added-back
    - **默认值**: false
    - **描述**: 控制是否可以将南瓜放回雪人身上
* ##### min-shoot-interval-ticks
    - **默认值**: 20
    - **描述**: 最小射击间隔刻数
* ##### max-shoot-interval-ticks
    - **默认值**: 20
    - **描述**: 最大射击间隔刻数
* ##### snow-ball-modifier
    - **默认值**: 10.0
    - **描述**: 雪球弹射物的修改值
* ##### attack-distance
    - **默认值**: 1.25
    - **描述**: 雪人攻击的距离
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使雪人绕过生物破坏游戏规则
* ##### takes-damage-from-water
    - **默认值**: true
    - **描述**: 如果为 false，那么 使这个生物停止受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 4.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### spider
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 16.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### squid
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### immune-to-EAR
    - **默认值**: true
    - **描述**: 使这个生物免疫 EAR（实体激活范围 - 请参阅 spigot.yml）
* ##### water-offset-check
    - **默认值**: 0.0
    - **描述**: 防止乌贼浮在水面上
* ##### can-fly
    - **默认值**: false
    - **描述**: 使乌贼可以飞行，哇哦！
* ##### attributes
    * ###### max_health
        - **默认值**: 10.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### stray
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### strider
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### give-saddle-back
    - **默认值**: false
    - **描述**: 按下 shift 并右键点击骑在其上的爬行者以移除其背上的鞍
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### takes-damage-from-water
    - **默认值**: true
    - **描述**: 如果为 false，那么 使这个生物不再受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### tadpole
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
#### trader_llama
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制。商人 llamas 必须被驯服才能通过 WASD 控制。骑鞍（地毯）不是必需的，因为它默认总是带有地毯。
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命属性
        * max
            - **默认值**: 30.0
            - **描述**: 最大生命属性
    * ###### jump_strength
        * min
            - **默认值**: 0.5
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 0.5
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.175
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.175
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### tropical_fish
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 3.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### turtle
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 30.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### vex
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 这个生物骑乘时能飞行的最大高度
* ##### attributes
    * ###### max_health
        - **默认值**: 14.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### villager
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 忽略 `mobGriefing` 游戏规则并允许村民掉落物品，允许他们繁殖
* ##### can-be-leashed
    - **默认值**: false
    - **描述**: 允许玩家用牵引绳抓住村民（商人除外）
* ##### follow-emerald-blocks
    - **默认值**: false
    - **描述**: 村民会被绿宝石方块吸引并跟随持有它们的玩家
* ##### allow-trading
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁用与村民交易
* ##### display-trade-item
    - **默认值**: true
    - **描述**: 如果为 false，那么 停止村民展示交易物品
* ##### lobotomize
    * ###### enabled
        - **默认值**: false
        - **描述**: 如果村民无法移动则会被 lobotomize（不禁用交易）
    * ###### check-interval
        - **默认值**: 100
        - **描述**: 检查村民是否被 lobotomize 的间隔（以刻为单位）
    * ###### wait-until-trade-locked
        - **默认值**: false
        - **描述**: 等待直到与村民交易过后再进行 lobotomize
* ##### minimum-demand
    - **默认值**: 0
    - **描述**: 解决 MC-163962 中村民需求无限减少的问题。Paper 添加了一个补丁，防止需求值低于零。此选项允许配置最低需求。
* ##### can-breed
    - **默认值**: true
    - **描述**: 是否允许村民繁殖
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### clerics-farm-warts
    - **默认值**: false
    - **描述**: 如果为 true，那么 使牧师种植下界疣
* ##### cleric-wart-farmers-throw-warts-at-villagers
    - **默认值**: true
    - **描述**: 如果为 false，那么 使牧师不再向其他村民投掷下界疣
* ##### spawn-iron-golem
    * ###### radius
        - **默认值**: 0
        - **描述**: 村民搜索现有铁傀儡的半径，超出范围无法生成更多。值为 0 禁用该功能
    * ###### limit
        - **默认值**: 0
        - **描述**: 村民在配置的半径内最多能生成多少个铁傀儡
* ##### search-radius
    * ###### acquire-poi
        - **默认值**: 48
        - **描述**: 村民搜索获取 POI 的半径
    * ###### nearest-bed-sensor
        - **默认值**: 48
        - **描述**: 村民搜索检测最近床铺的半径
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### tempt_range
        - **默认值**: 10.0
        - **描述**: 诱惑范围属性。只有启用 `follow-emerald-blocks` 时才生效
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### vindicator
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### johnny
    * ###### spawn-chance
        - **默认值**: 0.0
        - **描述**: 百分比机会（0.0 - 1.0）生成一个名为“Johnny”的复仇者，而不是普通复仇者
* ##### attributes
    * ###### max_health
        - **默认值**: 24.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### wandering_trader
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### can-be-leashed
    - **默认值**: false
    - **描述**: 允许玩家使用牵引绳拴住村民（不包括交易商）
* ##### allow-trading
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁用与流浪商人交易
* ##### follow-emerald-blocks
    - **默认值**: false
    - **描述**: 村民将被绿宝石方块吸引，并跟随持有这些方块的玩家
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### tempt_range
        - **默认值**: 10.0
        - **描述**: 吸引范围属性。仅在启用 `follow-emerald-blocks` 时有效
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### warden
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）

#### witch
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 26.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### wither
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### ridable-max-y
    - **默认值**: 256
    - **描述**: 这个生物骑乘时能飞行的最大高度
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### can-ride-vehicles
    - **默认值**: false
    - **描述**: 如果为 true，那么 使凋零能骑乘载具
* ##### play-spawn-sound
    - **默认值**: true
    - **描述**: 当凋零生成时，播放其生成音效
* ##### explosion-radius
    - **默认值**: 1.0
    - **描述**: 凋零弹射物攻击的爆炸半径
* ##### health-regen-amount
    - **默认值**: 1.0
    - **描述**: 凋零的生命恢复量
* ##### health-regen-delay
    - **默认值**: 20
    - **描述**: 延迟恢复生命的时间
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使凋零绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 300.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### wither_skeleton
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### wolf
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### milk-cures-rabid-wolves
    - **默认值**: true
    - **描述**: 如果为 false，那么 使狂犬病狼不能通过牛奶治愈
* ##### spawn-rabid-chance
    - **默认值**: 0.0
    - **描述**: 百分比机会（0.0 - 1.0）使狼生成时带有狂犬病
* ##### default-collar-color
    - **默认值**: RED
    - **描述**: 设置狼被驯服时的默认项圈颜色。[可用颜色]({{ project.javadoc }}/org/bukkit/Color.html)
* ##### breeding-delay-ticks
    - **默认值**: 6000
    - **描述**: 等待再次繁殖的刻数
* ##### attributes
    * ###### max_health
        - **默认值**: 8.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### zoglin
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### attributes
    * ###### max_health
        - **默认值**: 40.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

#### zombie
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### jockey
    * ###### only-babies
        - **默认值**: true
        - **描述**: 只有小型僵尸可以骑乘小鸡
    * ###### chance
        - **默认值**: 0.05
        - **描述**: 百分比机会（0.0 - 1.0）使生成的僵尸骑乘小鸡
    * ###### try-existing-chickens
        - **默认值**: true
        - **描述**: 尝试扫描现有的小鸡并在其上生成
* ##### aggressive-towards-villager-when-lagging
    - **默认值**: true
    - **描述**: 如果为 false，那么 以停止僵尸在游戏延迟时对村民的攻击
* ##### bypass-mob-griefing
    - **默认值**: false
    - **描述**: 如果为 true，那么 使僵尸绕过生物破坏游戏规则
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### spawn_reinforcements
        - **默认值**: 0.1
        - **描述**: 百分比机会（0.0 - 1.0）使僵尸生成援军
* ##### head-visibility-percent
    - **默认值**: 0.5
    - **描述**: 增加或减少该生物的头部可见度百分比，影响玩家戴上该生物头颅时的检测范围
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### zombie_horse
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### spawn-chance
    - **默认值**: 0.0
    - **描述**: 生成僵尸马的几率（0.0 - 1.0）（暴风雨中自然生成）
* ##### attributes
    * ###### max_health
        * min
            - **默认值**: 15.0
            - **描述**: 最小生命值属性
        * max
            - **默认值**: 15.0
            - **描述**: 最大生命值属性
    * ###### jump_strength
        * min
            - **默认值**: 0.4
            - **描述**: 最小跳跃强度属性
        * max
            - **默认值**: 1.0
            - **描述**: 最大跳跃强度属性
    * ###### movement_speed
        * min
            - **默认值**: 0.2
            - **描述**: 最小移动速度属性
        * max
            - **默认值**: 0.2
            - **描述**: 最大移动速度属性
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### zombie_villager
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### cure
    * ###### enabled
        - **默认值**: true
        - **描述**: 如果为 false，那么 停止僵尸村民的治愈
* ##### curing_time
    * ###### min
        - **默认值**: 3600
        - **描述**: 治愈所需的最小刻数
    * ###### max
        - **默认值**: 6000
        - **描述**: 治愈所需的最大刻数
* ##### jockey
    * ###### only-babies
        - **默认值**: true
        - **描述**: 只有幼崽可以骑乘鸡
    * ###### chance
        - **默认值**: 0.05
        - **描述**: 生成时骑乘鸡的几率（0.0 - 1.0）
    * ###### try-existing-chickens
        - **默认值**: true
        - **描述**: 扫描现有的鸡进行生成
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### spawn_reinforcements
        - **默认值**: 0.1
        - **描述**: 生成增援的几率（0.0 - 1.0）
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么
#### zombified_piglin
* ##### ridable
    - **默认值**: false
    - **描述**: 使这个生物可以骑乘
* ##### controllable
    - **默认值**: true
    - **描述**: 使这个生物可以通过 WASD 控制
* ##### ridable-in-water
    - **默认值**: true
    - **描述**: 使这个生物在水中可以骑乘（不会把你弹下去）
* ##### takes-damage-from-water
    - **默认值**: false
    - **描述**: 如果为 true，那么 使这个生物开始受到水的伤害
* ##### count-as-player-kill-when-angry
    - **默认值**: true
    - **描述**: 如果为 false，那么 停止僵尸猪灵被玩家激怒时掉落经验（但不被杀死）
* ##### jockey
    * ###### only-babies
        - **默认值**: true
        - **描述**: 只有幼崽可以骑乘鸡
    * ###### chance
        - **默认值**: 0.05
        - **描述**: 生成时骑乘鸡的几率（0.0 - 1.0）
    * ###### try-existing-chickens
        - **默认值**: true
        - **描述**: 扫描现有的鸡进行生成
* ##### attributes
    * ###### max_health
        - **默认值**: 20.0
        - **描述**: 最大生命属性
    * ###### scale
        - **默认值**: 1.0
        - **描述**: 缩放属性
    * ###### spawn_reinforcements
        - **默认值**: 0.0
        - **描述**: 生成增援的几率（0.0 - 1.0）
* ##### always-drop-exp
    - **默认值**: false
    - **描述**: 如果这个生物应该始终掉落经验，如果为 true，那么

### gameplay-mechanics

#### always-tame-in-creative
- **默认值**: false
- **描述**: 如果为 true，那么 使得在创造模式中百分之百驯服生物
#### animal-breeding-cooldown-seconds
- **默认值**: 0
- **描述**: 为每种动物添加繁殖冷却时间（以秒为单位）
#### armorstand
* ##### step-height
    - **默认值**: 0.0
    - **描述**: 设置盔甲架的默认跨步高度。对于将盔甲架作为交通工具的插件非常有用，可以不跳跃跨越方块等
* ##### set-name-visible-when-placing-with-custom-name
    - **默认值**: false
    - **描述**: 在放置时如果设置了自定义名称，使名称可见
* ##### fix-nametags
    - **默认值**: false
    - **描述**: 使用名字标签时，使盔甲架的名字可见
* ##### place-with-arms-visible
    - **默认值**: false
    - **描述**: 放置时使盔甲架的手臂可见
* ##### can-movement-tick
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁止盔甲架移动
* ##### can-move-in-water
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁止盔甲架在水中移动
* ##### can-move-in-water-over-fence
    - **默认值**: true
    - **描述**: 如果为 false，那么 禁止盔甲架在水中跨越围栏
#### arrow
* ##### movement-resets-despawn-counter
    - **默认值**: true
    - **描述**: 如果为 false，那么 防止箭矢在脱离存活状态时被无限延长存活时间（例如箭矢卡住的方块被移除时）
#### boat
* ##### eject-players-on-land
    - **默认值**: false
    - **描述**: 如果为 true，那么船在陆地上时玩家将会被弹出。
* ##### do-fall-damage
    - **默认值**: false
    - **描述**: 如果为 false，那么坐在船上时玩家不会受到摔落伤害。
#### clamp-explosion-radius
- **默认值**: true
- **描述**: 如果为 false，那么允许对爆炸半径设置负值。
#### daylight-cycle-ticks
* ##### daytime
    - **默认值**: 12000
    - **描述**: 设置白天的刻数。
* ##### nighttime
    - **默认值**: 12000
    - **描述**: 设置夜晚的刻数。
#### disable-drops-on-cramming-death
- **默认值**: false
- **描述**: 如果生物被压死，则不会掉落物品。
#### disable-oxidation-proximity-penalty
- **默认值**: false
- **描述**: 如果为 true，那么使铜块在附近没有氧化铜块时不受氧化惩罚。
#### drowning
* ##### air-ticks
    - **默认值**: 300
    - **描述**: 在开始窒息之前，你可以在水下呼吸的时间（以刻为单位）
* ##### ticks-per-damage
    - **默认值**: 20
    - **描述**: 每次窒息伤害之间的间隔刻数。
* ##### damage-from-drowning
    - **默认值**: 2.0
    - **描述**: 窒息造成的伤害。
#### elytra
* ##### damage-per-second
    - **默认值**: 1
    - **描述**: 每秒飞行时，鞘翅的耐久度消耗。
* ##### damage-multiplied-by-speed
    - **默认值**: 0.0
    - **描述**: 如果飞行速度大于设定速度，伤害将按速度放大。0 值禁用此乘数。
* ##### kinetic-damage
    - **默认值**: true
    - **描述**: 玩家飞行撞击墙面时是否受到伤害。
* ##### ignore-unbreaking
    - **默认值**: false
    - **描述**: 是否忽略鞘翅的耐久附魔。
* ##### damage-per-boost
    * ###### firework
        - **默认值**: 0
        - **描述**: 当使用烟花加速时，鞘翅的耐久损耗。
    * ###### trident
        - **默认值**: 0
        - **描述**: 当使用三叉戟加速时，鞘翅的耐久损耗。
#### entities-can-use-portals
- **默认值**: true
- **描述**: 如果为 false，那么禁止实体使用传送门。
#### entities-pick-up-loot-bypass-mob-griefing
- **默认值**: false
- **描述**: 即使禁用了 `mobGriefing` 游戏规则，可以拾取物品的生物仍然会继续拾取物品。
#### entity-blindness-multiplier
- **默认值**: 1
- **描述**: 当实体受到失明药水效果影响时的失明程度。
#### entity-left-handed-chance
- **默认值**: 0.05
- **描述**: 实体出生时使用左手的几率（0.0 - 1.0）。
#### entity-lifespan
- **默认值**: 0
- **描述**: 实体在消失之前生存的刻数。与玩家互动会重置计时器。
#### fireballs-bypass-mob-griefing
- **默认值**: false
- **描述**: 如果为 true，那么使火球绕过生物破坏游戏规则。
#### halloween
* ##### force
    - **默认值**: false
    - **描述**: 如果为 true，那么强制世界进入万圣节模式。
* ##### head-chance
    - **默认值**: 0.25
    - **描述**: 僵尸或骷髅生成时戴着南瓜灯或雕刻南瓜头的几率。
#### impose-teleport-restrictions-on-end-portals
- **默认值**: false
- **描述**: 如果为 true，那么对末地传送门增加传送限制。
#### impose-teleport-restrictions-on-gateways
- **默认值**: false
- **描述**: 如果为 true，那么对末地折跃门增加传送限制。
#### impose-teleport-restrictions-on-nether-portals
- **默认值**: false
- **描述**: 如果为 true，那么对下界传送门增加传送限制。
#### infinity-bow
* ##### works-without-arrows
    - **默认值**: false
    - **描述**: 如果为 true，那么使无限弓无需箭矢也能使用。
#### item
* ##### end-crystal
    * ###### place-anywhere
        - **默认值**: false
        - **描述**: 允许将末影水晶放置在任何方块上，而不仅仅是放置在黑曜石或基岩上。
* ##### shears
    * ###### damage-if-sprinting
        - **默认值**: false
        - **描述**: 在冲刺时手持剪刀是否对玩家造成随机伤害（不要跑着拿剪刀！）。对于具有 `item_model` 组件或 `custom_model_data` 组件的剪刀不会激活此效果。
    * ###### damage-if-sprinting-item-model
        - **默认值**: "purpurmc:scissors"
        - **描述**: 剪刀使用的 `item_model` 的资源位置。（需要启用 `damage-if-sprinting`）
    * ###### ignore-in-water
        - **默认值**: false
        - **描述**: 是否在水中忽略冲刺伤害。（需要启用 `damage-if-sprinting`）
    * ###### ignore-in-lava
        - **默认值**: false
        - **描述**: 是否在岩浆中忽略冲刺伤害。（需要启用 `damage-if-sprinting`）
    * ###### sprinting-damage
        - **默认值**: 1
        - **描述**: 冲刺时对玩家造成的伤害值。（需要启用 `damage-if-sprinting`）
    * ###### defuse-tnt-chance
        - **默认值**: 0.0
        - **描述**: 右键点击引爆的 TNT将会解除引爆的几率（0.0 - 1.0）。
* ##### snowball
    * ###### extinguish
        * ###### fire
            - **默认值**: false
            - **描述**: 投掷雪球时是否熄灭火焰。
        * ###### candles
            - **默认值**: false
            - **描述**: 投掷雪球时是否熄灭蜡烛。
        * ###### campfires
            - **默认值**: false
            - **描述**: 投掷雪球时是否熄灭篝火。
* ##### shulker_box
    * ###### drop-contents-when-destroyed
        - **默认值**: true
        - **描述**: 破坏时是否掉落潜影盒内的物品。
* ##### compass
    * ###### holding-shows-bossbar
        - **默认值**: false
        - **描述**: 手持指南针时是否显示 [`/compass`](commands#compass) 命令的 bossbar。
* ##### glow_berries
    * ###### eat-glow-duration
        - **默认值**: 0
        - **描述**: 玩家吃下发光浆果后发光的持续时间（以刻为单位）。设置为 0 以禁用。
* ##### ender-pearl
    * ###### damage
        - **默认值**: 5
        - **描述**: 使用末影珍珠传送后所受到的伤害。
    * ###### cooldown
        - **默认值**: 20
        - **描述**: 使用末影珍珠后的冷却时间（以刻为单位）。
    * ###### creative-cooldown
        - **默认值**: 20
        - **描述**: 在创造模式下使用末影珍珠后的冷却时间（以刻为单位）。
    * ###### endermite-spawn-chance
        - **默认值**: 0.05
        - **描述**: 使用末影珍珠传送后生成末影螨的概率（0.0 - 1.0）。
* ##### immune
    * ###### explosion
        - **默认值**: []
        - **描述**: 免受爆炸伤害的物品列表。
    * ###### fire
        - **默认值**: []
        - **描述**: 免受火焰伤害的物品列表。
    * ###### lightning
        - **默认值**: []
        - **描述**: 免受闪电伤害的物品列表。
    * ###### cactus
        - **默认值**: []
        - **描述**: 免受仙人掌伤害的物品列表。
          ???+ 注释 "物品免疫列表示例:"
        ``` yaml
        explosion:
          - minecraft:diamond
          - minecraft:diamond_block
          - minecraft:diamond_sword
        ```

???+ warning "警告"
这可能会导致客户端的同步问题，例如地上的物品不可见！这从服务器端代码无法解决。

#### mending-multiplier
- **默认值**: 1.0
- **描述**: 修复物品的效果强度，数值越高修复物品所消耗的经验越少。（1.0 = 100%）
#### milk-clears-beneficial-effects
- **默认值**: true
- **描述**: 如果为 false，那么牛奶将会只清除负面状态效果。
#### milk-cures-bad-omen
- **默认值**: true
- **描述**: 允许玩家通过喝牛奶来解除不祥之兆效果。
#### minecart
* ##### max-speed
    - **默认值**: 0.4
    - **描述**: 矿车最大速度。
* ##### place-anywhere
    - **默认值**: false
    - **描述**: 矿车是否可以放置在任何地方，而不仅仅是铁轨上。
* ##### powered-rail
    * ###### boost-modifier
        - **默认值**: 0.06
        - **描述**: 矿车开上充能铁轨后获得的速度增益（熔炉矿车不受影响）。
* ##### controllable
    * ###### enabled
        - **默认值**: false
        - **描述**: 在不在铁轨上时，矿车是否可以受到玩家的方向控制。
    * ###### fall-damage
        - **默认值**: true
        - **描述**: 如果为 true，那么玩家在矿车中将会受到摔落伤害。
    * ###### step-height
        - **默认值**: 1.0
        - **描述**: 矿车可以在不跳跃的情况下，跨越的最大方块高度。
    * ###### hop-boost
        - **默认值**: 0.5
        - **描述**: 按空格键时矿车的跳跃增益。
    * ###### base-speed
        - **默认值**: 0.1
        - **描述**: 矿车最低速度。
    * ###### block-speed
        - **默认值**:
            ``` yaml
            grass_block: 0.3
            stone: 0.5
            ```
        - **描述**: 矿车在每种不同方块上的移动速度。
#### mob-effects
* ##### health-regen-amount
    - **默认值**: 1.0
    - **描述**: 生命恢复效果对实体的生命恢复量。
* ##### minimal-health-poison-amount
    - **默认值**: 1.0
    - **描述**: 中毒效果对实体的最小毒性影响量。
* ##### poison-degeneration-amount
    - **默认值**: 1.0
    - **描述**: 中毒效果对实体的毒性量。
* ##### wither-degeneration-amount
    - **默认值**: 1.0
    - **描述**: 虚弱效果对实体的虚弱量。
* ##### hunger-exhaustion-amount
    - **默认值**: 0.005
    - **描述**: 饥饿效果对实体的饥饿度消耗量。
* ##### saturation-regen-amount
    - **默认值**: 1.0
    - **描述**: 饱和效果对实体的饱和度恢复量。
#### mob-last-hurt-by-player-time
- **默认值**: 100
- **描述**: 允许你改变一个生物在被玩家攻击后死亡计为玩家击杀所需的刻数（通过弹射物或直接攻击）
#### mob-spawning
* ##### village-cats
    - **默认值**: default
    - **描述**: 如果为 true，那么这个世界的村庄中将会生成猫。
* ##### raid-patrols
    - **默认值**: default
    - **描述**: 如果为 true，那么这个世界中将会生成袭击巡逻队。
* ##### phantoms
    - **默认值**: default
    - **描述**: 如果为 true，那么这个世界中将会生成幻翼。
* ##### wandering-traders
    - **默认值**: default
    - **描述**: 如果为 true，那么这个世界中将会生成流浪商人。
* ##### village-sieges
    - **默认值**: default
    - **描述**: 如果为 true，那么这个世界中将会启用袭击。
* ##### ignore-creative-players
    - **默认值**: false
    - **描述**: 创造模式玩家是否计入最大生物生成计数。
#### mobs-ignore-rails
- **默认值**: false
- **描述**: 如果为 true，那么允许生物穿过铁轨。
#### note-block-ignore-above
- **默认值**: false
- **描述**: 如果为 true，那么即使有方块在上放，音符盒仍可以发出声音。
#### persistent-droppable-entity-display-names
- **默认值**: true
- **描述**: 如果为 true，那么实体的显示名称和说明在破坏为物品状态后仍然保留（例如命名的盔甲架保持其名称）。
#### persistent-tileentity-display-name
- **默认值**: true
- **描述**: 如果为 false，那么禁用一直显示方块实体（TE）显示名称（例如看向命名的自定义玩家头像时才显示其名称）。
#### persistent-tileentity-lore
- **默认值**: false
- **描述**: 如果为 true，那么使 TE 的说明在破坏后仍然保留（例如带有说明的自定义玩家头像保持其说明）。
#### player
* ##### exp-pickup-delay-ticks
    - **默认值**: 2
    - **描述**: 玩家捡起掉落的经验的延迟（单位为游戏刻）。
* ##### shift-right-click-repairs-mending-points
    - **默认值**: 0
    - **描述**: 手持物品时，蹲下右键修复附魔经验修补的物品将花费的经验点数（设置为 0 以禁用）。
* ##### spawn-invulnerable-ticks
    - **默认值**: 60
    - **描述**: 控制玩家出生时的无敌时间（单位为游戏刻）。
* ##### invulnerable-while-accepting-resource-pack
    - **默认值**: false
    - **描述**: 玩家下载资源包时是否进入无敌状态。
* ##### teleport-if-outside-border
    - **默认值**: false
    - **描述**: 如果玩家进入世界边界外，则将其传送回出生点。
* ##### teleport-on-nether-ceiling-damage
    - **默认值**: false
    - **描述**: 如果玩家在下界的基岩层天花板上受到伤害，将其传送回出生点。
* ##### allow-void-trading
    - **默认值**: false
    - **描述**: 允许虚空交易。
* ##### totem-of-undying-works-in-inventory
    - **默认值**: false
    - **描述**: 允许不死图腾在玩家的任何背包格中生效，而不仅仅是在副手。
* ##### ridable-in-water
    - **默认值**: false
    - **描述**: 允许在水中骑乘生物/玩家。
* ##### fix-stuck-in-portal
    - **默认值**: false
    - **描述**: 如果玩家被困在传送门内且无法出去，走到另一个方块上时将重置传送门冷却时间，使其可以再次传送。
* ##### one-punch-in-creative
    - **默认值**: false
    - **描述**: 如果玩家处于创造模式并用空手击打实体，实体会立即死亡。
* ##### sleep-ignore-nearby-mobs
    - **默认值**: false
    - **描述**: 如果为 true，那么即使附近有敌对生物也能睡觉。
* ##### can-skip-night
    - **默认值**: true
    - **描述**: 如果为 false，那么玩家通过睡觉跳过夜晚将会被禁用。
* ##### critical-damage-multiplier
    - **默认值**: 1.5
    - **描述**: 暴击攻击对基础伤害的百分比加成。
* ##### burp-when-full
    - **默认值**: false
    - **描述**: 玩家吃饱后是否可以发出打嗝声。
* ##### burp-delay
    - **默认值**: 10
    - **描述**: 打嗝声音的延迟时间；`burp-when-full` 选项必须启用。
* ##### curse-of-binding
    * ###### remove-with-weakness
        - **默认值**: false
        - **描述**: 允许玩家在受到虚弱效果时脱下附魔绑定诅咒的盔甲。
* ##### idle-timeout
    * ###### kick-if-idle
        - **默认值**: true
        - **描述**: 如果玩家处于挂机状态则将其踢出（参见 server.properties 中的 player-idle-timeout 时间）。
    * ###### tick-nearby-entities
        - **默认值**: true
        - **描述**: 当附近玩家处于挂机状态时，实体是否正常进行 tick。如果为 false，那么需要至少一个活动玩家才能触发实体 tick。
    * ###### mobs-target
        - **默认值**: true
        - **描述**: 生物是否会攻击附近的挂机玩家。
    * ###### count-as-sleeping
        - **默认值**: false
        - **描述**: 挂机玩家是否算作正在睡觉？（允许活跃玩家通过睡觉跳过夜晚，即使挂机玩家不在床上）
    * ###### update-tab-list
        - **默认值**: false
        - **描述**: 挂机玩家在 TAB 列表中名字前是否加上 `[AFK]`。
* ##### exp-dropped-on-death
    * ###### equation
        - **默认值**: expLevel * 7
        - **描述**: 死亡时掉落的经验数量。可用的 NMS 变量有 `expLevel`、`expTotal` 和 `exp`。
    * ###### maximum
        - **默认值**: 100
        - **描述**: 死亡时掉落的最大经验量。
* ##### netherite-fire-resistance
    * ###### duration
        - **默认值**: 0
        - **描述**: 设置火焰抗性效果持续时间。设置为 0 以禁用。
    * ###### amplifier
        - **默认值**: 0
        - **描述**: 设置火焰抗性效果的等级。
    * ###### ambient
        - **默认值**: false
        - **描述**: 如果为 true，那么将会使粒子效果对客户端屏幕的干扰更小。
    * ###### show-particles
        - **默认值**: false
        - **描述**: 如果为 true，那么将会显示火焰抗性药水效果粒子。
    * ###### show-icon
        - **默认值**: true
        - **描述**: 如果为 false，那么客户端将会不显示火焰抗性效果的图标。
#### projectile-damage
* ##### snowball
    - **默认值**: -1
    - **描述**: 设置雪球的造成的伤害（-1 会对烈焰人造成 3 点伤害，对所有其他实体为 0，默认值）。
#### projectile-offset
* ##### bow
    - **默认值**: 1.0
    - **描述**: 弓箭的弹射物偏移。
* ##### crossbow
    - **默认值**: 1.0
    - **描述**: 弩的弹射物偏移。
* ##### egg
    - **默认值**: 1.0
    - **描述**: 鸡蛋的弹射物偏移。
* ##### ender-pearl
    - **默认值**: 1.0
    - **描述**: 末影珍珠的弹射物偏移。
* ##### throwable-potion
    - **默认值**: 1.0
    - **描述**: 可投掷药水的弹射物偏移。
* ##### trident
    - **默认值**: 1.0
    - **描述**: 三叉戟的弹射物偏移。
* ##### snowball
    - **默认值**: 1.0
    - **描述**: 雪球的弹射物偏移。
#### projectiles-bypass-mob-griefing
* **默认值**: false
* **描述**: 如果为 true，那么弹射物可以无视 doMobGriefing 的值进行破坏。
#### raid-cooldown-seconds
- **默认值**: 0
- **描述**: 在另一次袭击开始之前应等待的时间。
#### rain-stops-after-sleep
- **默认值**: true
- **描述**: 如果为 false，那么玩家睡觉后仍将继续下雨。
#### shovel-turns-block-to-grass-path
- **默认值**:
    ``` yaml
    - minecraft:coarse_dirt
    - minecraft:dirt
    - minecraft:grass_block
    - minecraft:mycelium
    - minecraft:podzol
    - minecraft:rooted_dirt
    ```
- **描述**: 规定可以将那些方块通过铲子右键转换为草径。
#### silk-touch
需要 [`purpur.drop.spawners`](permissions#purpurdropspawners) 和 [`purpur.place.spawners`](permissions#purpurplacespawners) 权限
* ##### enabled
    - **默认值**: false
    - **描述**: 如果设置为 true ，那么你可以使用附魔了精准采集的工具来挖掘刷怪笼。
* ##### minimal-level
    - **默认值**: 1
    - **描述**: 获取刷怪笼时所需的最低挖掘等级。
* ##### tools
    - **默认值**:
    ``` yaml
    - minecraft:iron_pickaxe
    - minecraft:golden_pickaxe
    - minecraft:diamond_pickaxe
    - minecraft:netherite_pickaxe
    ```
    - **描述**: 允许使用精准采集挖掘刷怪笼的工具列表。
* ##### spawner-name
    - **默认值**: "&lt;reset>&lt;white> 刷怪笼"
    - **描述**: 刷怪笼的名称。
* ##### spawner-lore
    - **默认值**:
        ``` yaml
        - 生成一个 <mob>
        ```
    - **描述**: 刷怪笼的说明。
#### thunder-stops-after-sleep
- **默认值**: true
- **描述**: 如果为 false，那么雷暴在玩家睡觉后将会继续。
#### tick-fluids
- **默认值**: true
- **描述**: 如果为 false，那么将会停止所有液体更新。[此处](images/freezefluids-chat-screenshot.png) 使用了此选项的一个简单的插件的截图。
#### trident-loyalty-void-return-height
- **默认值**: 0.0
- **描述**: 忠诚三叉戟能够返回投掷者处的最大虚空高度。设置为 0.0 或更高值将禁用此功能。
#### use-better-mending
- **默认值**: false
- **描述**: 如果为 true，那么经验修补将会优先修复损坏最严重的装备。

### ridable-settings

#### babies-are-ridable
- **默认值**: true
- **描述**: 如果为 false，那么将会禁止玩家骑乘婴儿生物。
#### untamed-tamables-are-ridable
- **默认值**: true
- **描述**: 如果为 false，那么将会禁止玩家骑乘未驯服的可驯化生物。
#### use-dismounts-underwater-tag
- **默认值**: true
- **描述**: 如果为 false，那么将会使用 `<mob>.ridable-in-water` 属性，而不是 [`DISMOUNTS_UNDERWATER`](https://minecraft.wiki/w/Tag#Entity_types) 标签。
#### use-night-vision
- **默认值**: false
- **描述**: 如果为 true，那么骑乘者将在骑乘生物时获得夜视效果。
