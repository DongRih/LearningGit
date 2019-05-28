# Learning Git

## 3. Basic Operations

### 3.1 新建仓库/克隆仓库

#### 新建仓库

1. 在当前目录初始化仓库

        $ git init

2. 在 .gitignore 写入要忽略的文件/目录名，要符合[glob语法](/3_z_glob.md/).

>所谓的 glob 模式是指 shell 所使用的简化了的正则表达式。 星号（\*）匹配零个或多个任意字符；[abc] 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）；问号（?）只匹配一个任意字符；如果在方括号中使用短划线分隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到 9 的数字）。 使用两个星号（*) 表示匹配任意中间目录，比如 a/**/z 可以匹配 a/z , a/b/z 或 a/b/c/z 等。

        Listings
        Objects
        *.uvgui.*

3. 添加文件

    ```` bash
    $ git add *.c
    $ git add LICENSE
    $ git add *
    ````

4. 第一个commit

    ```` bash
    $ git commit -m 'initial project version'
    ````

#### 克隆现有的仓库

```` bash
$ git clone https://address/of/repo name

$ git clone user@server:path/to/repo.git
````

在当前目录下按指定的项目名称创建目录 (参数留空时不改变原名称），并在这个目录下初始化一个 .git 文件夹，从远程仓库拉取下所有数据放入 .git 文件夹，然后从中读取最新版本的文件的拷贝。

### 3.2 记录更新

![States](/res/states.png)

#### 检查当前状态

使用 `git status` 检查当前状态。

```` bash
$ git status
  On branch master
  nothing to commit, working directory clean
````

现在，master分支的工作目录干净：所有已跟踪文件在上次提交后都未被更改，没有任何处于未跟踪状态的新文件。**我们在工作目录下新创建README这一文件：**

```` bash
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    README

nothing added to commit but untracked files present (use "git add" to track)
````

新建的 README 文件出现在 Untracked files 下面。 未跟踪的文件意味着 Git 在之前的快照（提交）中没有这些文件；Git 不会自动将之纳入跟踪范围，除非你明明白白地告诉它“我需要跟踪该文件”， 这样，不必担心将生成的二进制文件或其它不想被跟踪的文件包含进来。