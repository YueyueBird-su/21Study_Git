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

## 1.3添加提交以及查看状态操作

- git status 查看当前仓库状态
- git add *** 将对应文件添加到暂存区
- git rm --catched *** 删除暂存区

