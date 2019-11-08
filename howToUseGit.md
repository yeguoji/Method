How to use git

###### 实验楼中直接输入git 检测是否安装成功，wins系统待自己测试

**如何新建一个代码仓库**

仓库（ repository），可理解为储存代码的场所，点击个人主页的右上角的加号，再点击 `New repository` ，即可创建新的仓库。

Git 如何控制目录？

在目录中输入 git init 即可。

Git 提交代码的基本流程是这样的：

- 创建或修改 **本地文件**
- 使用 **git add** 命令，将创建或修改的文件添加到本地的 **暂存区**，这里保存的是你的临时更改
- 使用 **git commit** 命令，提交文件到 **本地仓库**
- 使用 **git push命令**，将本地代码库同步到 **远端仓库**

目前为止，我们实现了第一步，创建了一个文件，我们的**最终目标是**：将本地的 Demo 仓库，同步到 GitHub 上的 Demo 仓库中。

#### git add

使用 `git add + 文件名/目录名` 命令，可以将你需要同步的文件，添加到本地的暂存区。我们先进入 DEMO 目录，然后把 README.md 文件添加一下：

```
cd /home/shiyanlou/Demo
git add README.md
```

输入 `git status` ，可以检测当前目录和暂存区的状态，查看哪些修改被暂存了：

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558601543864)

可以看到我们刚刚 `add` 的文件已经被初始提交了。

#### 💡 git commit

`git commit` 提交是你工作的一个里程碑 —— **每当你完成一些工作，都可以创建一次提交，保存当前的版本。**

这样一来，无论你何时修改了文件，都创建一个新版本的文件，你可以很方便地查看以往所有版本的文件和内容。

**在提交之前，你必须先设置你的名字和 email**，这是你在提交 commit 时的签名，每次提交记录里都会包含这些信息。

使用 git config 命令进行配置：

```
$ git config --global user.name "YourName"
$ git config --global user.email "YourEmail@xxx.com"
```

完成配置后，我们可以创建提交了，请输入：

```
git commit -m "first commit"
```

`commit` 的语法结构是 `git commit -m "注释"`，通过上个命令，你创建了一条注释为 “first commit” 的 Git 提交。

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558603780044)

**⚠️ 注意：**每次提交，您都必须用 `-m + '注释'` 编辑注释信息 。它不仅能协助您辨别不同的版本，而且能让你理解，自己当时对文件做了什么修改。

比如当你每次在文件中添加了新的代码后，你可以写一句提交信息：“添加了 XXX 代码” —— 当你一个月后回来看提交记录或者 Git 日志 时，你还能知道当时做了什么。

#### git add

使用 `git add + 文件名/目录名` 命令，可以将你需要同步的文件，添加到本地的暂存区。我们先进入 DEMO 目录，然后把 README.md 文件添加一下：

```
cd /home/shiyanlou/Demo
git add README.md
```

输入 `git status` ，可以检测当前目录和暂存区的状态，查看哪些修改被暂存了：

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558601543864)

可以看到我们刚刚 `add` 的文件已经被初始提交了。

#### 💡 git commit

`git commit` 提交是你工作的一个里程碑 —— **每当你完成一些工作，都可以创建一次提交，保存当前的版本。**

这样一来，无论你何时修改了文件，都创建一个新版本的文件，你可以很方便地查看以往所有版本的文件和内容。

**在提交之前，你必须先设置你的名字和 email**，这是你在提交 commit 时的签名，每次提交记录里都会包含这些信息。

使用 git config 命令进行配置：

```
$ git config --global user.name "YourName"
$ git config --global user.email "YourEmail@xxx.com"
```

完成配置后，我们可以创建提交了，请输入：

```
git commit -m "first commit"
```

`commit` 的语法结构是 `git commit -m "注释"`，通过上个命令，你创建了一条注释为 “first commit” 的 Git 提交。

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558603780044)

**⚠️ 注意：**每次提交，您都必须用 `-m + '注释'` 编辑注释信息 。它不仅能协助您辨别不同的版本，而且能让你理解，自己当时对文件做了什么修改。

比如当你每次在文件中添加了新的代码后，你可以写一句提交信息：“添加了 XXX 代码” —— 当你一个月后回来看提交记录或者 Git 日志 时，你还能知道当时做了什么。

本节实验最后一个知识点是 `git clone` 命令，它可以帮你拷贝一个 Git 仓库到本地，让自己能够查看该项目，或者进行修改。

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558610914428)

如果你想要复制一个项目，看看代码，或者把自己的远程仓库复制到本地，可以执行命令：

```
git clone [url]
```

[url] 指的就是你想复制的仓库，我们在 `github.com` 上提供了一个名字为 `gitproject` 的公开仓库， 供大家测试，现在你要把这个仓库复制到实验环境中，只需输入：

```
$ cd /home/shiyanlou/
$ git clone https://github.com/shiyanlou/gitproject
```

操作完成后，会发现 /home/shiyanlou 目录下多了一个 gitproject 文件夹，这个文件夹里的内容就是我们刚刚 clone 下来的代码。

![图片描述](https://doc.shiyanlou.com/courses/uid8504-20190523-1558611764793)

