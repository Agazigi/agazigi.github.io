---
title: Let' s Git!
draft: false
tags:
  - "#工具箱"
  - "#Git"
---
 
# Git 与 Learn Git Branching

Git就是一个分布式的版本管理系统。无论是个人开发还是协作开发，都能够对我们的代码进行十分友好的管理。

[Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)是一个免费的Git学习教程，用游戏的方式进行Git命令的教学，其树状的可视化分支使得Git的版本管理细节清晰可见。

本文提供了[Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)教程全通关的全部命令，本文既是一篇游戏教程，又是Git命令的一个工具箱。(＾▽＾)

# 一、主要
## 1.1 基础篇

这一部分要循序渐进的介绍Git的主要命令。本小节主要涉及到以下Git命令。

```bash
git commit # 提交记录
git branch <name> # 创建新分支
git checkout <name> # 切换分支
git switch <name> # 选择分支
git checkout -b <name> # 创建分支并切换到该分支上
git merge <name> # 将该分支合并到当前分支上
git rebase <name> # 将该分支当做当前分支的新基底
```
### 关卡1 - Git Commit
```bash
git commit
git commit
```
### 关卡2 - Git Branch
```bash
git checkout -b bugFix

git branch bugFix
git checkout bugFix
```
### 关卡3 - Git Merge
```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git merge bugFix
```
### 关卡4 - Git Rebase
```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```
## 1.2 高级篇

要开始介绍Git的超棒特性了，快来吧！本小节主要涉及到以下Git命令：

```bash
cat .git/HEAD # 查看HEAD
git symbolic-ref HEAD # 查看HEAD
git log # 查看提交记录
git checkout <name>^ # 向前移动一次，有几个^就移动几次
git checkout <name>~<num> # 向前移动num次
git branch -f <name> HEAD~<num> # 将<name>分支强制指向HEAD的第<num>级并提交
git branch -f <name> <name>
git reset <name>
git revert <name>
```
### 关卡1 - 分离HEAD
```bash
git checkout C4
```
### 关卡2 - 相对引用1
```bash
git checkout C4^
```
### 关卡3 - 相对引用2
```bash
git branch -f main C6
git checkout HEAD^
git branch -f bugFix HEAD^
```
### 关卡4 - 撤销变更
```bash
git reset HEAD^
git checkout pushed
git revert C2
```
## 1.3 移动提交记录

自由修改提交树。

## 1.4 杂项

Git技术、技巧与贴士大集合。

## 1.5 高级话题

只为真正的勇士。

# 二、远程
## 2.1 Push & Pull - Git 远程仓库

是时候分享你的代码了，让编码变得社区化吧。

## 2.2 Git 远程仓库高级操作

做一名仁慈的独裁者一定很有趣。
