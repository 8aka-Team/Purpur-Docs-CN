## 在哪里可以下载??!1?

我们在我们的网站上有一个下载页面，几乎和我的胡子一样雄伟 ![Billy's Majestic Beard](https://cdn.discordapp.com/emojis/768978823655063602.png?size=16)。这是我们友好的用户界面，用于访问我们的下载API：{{ project.downloads }}

如果你更喜欢直接使用下载API（用于自动化、脚本或其他用途），你可以在[主页]({{ project.downloads }})上找到列出的API端点。

## Purpur有哪些最佳选项?

总结Purpur很困难，因为这样就无法完全代表它的所有功能。

在Reddit上查看 [最受欢迎的功能](https://www.reddit.com/r/admincraft/comments/pbx5le/what_is_your_favorite_purpur_feature/) 投票。  
但这个列表并不全面，所以一定要查看所有可用选项，每个人都能找到适合自己的选项 \o/  
{{ site_url }}配置

## 我可以提出功能请求或报告错误吗?

当然可以！这正是让Purpur变得更好的原因 ^_^

如果你需要报告错误，请告诉我们。请记住，我们无法修复我们不知道出了什么问题 :wink:

错误报告：{{ project.source }}/issues/new

如果你有功能请求或建议，请记住我们尽量避免使用可能只对1或2个服务器有帮助的特定功能。这类功能最适合于插件或数据包。如果不确定，仍然可以提交一个工单，我们会告诉你 \o/

功能请求：{{ project.source }}/discussions/new

## Purpur有权限吗? :open_mouth:

有的。

Purpur为一些添加的功能和命令添加了一些权限。某些特定功能的权限除非你在purpur.yml中启用了该功能，否则将无法正常工作，所以请留意这一点 :wink:

{{ site_url }}权限

## *&lt;插入随机配置选项>* 是用来做什么的?

一些东西。

不是开玩笑，我们经常被问到这个问题。我们建立了这个维基来回答所有这些问题，这样我们就不必每天重复回答。

我保证，这个维基涵盖了purpur.yml中的每个选项 - 你不会找到任何遗漏的条目。（唯一的例外是当添加了新选项时，可能需要一两天才能更新维基）

{{ site_url }}配置

## Purpur有Discord吗?

有的！这是Purpur社区的所在地。不要害怕探头进去看看！{{ social[0].link }}

## Purpur与上游有什么添加/更改?

实际上有很多。但除非**你**在`purpur.yml`中启用它，否则这些更改都不会生效。我们将所有更改设置为默认行为。如果你不编辑`purpur.yml`中的任何内容，运行此JAR文件与运行Pufferfish没有任何区别。

对于好奇的人，你可以在GitHub上查看所有代码更改：{{ project.source }}/tree/master/patches

如果你无法阅读代码，不要担心。大多数人都不会。我们有这个很好的维基，涵盖了`purpur.yml`中的每个选项以及为一些新功能/命令添加的所有新权限节点。

## Purpur是否具有来自Paper的*X*功能?

是的，这就是分支的工作原理。所有上游功能都是继承的

`原版 -> CraftBukkit -> Spigot -> Paper -> Pufferfish -> Purpur`

我们都有 ^_^

## CraftBukkit/Spigot/Paper/Pufferfish的插件能在Purpur上运行吗?

可以。唯一不兼容的情况是因为作者将支持硬编码为CraftBukkit/Spigot，忽略了Paper及其分支的存在。如果你遇到任何因为Purpur而导致的错误，请[创建一个工单]({{ project.source }}/issues/new)和/或[加入我们的Discord服务器]({{ social[0].link }})以便我们查看。

## 是否有适用于MC _`插入随机版本`_的Purpur版本?
也许。请查看下载页面。

{{ project.downloads }}