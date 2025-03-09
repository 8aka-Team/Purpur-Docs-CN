# Log4j 安全漏洞
几位研究人员发现了一个远程代码执行（RCE）漏洞，存在于 Minecraft 和许多其他基于 Java 的应用程序中使用的日志记录库中。这个漏洞允许任何人以极小的操作在你的服务器上执行命令并运行代码，并获取你的后端服务器的公共 IP 地址。

这个漏洞存在于所有 1.7.10 或更高版本的原版 Minecraft 版本中，并影响使用该库的每个应用程序。特别是原版客户端、所有基于原版的服务器，如 Paper 和 Purpur、Velocity 和 Waterfall。如果你运行任何其他基于 Java 的应用程序，如 Jenkins 或 UniFi ，请确保它们也是最新的。

Mojang 已为所有 1.8 及更新版本的客户端推送了修复程序。1.7.10 及更早版本不受影响。Purpur 已为 1.18.1 推送了一个包含修复程序的 JAR，并发布了 1.18 及更早版本的 XML 文件。那些使用旧版本库的插件也需要更新。

## 更新 Purpur
由于我们的工具工作方式的原因，我们无法为早于最新 Minecraft 版本的版本推送修复的 JAR。现在是摆脱不受支持版本，升级到最新版本的游戏的好时机。

### 1.18.1及更新版本
1.18.1 版本 [`#1464`](https://api.purpurmc.org/v2/purpur/1.18.1/1464/download) 及更新版本已修复。[在这里下载最新版本](项目下载)。

### 1.18至1.17
如上所述，Purpur 不提供修复的 JAR。不过，我们提供一个禁用漏洞的 XML 文件。要安装，请<a download href="../../xml/purpur_log4j2_117.xml">下载此XML文件</a>，将其放在服务器的根目录（JAR文件所在的位置），并在启动参数中的 `java` 后面添加 `-Dlog4j.configurationFile=purpur_log4j2_117.xml`。

???+ warning "警告"
这种方法在 1.18 版本上尚未经过完全测试。如果发现任何问题，请在文档的 [问题跟踪器](https://github.com/PurpurMC/PurpurDocs/issues)上报告。

### 1.16.5 及更早版本
过程与上述相同，但使用不同的 XML 文件。将<a download href="../../xml/purpur_log4j2_1141-1165.xml">此 XML 文件下载</a>到服务器的根目录，并在启动参数中的 `java` 后面添加 `-Dlog4j.configurationFile=purpur_log4j2_1141-1165.xml`。

请注意其他声称通过将日志重定向到系统输出流来修复漏洞的插件，因为 Paper 会自动将这些调用重定向回 Log4j。过滤掉有问题的字符串将不会修复漏洞，因为所有过滤器都可以以各种方式被绕过。

## 工作原理
要测试此漏洞是否影响你，请在服务器的聊天中发送 `${jndi:ldap://127.0.0.1:1389/a}`，并检查服务器的日志。如果控制台有*任何*响应，则你的服务器有漏洞。

标志 `-Dlog4j2.formatMsgNoLookups=true` 无法阻止早于 1.17 版本的漏洞发挥作用。它仅适用于 1.16.5 及更新版本，这些版本已经提供了更好的缓解措施。

关于漏洞工作原理的基本解释可以在 [这里](https://gist.github.com/TheCurle/f15a6b63ceee3be58bff5e7a97c3a4e6#the-problem) 找到。根据 [Paper团队](https://discord.com/channels/289587909051416579/289587909051416579/918964269415030855)[^1] 的当前知识，所有Java版本都可能允许远程代码执行。

有关更多信息，请阅读 [Mojang关于漏洞的博文](https://www.minecraft.net/en-us/article/important-message--security-vulnerability-java-edition)。其中包含其他平台的修复措施，如第三方客户端。Paper 的 [信息帖子](https://discord.com/channels/289587909051416579/289587909051416579/918964269415030855)[^1] 和 [公告](https://discord.com/channels/289587909051416579/492517675680006144/918581596825718815)[^2] 也可能有所帮助。

[^1]: ![Paper的Log4j信息帖子](images/paper-log4j-pin.png)
[^2]: ![Paper的Log4j信息公告](images/paper-log4j-announcement.png)