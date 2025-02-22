Purpur为其新增功能添加了一些新的权限节点。

默认情况下，Purpur会禁用**所有**这些权限，无论用户是否具有OP权限。服务器需要一个像[LuckPerms](https://luckperms.net/)这样的权限插件来向用户授予权限。

## allow.ride.<mob_id&gt;
需要在purpur.yml中启用[`<mob_id>.ridable`](configuration#mobs)

- 此权限允许通过按住Shift右键来骑乘特定生物。一旦骑乘，你可以使用WASD键移动，空格键跳跃或飞行。只需用生物的实体ID替换"<mob_id&gt;"。

- **示例**：
    - `allow.ride.cow`
    - `allow.ride.zombie_pigman`
    - `allow.ride.snow_golem`

## allow.special.<mob_id&gt;
需要在purpur.yml中启用[`<mob_id>.ridable`](configuration#mobs)

- 此权限允许激活可骑乘生物的特殊能力。并非所有生物都有特殊能力。只需用生物的实体ID替换"<mob_id&gt;"。

- **当前可用的特殊能力**
    - `allow.special.creeper`
        - 按下空格键时点燃
    - `allow.special.dolphin`
        - 按下空格键时吐水
    - `allow.special.phantom`
        - 按下空格键时发射火焰
    - `allow.special.wither`
        - 鼠标点击时发射凋零头

## allow.powered.creeper
需要在purpur.yml中启用[`creeper.ridable`](configuration#creeper)

- 此权限允许在骑乘时切换爆炸状态的充能爬行者。在不移动时按住空格键进行充能切换。充能状态将在爆炸时切换开或关。

## bukkit.command.uptime
- 允许使用 [`/uptime`](commands#uptime) 命令。

## bukkit.command.demo
- 允许使用 [`/demo`](commands#demo) 命令。

## bukkit.command.demo.other
- 允许在其他玩家身上使用 [`/demo`](commands#demo) 命令。

## bukkit.command.credits
- 允许使用 [`/credits`](commands#credits) 命令。

## bukkit.command.credits.other
- 允许在其他玩家身上使用 [`/credits`](commands#credits) 命令。

## bukkit.command.ping
- 允许使用 [`/ping`](commands#ping) 命令。

## bukkit.command.ping.other
- 允许在其他玩家身上使用 [`/ping`](commands#ping) 命令。

## bukkit.command.tpsbar
- 允许使用 [`/tpsbar`](commands#tpsbar) 命令。

## bukkit.command.tpsbar.other
- 允许在其他玩家身上使用 [`/tpsbar`](commands#tpsbar) 命令。

## bukkit.command.ram
- 允许使用 [`/ram`](commands#ram) 命令。

## bukkit.command.rambar
- 允许使用 [`/rambar`](commands#rambar) 命令。

## bukkit.command.rambar.other
- 允许在其他玩家身上使用 [`/rambar`](commands#rambar) 命令。

## bukkit.command.compass
- 允许使用 [`/compass`](commands#compass) 命令。

## minecraft.command.gamemode.<gamemode&gt;
需要在 purpur.yml 中启用 [`gamemode.requires-specific-permission`](configuration#command)

- 允许用户将自己的游戏模式设置为 <gamemode&gt;
- 可用的游戏模式
    - 冒险模式, 创造模式, 旁观者模式, 生存模式

## minecraft.command.gamemode.<gamemode&gt;.other;
需要在 purpur.yml 中启用 [`gamemode.requires-specific-permission`](configuration#command)

- 允许用户将自己和其他玩家的游戏模式设置为 <gamemode&gt;
- 可用的游戏模式
    - 冒险模式, 创造模式, 旁观者模式, 生存模式

## purpur.debug.f3n
- 允许使用 F3+N 调试热键来交换游戏模式。
  玩家必须具有此权限和相应的游戏模式权限才能使用。

## purpur.drop.spawners
需要在 purpur.yml 中启用 [`gameplay-mechanics.silk-touch`](configuration#silk-touch_1)

- 拥有此权限的玩家可以使用带有丝绸之触附魔的配置工具来挖掘任何刷怪笼，而不是让它消失。

## purpur.joinfullserver
- 允许玩家在服务器已满时加入

## purpur.bypassIdleKick
- 允许玩家在空闲时避免被踢出

## purpur.portal.instant
- 允许玩家在穿过传送门时立即传送

## purpur.place.spawners
需要在 purpur.yml 中启用 [`gameplay-mechanics.silk-touch`](configuration#silk-touch_1)

- 拥有此权限的玩家可以放置刷怪笼并将生物类型恢复为使用丝绸之触挖掘时的类型。

## purpur.sign.color
需要在 purpur.yml 中启用 [`sign.allow-colors`](configuration#sign)

- 允许玩家在牌子上使用颜色代码

## purpur.sign.style
需要在 purpur.yml 中启用 [`sign.allow-colors`](configuration#sign)

- 允许玩家在牌子上使用样式代码（除了魔法/模糊代码）

## purpur.sign.magic
需要在 purpur.yml 中启用 [`sign.allow-colors`](configuration#sign)

- 允许玩家在牌子上使用魔法/模糊样式代码

## purpur.book.color.edit
- 允许玩家在书籍中使用传统的（`&a`）颜色代码，在书籍关闭后更新

## purpur.book.color.sign
只有在书籍签名后才会注册十六进制颜色代码

- 允许玩家在书籍中使用传统的（`&a`）和十六进制（`&#AAAAAA`）颜色代码，在书籍签名后更新

## purpur.anvil.color
需要在 purpur.yml 中启用 [`anvil.allow-colors`](configuration#allow-colors_1)

- 允许玩家在铁砧中使用传统颜色代码。[`关于颜色代码的更多信息，请查看 Minecraft 网站。`](https://minecraft.wiki/w/Formatting_codes)

## purpur.anvil.minimessage
需要在 purpur.yml 中启用 [`anvil.allow-minimessage`](configuration#use-mini-message)

- 允许玩家在铁砧中使用 MiniMessage 标签。[`你可以在这里测试你的 MiniMessage 标签。`](https://webui.advntr.dev/)

## purpur.anvil.remove_italics
需要在 purpur.yml 中启用 [`anvil.allow-colors`](configuration#anvil)

- 允许玩家通过以 '&r' 开头的文本来移除铁砧中重命名物品的斜体

## purpur.anvil.format
需要在 purpur.yml 中启用 [`anvil.allow-colors`](configuration#anvil)

- 允许玩家在铁砧中使用传统格式代码（&l, &m, &n, &o）

## purpur.enderchest.rows.<number&gt;
需要在 purpur.yml 中启用 [`ender_chest.six-rows`](configuration#ender_chest) 和 [`ender_chest.use-permissions-for-rows`](configuration#ender_chest)

- 控制玩家末影箱的行数
- 可用大小
    - one, two, three, four, five, six

## purpur.inventory_totem
需要在 purpur.yml 中启用 [`totem-of-undying-works-in-inventory`](configuration#totem-of-undying-works-in-inventory)

- 允许玩家的不死图腾在他们的背包中起作用

## purpur.mending_shift_click
需要将 [`shift-right-click-repairs-mending-points`](configuration#shift-right-click-repairs-mending-points) 设置为大于0的数值

- 允许玩家按住 Shift 右键来使用他们存储的经验来修复装备

## purpur.tnt.defuse
需要将 [`defuse-tnt-chance`](configuration#defuse-tnt-chance) 设置为大于0的概率

- 允许玩家右键使用剪刀来拆除引爆的TNT