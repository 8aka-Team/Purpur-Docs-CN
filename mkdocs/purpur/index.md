[![Purpur 图片](https://user-images.githubusercontent.com/74448585/150906023-101cd383-da82-4a3c-9603-a3b5741c3994.png)]({{ project.website }})

<div markdown="1" id="center">

[![MIT 许可证](https://img.shields.io/github/license/PurpurMC/Purpur?&logo=github)](许可证)&nbsp;
[![Github Actions 构建](https://img.shields.io/github/workflow/status/purpurmc/purpur/Build?event=push&logo=github)]({{ project.downloads }})
[![CodeFactor](https://www.codefactor.io/repository/github/purpurmc/purpur/badge)](https://www.codefactor.io/repository/github/purpurmc/purpur)&nbsp;
[![加入我们的 Discord](https://img.shields.io/discord/685683385313919172.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)]({{ social[0].link }})&nbsp;  

[![Purpur 的点赞者](https://img.shields.io/github/stars/PurpurMC/Purpur?label=stars&logo=github)]({{ project.source }}/stargazers)&nbsp;
[![Purpur 的分支](https://img.shields.io/github/forks/PurpurMC/Purpur?label=forks&logo=github)]({{ project.source }}/network/members)&nbsp;
[![Purpur 的关注者](https://img.shields.io/github/watchers/PurpurMC/Purpur?label=watchers&logo=github)]({{ project.source }}/watchers)&nbsp;

欢迎访问[Purpur]({{ project.source }}/)&nbsp;项目的官方文档源。

本文档适用于构建&nbsp;[#{{ project.build.number }}](https://api.purpurmc.org/v2/purpur/{{ project.version }}/{{ project.build.number }}/download)&nbsp;（[`{{ project.build.commit }}`]({{ project.source }}/commit/{{ project.build.commit }})）

Purpur 是 [Paper](https://github.com/PaperMC/Paper) 服务器的一个可配置的、设计新颖且充满乐趣的游戏功能的替代品。

</div>

## 联系 [![Discord shield.io](https://img.shields.io/discord/685683385313919172.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)]({{ social[0].link }})

加入我们的 [Discord]({{ social[0].link }})！

## 下载

你可以从[下载页面]({{ project.downloads }})或[下载 API](https://api.purpurmc.org/)下载 Purpur。

下载 API 端点：

 * 列出具有可用构建的 Minecraft 版本：  
 `https://api.purpurmc.org/v2/purpur/`
 * 列出某个 Minecraft 版本的构建：  
 `https://api.purpurmc.org/v2/purpur/<version>`
 * 下载特定版本的特定构建：  
 `https://api.purpurmc.org/v2/purpur/<version>/<build>/download`
 * 下载 Minecraft 版本的最新构建：  
 `https://api.purpurmc.org/v2/purpur/<version>/latest/download`

## 许可证 [![MIT 许可证](https://img.shields.io/github/license/PurpurMC/Purpur?&logo=github)](./#license)

该项目将所有补丁都授权为 MIT 许可证，除非补丁头部另有说明。

有关此项目使用的材料许可，请参阅[PaperMC/Paper](https://github.com/PaperMC/Paper)。

## bStats

<iframe src="https://purpurmc.org/stats" loading="lazy" title="hi" height="800" width="900"></iframe>


## API

### Javadoc
你可以在这里找到 Purpur 的 Javadoc：{{ project.javadoc }}

### 依赖信息
=== "Maven"

    ``` xml linenums="1"
    <repositories>
        <!-- 其他仓库... -->
        <repository>
            <id>purpur</id>
            <name>Purpur Maven 仓库</name>
            <url>https://repo.purpurmc.org/snapshots</url>
        </repository>
        <!-- 其他仓库... -->
    </repositories>
    ```
    ``` xml linenums="1"
    <dependencies>
        <!-- 其他依赖 -->
        <dependency>
            <groupId>org.purpurmc.purpur</groupId>
            <artifactId>purpur-api</artifactId>
            <version>{{ project.version }}-R0.1-SNAPSHOT</version>
            <scope>provided</scope>
        </dependency>
        <!-- 其他依赖 -->
    </dependencies>
    ```

=== "Gradle (Kotlin)"

    ``` kotlin linenums="1"
    repositories {
        //... 其他仓库 ...//
        
        //在 mavenCentral() 之后的某处添加以下内容
        maven("https://repo.purpurmc.org/snapshots")
        
        //... 其他仓库 ...//
    }
    ```
    ``` kotlin linenums="1"
    dependencies {
        //... 其他依赖 ...//
        
        compileOnly("org.purpurmc.purpur", "purpur-api", "{{ project.version }}-R0.1-SNAPSHOT")
        
        //... 其他依赖 ...//
    }
    ```

=== "Gradle (Groovy)"

    ``` groovy linenums="1"
    repositories {
        //... 其他仓库 ...//
        
        //在 mavenCentral() 之后的某处添加以下内容
        maven {
            url "https://repo.purpurmc.org/snapshots"
        }
        
        //... 其他仓库 ...//
    }
    ```
    ``` groovy linenums="1"
    dependencies {
        //... 其他依赖 ...//
        
        compileOnly "org.purpurmc.purpur:purpur-api:{{ project.version }}-R0.1-SNAPSHOT"
        
        //... 其他依赖 ...///
    }
    ```

将 Purpur 导入到你的项目中还会包括 Pufferfish、Paper、Spigot 和 Bukkit 提供的所有 API。

## 构建和设置

#### 初始设置
在项目目录的根目录中运行以下命令：

``` bash linenums="1"
./gradlew applyPatches
```

#### 创建一个补丁
补丁实际上只是 `Purpur-API` 或 `Purpur-Server` 中的提交。要创建一个补丁，只需向任一存储库添加一个提交，然后运行 `./gradlew rebuildPatches`，Gradle 将在补丁文件夹中放置一个补丁。修改提交也会修改其相应的补丁文件。

有关更详细的信息，请参阅[CONTRIBUTING.md]({{ project.source }}/blob/HEAD/CONTRIBUTING.md)。


#### 编译

使用命令 `./gradlew build` 来构建 API 和服务器。Gradle 将在 `Purpur-API/build/libs` 和 `Purpur-Server/build/libs` 下放置编译的 jar 文件。

要获取 purpurclip jar，运行 `./gradlew paperclip`。
要将 `purpur-api` 和 `purpur` 依赖项安装到你的本地 maven 仓库，请运行 `./gradlew publishToMavenLocal`
