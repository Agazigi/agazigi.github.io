---
title: 😯zsh 及 Oh-my-zsh 配置教程
draft: false
tags:
  - "#工具箱"
  - "#zsh"
  - "#Oh-my-zsh"
  - "#教程"
---
> [!note] 本篇说明
> zsh 是一个非常好用的 Shell，配合 Oh-my-zsh 这一美化包、功能扩展包，能够实现命令行补全、文件夹快速跳转等功能。

> [!tip] 快速安装
> 依次复制粘贴以下命令即可快速的完成 zsh 和 Oh-my-zsh 的配置：
> 
> Step1：安装 `zsh` 和 `Oh-my-zsh`
> ```bash
> apt install zsh
chsh -s /bin/zsh
sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
> ```
> Step2：安装 `命令提示` 和 `语法高亮` 插件
> ```bash
> git clone https://gh.xmly.dev/https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://gh.xmly.dev/https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
> ```
> Step3：修改 `.zshrc`
> ```bash
> vim ~/.zshrc
> ```
> Step4：在 `plugins` 添加插件
> ```txt
zsh-autosuggestions zsh-syntax-highlighting z
> ```

---
> [!success] 结语
> zsh 及 Oh-my-zsh 的使用不需要配置过多的插件和好看的主题，个人感觉使用原生的主题和以上推荐的两个插件就能够满足平常工作的大部分需求。
> 
> 参考文献：
> 1. https://www.zsh.org
> 2. https://github.com/z-shell
> 3. https://ohmyz.sh
> 4. https://www.haoyep.com/posts/zsh-config-oh-my-zsh/





