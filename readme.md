# Git与GitHub Study

> 学习地址：https://www.bilibili.com/video/BV1pW411A7a5?from=search&seid=14171986869332635785&spm_id_from=333.337.0.0

## 1.1本地库初始化

命令： git add

使用git init 进行本地初始化

- .git 存放的是本地库相关的子目录和文件，不要删，也不能胡乱修改

## 1.2设置签名

区分不同开发人员身份

- 形式
  - 用户名
  - Email 地址 

- 命令

  - 项目/仓库级别：仅在当前项目有效

    “存在 .git/config 中”

    git config user.name ***

    git config user.email ***

  - 系统用户级别：登陆当前系统的用户范围

    "存在 ～/.gitconfig 中"

    git config --global user.name ***

    git config --global user.email ***

    ​		项目级别优先级更高，二者都没有不允许

## 1.3基本操作

1. 状态查看

   git status

2. 添加操作

   git add [filename]

3. 提交操作

   git commit -m "message" [filename]

4. 查看历史记录

   git log

   git log --pretty=oneline

   git log --oneline

   git reflog  # 适用于版本回退

5. 版本前进后退

   基于索引值操作【Good】

   ​       git reset --hard [索引值]

   使用^符号    *只能后退*

   ​		git reset --hard HEAD^^  # 后退两次

   使用～符号  *只能后退*

   ​		git reset --hard HEAD~3 # 后退三次

   - reset 的三种参数
     - --soft          	仅在本地库移动
     - --mixed          本地库移动、重置暂存区
     - --hard             本地库移动，重置暂存区、缓存区

6. 删除文件后找回

   回退到指定之前版本即可

7. 添加到暂存区的文件找回

   $使用git reset --hard HEAD 进行恢复

8. 比较文件差异

   - git diff [文件名]
   - git diff [历史版本] [文件名]

## 1.4版本分支

- 创建新分支

  - 内容和主干一致，各自向前开发，彼此独立，也能请求合并到主分支
  - git branch [分支名]

- 查看分支

  - git branch -v

- 切换分支

  - git checkout [分支名]

- 合并分支

  - 切换到接受修改的分支上 git checkout [***]
  - 执行merge命令 git merge [**]

- 分支冲突

  ![image-20211022233330557](/home/yueyuebird/.config/Typora/typora-user-images/image-20211022233330557.png)

  - 编辑文件，删除特殊符号
  - 修改文件
  - git add
  - git commit

## 2GitHub Study

### 2.1 基础

- 连接

  - git remote -v 查看当前所有远程地址别名
  - git remote add [别名] [地址]

- 推送

  - git push [别名] [分支]

- 克隆

  - git clone [远程地址]

-  协作

  ![image-20211025220743438](/home/yueyuebird/.config/Typora/typora-user-images/image-20211025220743438.png)

- 抓取远程内容

  - pull = fetch + merge
  - git fetch [远程地址别名] [远程分支名]
  - git merge [远程地址别名 / 远程分支名]
  - 也可以直接 git pull [远程地址别名] [远程分支名]

- 冲突

  1. 如果不是基于最新版的修改，则不能推送
  2. 拉取下来后如果进入冲突状态，则修改合并文件使满足自己的需求

### 2.2跨团队操作

1. fork
2. 本地修改、推送到远程
3. Pull Request  在github网站中
4. 审核代码
5. 合并代码

### 2.3SSH登陆

1. 生成.ssh 密钥目录

   ssh-keygen -t rsa -C [eamil/usrname]

2. 拷贝id_rsa.pub的内容

3. 粘贴到GitHub设置中的SSH and GPG keys

4. 回到终端创建远程地址别名

   git remote add [别名] [地址]
