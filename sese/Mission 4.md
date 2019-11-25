# Mission 4

### git菜鸟笔记

##### 1 初识git

创建github帐号不用细说，创建储存库是一切的开始

linux下安装git核心需要如下命令

```
git config --global user.name "XXXX"   配置用户名，用户名为上面自己创建的github的账号
git config --global user.email  "XXXXXXXXXX"    配置邮箱，确保邮箱存在且正确
git config --list     是否配置成功
配置Git的私钥和公钥.密码为空:
ssh-keygen -t rsa  -C "用户邮箱"      注：出来需要输入的东西，直接回车
cd ~/.ssh/                                    ：查看是否生成成功
vim id_rsa.pub      复制文件中全部的文字，到GitHub中的key中
ssh git@github.com 验证Git是否配置成功
```

##### 2 了解git生平往事

git里的命令容易理解，语法较为简单，需要在init的目录里进行操作，一个终端可以建立多个init。

操作命令如下：

```
 1.  git init -- 初始化本地版本库

 2.  git add . -- 跟踪所有改动过的文件

 3.  git add <file>  -- 跟踪指定的文件

 4.  git commit -m “commit message” -- 提交所有更新过的文件

 5.  git push origin <本地分支名>:<远程分支名>  推送本地提交数据到远程仓库指定分支 如果是		相同的，可以省略
 
 6.  git checkout -b 分支名    创建切换分支
 	 git branch [分支名] 创建分支：

 7.  git branch   查看当前所在分支

 8.  git checkout 分知名   切换分支

 9.  git merge <branch>   合并指定分支到当前分支

 10. git fetch -a 从远程获取最新版本到本地
 11. git clone + [仓库地址]  标准的克隆仓库命令。进入仓库主目录，如下图所示，仓库主目录中		有个 .git 隐藏目录，它里面包含了仓库的全部信息，删掉这个目录，仓库就变成普通的目录了。进	   入到仓库目录中，命令行前缀发生了一些变化，出现了红色的 master ，它就是当前所在的分支名
 12. 删除分支： $ git branch -d mybranch
 13. 强制删除分支： $ git branch -D mybranch
     查看各个分支最后一次提交： $ git branch -v 
     查看哪些分支合并入当前分支： $ git branch –merged		
     查看哪些分支未合并入当前分支： $ git branch –no-merged
     更新远程库到本地： $ git fetch origin
     取远程分支合并到本地： $ git merge origin/mybranch
     删除远程分支：$ git push origin :mybranch
```

##### 3 git的性格特点

```
git add *.html 可以帮你把项目文件夹下的所有.html文件都放进暂存区

git reset filename.extension 从暂存区中删除指定文件。

$git rebase master 更新master主线上的东西到该分支上

git rm —cached filename.extension 从暂存区中删除该文件，并将其设置为未跟踪。

touch .gitignore  创建一个名叫.gitignore的文件，你可以用文本编辑器打开这个文件，写下存储库里需要忽略的文件名或者文件夹名，运行的时候这些被忽略的文件不会显示。

git branch branchName  创建一个分支（branch），就是你前一个分支代码库的直接副本。

git checkout “branchName”  检查你创建的分支，并在这个分支内工作。你可以再次对你的代码进行任何更改，弄完之后再提交代码然后把这个分支push到GitHub上。如果除了问题或者你不再需要这个功能了，那就可以直接删掉分支。

当我们在 GitHub 上创建一个仓库时，同时生成了仓库的默认主机名 origin，并创建了默认分支 master。GitHub 可以看成是免费的 Git 服务器，在 GitHub 上创建仓库，会自动生成一个仓库地址，主机就是指代这个仓库，主机名就等于这个仓库地址。克隆一个 GitHub 仓库（也叫远程仓库）到本地，本地仓库则会自动关联到这个远程仓库，执行 git remote -v 命令可以查看本地仓库所关联的远程仓库信息：Git 要求对本地仓库关联的每个远程主机都必须指定一个主机名（默认为 origin），用于本地仓库识别自己关联的主机，git remote 命令就用于管理本地仓库所关联的主机，一个本地仓库可以关联任意多个主机（即远程仓库）。

删除远程分支，使用 git push [主机名] :[远程分支名] ，如果一次性删除多个，可以这样：git push [主机名] :[远程分支名] :[远程分支名] :[远程分支名] 。此命令的原理是将空分支推送到远程分支，结果自然就是远程分支被删除。另一个删除远程分支的命令：git push [主机名] --delete [远程分支名]。删除远程分支的命令可以在任意本地分支中执行。两个命令分别试一下：


```

##### 参考资料

[小白笔记](https://www.runoob.com/git/git-tutorial.html)

[新手指南](https://www.zhihu.com/question/21669554/answer/836370309)

[同性交友](https://segmentfault.com/a/1190000009985489)

[从入门到入坑](https://www.jianshu.com/p/cfe49324de09)

