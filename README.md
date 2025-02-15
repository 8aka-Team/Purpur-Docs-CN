# PurpurDocs

这是用[Mkdocs](https://github.com/mkdocs/mkdocs)生成的静态站点文档，托管在[Purpur](https://purpurmc.org/)的https://purpurmc.org/docs上。其中包含一个Python脚本，用于比较两个提交哈希的差异，并将配置/权限的添加/移除输出到一个YAML文件中。

## 构建

[创建并激活一个Python 3虚拟环境](https://docs.python.org/3/tutorial/venv.html)
```sh
$ pip install --user virtualenv
$ virtualenv env
$ source env/bin/activate
```

安装所需的包
```sh
pip install -r requirements.txt
```

#### 预览更改

要预览文档的更改，运行 `mkdocs serve`。这将启动一个Web服务器，用于预览文档并在您进行更改时重新编译它。更多信息请参见：https://www.mkdocs.org/#getting-started
```sh
$ mkdocs serve
```

### 比较配置/权限添加/移除的提交

运行 `compare-commits.sh` 脚本，运行一个交互式脚本，比较Purpur提交之间的差异，并生成一个配置选项/权限添加/移除的文件。

<details>
<summary><code>./compare-commits.sh &lt;prev_hash> &lt;curr_hash> </code></summary>
您还可以将两个提交哈希作为命令行参数添加，这样将跳过脚本的交互部分。

```sh
$ ./compare-commits.sh 885092 22b876
```

```yml
# logs/885092..22b876.yml

config:
  additions:
  - gameplay-mechanics.item.immune.cactus: new ArrayList<>()
  - gameplay-mechanics.player.fix-stuck-in-portal: 'false'
  removals:
  - projectile-load-save-per-chunk-limit: '-1'
permission:
  additions: []
  removals: []
```
</details>

<details>
<summary><code>./compare-commits.sh &lt;prev_hash> </code></summary>
只包括一个哈希将与指定分支的最新提交进行比较（在撰写本文时为`ver/1.16.5`）。

```sh
$ ./compare-commits.sh 885092
```

```yml
# logs/885092..ver|1.16.5.yml

config:
  additions:
  - gameplay-mechanics.item.immune.cactus: new ArrayList<>()
  - gameplay-mechanics.player.fix-stuck-in-portal: 'false'
  removals:
  - projectile-load-save-per-chunk-limit: '-1'
permission:
  additions: []
  removals: []
```
</details>

<details>
<summary><code>./compare-commits.sh --no-commits </code></summary>
使用选项 `--no-commits` 或 `-nc` 运行脚本将创建一个`last_commit`文件，其中包含运行时最近的提交。再次运行将使用`last_commit`中的哈希作为第一个提交哈希，在生成文件后用最新的提交替换它。

```sh
# 第一次运行
$ ./compare-commits.sh -nc
```

```yml
# logs/885092..ver|1.16.5.yml

config:
  additions:
  - gameplay-mechanics.item.immune.cactus: new ArrayList<>()
  - gameplay-mechanics.player.fix-stuck-in-portal: 'false'
  removals:
  - projectile-load-save-per-chunk-limit: '-1'
permission:
  additions: []
  removals: []
```

```yml
# 创建一个last_commit文件
885092
```



```sh
# 在Purpur推送新提交后再次运行
$ ./compare-commits.sh -nc
```

```yml
# logs/885092..22b876.yml

config:
  additions:
  - gameplay-mechanics.item.immune.cactus: new ArrayList<>()
  - gameplay-mechanics.player.fix-stuck-in-portal: 'false'
  removals:
  - projectile-load-save-per-chunk-limit: '-1'
permission:
  additions: []
  removals: []
```

```yml
# 修改last_commit文件
22b876
```
</details>