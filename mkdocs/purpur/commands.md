Purpur 为游戏添加了一些新的命令。

???+ note "注意"
    安装 Essentials 后，Essentials 将覆盖下面的一些命令。要使用 Purpur 的命令，请将以下内容添加到 Essentials 配置文件的 `disabled_commands` 部分。
    ``` yaml
    disabled-commands:
      - ping
      - uptime
      - compass
    ```

## /purpur
- 该命令重新加载 purpur.yml 配置文件并显示 Purpur 版本。

- **示例**：
    - `/purpur reload` 在不重启服务端的情况下重新加载 purpur.yml
    - `/purpur version` 显示当前版本（与 `/version` 作用相同）

- **权限节点**：
    - `bukkit.command.purpur`

## /ping
- 该命令显示玩家的 ping 值，前提是你有 `bukkit.command.ping.other` 权限。如果你没有指定玩家名称，或玩家实体选择器（`@a`、`@r`等），它将显示你自己的 ping 值。

- **示例**：
    - `/ping` 显示你自己的 ping 值
    - `/ping BillyGalbreath` 显示 BillyGalbreath 的 ping 值
    - `/ping @a` 显示所有玩家的 ping 值
    - `/ping @r` 显示一个随机玩家的 ping 值

- **权限节点**：
    - `bukkit.command.ping`
    - `bukkit.command.ping.other`

???+ note "注意"
    除非你有 `minecraft.command.selector` 权限，否则玩家实体选择器将无法使用。

## /uptime
- 该命令将显示服务器的正常运行时间。

- **权限节点**：
    - `bukkit.command.uptime`

## /demo
??? info "demo 版界面的图像 📷"
    ![demo 版界面](demo.png)
- 该命令将给玩家显示 demo 版界面，如果你有 `bukkit.command.demo.other` 权限。如果你没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向你显示 demo 版界面。

- **示例**：
    - `/demo` 显示 demo 版界面
    - `/demo BillyGalbreath` 向 BillyGalbreath 显示 demo 版界面
    - `/demo @a` 向所有玩家显示 demo 版界面
    - `/demo @r` 向一个随机玩家显示 demo 版界面

- **权限节点**：
    - `bukkit.command.demo`
    - `bukkit.command.demo.other`

???+ note "注意"
    除非你有 `minecraft.command.selector` 权限，否则玩家实体选择器将无法使用。

## /credits
??? info "鸣谢屏幕的图像 📷"
    ![鸣谢屏幕](credits.png)
- 该命令向玩家显示鸣谢屏幕，如果你有`bukkit.command.credits.other`权限。如果你没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向你显示鸣谢屏幕。

- **示例**：
    - `/credits` 显示鸣谢屏幕
    - `/credits BillyGalbreath` 向 BillyGalbreath 显示鸣谢屏幕
    - `/credits @a` 向所有玩家显示鸣谢屏幕
    - `/credits @r` 向一个随机玩家显示鸣谢屏幕

- **权限节点**：
    - `bukkit.command.credits`
    - `bukkit.command.credits.other`

???+ note "注意"
    除非你有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /tpsbar
??? info "tpsbar 的实际效果 📷"
    ![tpsbar 的实际效果](bossbar.gif)
- 该命令向玩家显示一个 bossbar，展示你当前的 TPS/MSPT，如果你有 `bukkit.command.tpsbar.other` 权限。如果你没有指定玩家名称或玩家实体选择器（`@a`、`@r`等），它将向你显示tpsbar。

- **示例**：
    - `/tpsbar` 显示 tpsbar
    - `/tpsbar BillyGalbreath` 向 BillyGalbreath 显示 tpsbar
    - `/tpsbar @a` 向所有玩家显示 tpsbar
    - `/tpsbar @r` 向一个随机玩家显示 tpsbar

- **权限节点**：
    - `bukkit.command.tpsbar`
    - `bukkit.command.tpsbar.other`

???+ note "注意"
    除非你有`minecraft.command.selector`权限，否则玩家实体选择器将无法使用。

## /compass
??? info "指南针的实际效果 📷"
    ![指南针的实际效果](bossbar.gif)
- 该命令显示一个 bossbar，展示你当前的朝向。

- **示例**：
    - `/compass` 显示指南针

- **权限节点**：
    - `bukkit.command.compass`
