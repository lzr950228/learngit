# 笔记
## 登录Git
1.git config --global user.email "you@example.com"
2.git config --global user.name "Your Name"

## 创建版本库：
1.在所选目录下创建文件夹
2.空白处右键选择Git Bush Here 将Git文件目录设置成当前目录
3.输入git init命令创建版本库（创建唯一master分支）

## 文件的上传
1.编译文件并保存在learngit文件夹下（工作区）
2.将文件添加到仓库（add-暂存区）(git add readme.txt)
3.提交到仓库（更新分支）(git commit -m "wrote a readme file")
    注：-m后“”内的内容可以自己编译，最好是有意义的
4.命令git commit执行成功后：
1 file changed1 一个文件被改动
2 insertionsv 插入了两行内容
5.git commit只上传暂存区内的文件，不上传工作区的文件
6.为什么Git添加文件需要add，commit一共两步呢？因为commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：
$ git add file1.txt
$ git add file2.txt file3.txt
$ git commit -m "add 3 files."

## 文件的修改：
1.对工作区的文件进行修改
2.运行git status命令可掌握仓库当前的状态
例如：
    1）哪些文件被修改过
    2）如果多个文件被修改只有其中的几个重新上传成功则会显示未上传成功的内容
    3）被修改项目若成功add暂存库 modified:   xxx.xx
    会显示绿色，反之为红色
    4）若修改的项目全部上传成功则显示nothing to commit, working tree clean
3.运行git diff命令可查看上次的修改内容是什么(将工作区与仓库里的文件进行对比)

## 时光机：
1.运行git log命令可查看历史提交版本（可以使用git log --prrtty=oneline查看版本的简化版，开头一串为版本号）
2.执行cat XXX.XX命令可查看XXX文件的当前版本
3.执行git reset --hard HEAD^命令回退到上一个版本（在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100）
4.执行 git reset --hard 版本号,可回到所选版本
5.执行git reflog可查看历史操作（便于查找历史）
6.撤销修改：
1)将工作区的文件进行修改（git checkout -- xxx.xx）
    一种是xxx.xx自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
    一种是xxx.xx已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
2)将暂存区的文件进行回退至工作区(git reset HEAD xxx.xx)
7.删除文件：
1)rm xxx.xx从工作区里删除
2)git checkout -- xxx.xx将工作区误删的文件从版本库中恢复
3)从版本库中删除：
(1)git rm xxx.xx
(2)git commit -m "xxx.xx"

## 本地上传至远程库
1.关联：git remote add origin git@github.com:用户名/本地库文件夹名称.git
2.本地推送至远程库：
    1)第一次推git push -u origin master
    2)git push origin master

