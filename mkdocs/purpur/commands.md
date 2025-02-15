Purpur为游戏添加了一些新的命令。

???+ note "注意"
    当您安装Essentials时，Essentials将覆盖下面的一些命令。要使用Purpur的命令，请将以下内容添加到Essentials配置文件的`disabled_commands`部分。
    ``` yaml
    disabled-commands:
      - ping
      - uptime
      - compass
    ```

## /purpur
- 该命令重新加载purpur.yml配置文件并显示Purpur版本。

- **示例**：
    - `/purpur reload` 在不重启的情况下重新加载purpur.yml
    - `/purpur version` 显示当前版本（与`/version`相同）

- **权限**：
    - `bukkit.command.purpur`

## /ping
- 该命令显示玩家的ping值，如果您有`bukkit.command.ping.other`权限。如果您没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将显示您自己的ping值。

- **示例**：
    - `/ping` 显示您自己的ping值
    - `/ping BillyGalbreath` 显示BillyGalbreath的ping值
    - `/ping @a` 显示所有玩家的ping值
    - `/ping @r` 显示一个随机玩家的ping值

- **权限**：
    - `bukkit.command.ping`
    - `bukkit.command.ping.other`

???+ note "注意"
    除非您有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /uptime
- 该命令显示服务器的正常运行时间。

- **权限**：
    - `bukkit.command.uptime`

## /demo
??? info "演示屏幕的图像 📷"
    ![演示屏幕](demo.png)
- 该命令显示演示屏幕给玩家，如果您有`bukkit.command.demo.other`权限。如果您没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向您显示演示屏幕。

- **示例**：
    - `/demo` 显示演示屏幕
    - `/demo BillyGalbreath` 向BillyGalbreath显示演示屏幕
    - `/demo @a` 向所有玩家显示演示屏幕
    - `/demo @r` 向一个随机玩家显示演示屏幕

- **权限**：
    - `bukkit.command.demo`
    - `bukkit.command.demo.other`

???+ note "注意"
    除非您有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /credits
??? info "鸣谢屏幕的图像 📷"
    ![鸣谢屏幕](credits.png)
- 该命令向玩家显示鸣谢屏幕，如果您有`bukkit.command.credits.other`权限。如果您没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向您显示鸣谢屏幕。

- **示例**：
    - `/credits` 显示鸣谢屏幕
    - `/credits BillyGalbreath` 向BillyGalbreath显示鸣谢屏幕
    - `/credits @a` 向所有玩家显示鸣谢屏幕
    - `/credits @r` 向一个随机玩家显示鸣谢屏幕

- **权限**：
    - `bukkit.command.credits`
    - `bukkit.command.credits.other`

???+ note "注意"
    除非您有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /tpsbar
??? info "tpsbar的实际效果 📷"
    ![tpsbar的实际效果](bossbar.gif)
- 该命令向玩家显示一个bossbar，展示您当前的TPS/MSPT，如果您有`bukkit.command.tpsbar.other`权限。如果您没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向您显示tpsbar。

- **示例**：
    - `/tpsbar` 显示tpsbar
    - `/tpsbar BillyGalbreath` 向BillyGalbreath显示tpsbar
    - `/tpsbar @a` 向所有玩家显示tpsbar
    - `/tpsbar @r` 向一个随机玩家显示tpsbar

- **权限**：
    - `bukkit.command.tpsbar`
    - `bukkit.command.tpsbar.other`

???+ note "注意"
    除非您有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /compass
??? info "指南针的实际效果 📷"
    ![指南针的实际效果](bossbar.gif)
- 该命令显示一个bossbar，展示您当前的朝向。

- **示例**：
    - `/compass` 显示您的指南针

- **权限**：
    - `bukkit.command.compass`
