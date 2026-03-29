---
title: 🐧Linux 命令本
draft: true
tags:
  - "#工具箱"
  - "#Linux"
---
> [!note] 本篇说明

# 常用命令


| 命令                                   | 释义  |
| ------------------------------------ | --- |
| pwd                                  |     |
| cd                                   |     |
| ls                                   |     |
| ls -l                                |     |
| mkdir                                |     |
| who am i                             |     |
| which python/echo                    |     |
| tail [-f] filename -n[+]10           |     |
| head                                 |     |
| watch -n -d 1 [nvidia-smi]           |     |
| ssh                                  |     |
| top                                  |     |
| htop                                 |     |
| screen -S name                       |     |
| screen -r name                       |     |
| screen -X -S name quit               |     |
| source ~/conda/bin/activate env_name |     |
| tar                                  |     |
| clear                                |     |
| kill -l / -9 [PID]                   |     |
| touch                                |     |
| rm -rf                               |     |
| tree                                 |     |
| df -a / -h / -i                      |     |
| du -sh * / --max-depth=2 / -d 2      |     |
| vim                                  |     |
| mv                                   |     |
| find                                 |     |
| cat                                  |     |
| echo                                 |     |
|                                      |     |

# man


# rsync

## 一、什么是rsync

rsync 是一个常用的 Linux 应用程序，用于文件同步。

它可以在本地计算机与远程计算机之间，或者两个本地目录之间同步文件（但不支持两台远程计算机之间的同步）。

它名称里面的`r`指的是 remote rsync 其实就是"远程同步"（remote sync）的意思。与其他文件传输工具（如 FTP 或 scp）不同，rsync 的最大特点是会检查发送方和接收方已有的文件，仅传输有变动的部分（默认规则是文件大小或修改时间有变动）。

## 二、安装

如果本机或者远程计算机没有安装 rsync，可以用下面的命令安装。

> ```bash
> # Debian
> $ sudo apt-get install rsync
> ```

注意，传输的双方都必须安装 rsync。

## 三、常用命令

> ```
> 
> ```


# ssh



---
> [!success] 结语



