# Learning Git

## 2.Initial configs

### 配置文件位置

 `git config` 设置控制 Git 外观和行为的配置变量。 这些变量存储在三个不同的位置：

>`/etc/gitconfig` 文件: 包含系统上每一个用户及他们仓库的通用配置。 如果使用带有 --system 选项的 git config 时，它会从此文件读写配置变量。  

>`~/.gitconfig` 或 `~/.config/git/config` 文件：只针对当前用户。 可以传递 `--global` 选项让 Git 读写此文件。

>当前使用仓库的 Git 目录中的 config 文件（就是 `.git/config`）：针对该仓库。

每一个级别覆盖上一级别的配置，所以 `.git/config` 的配置变量会覆盖 `/etc/gitconfig` 中的配置变量。

在 Windows 系统中，Git 会查找 `$HOME` 目录下（一般情况下是 `C:\Users\$USER`）的 `.gitconfig` 文件。 Git 同样也会寻找 `/etc/gitconfig` 文件，但只限于 MSys 的根目录下，即安装 Git 时所选的目标位置。

### 用户信息

设置用户名称与邮件地址。 这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到你的每一次提交中，不可更改：

```` bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
````

在项目目录下运行没有 --global 选项的命令，对项目单独配置。


### 文本编辑器

```` bash
$ git config --global core.editor vim
````

### 检查配置信息

`git config --list` 命令列出所有 Git 当时能找到的配置。

```` bash
$ git config --list

user.name=John Doe
user.email=johndoe@example.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
````

可能会看到重复的变量名，因为 Git 会从不同的文件中读取同一个配置（例如：/etc/gitconfig 与 ~/.gitconfig）。 这种情况下，Git 会使用它找到的每一个变量的最后一个配置。

可以通过输入 `git config <key>`来检查 Git 的某一项配置

``` bash
$ git config user.name
John Doe
```