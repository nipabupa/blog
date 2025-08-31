---
title: OneTerm安装与配置
description: 
date: 2025-08-10T22:00:31+08:00
draft: false
categories:
    - 开发工具
tags:
    - 终端
---

{{< lead >}}
OneTerm是作者从开源社区浩如烟海的工具中筛选并配置而成的终端开发工具集。
{{< /lead >}}

## 安装Wezterm

参考[官方文档](https://wezterm.org/installation.html)

最推荐的终端Wezterm。

之前用过WindowsTerminal、Alacritty、UbuntuTerminal、和一些基于Electron的终端工具。综合性能、美观、易用性、兼容性、跨平台等多方面打分，个人认为wezterm最佳

Wezterm特性
- 基于Rust开发，支持GPU加速，性能优异
- 使用Lua进行配置，灵活度高；且可配置项相当多，定制能力优异
- 多标签页、窗口透明、背景图片
- 内置1000+主题
- 内置NerdFont字体（Jetbrains Mono、Nerd Font Symbols、Noto Color Emoji），支持连字符，开箱即用
- 支持显示图片
- 支持Linux、Windows、Macos，各平台显示效果一致

## 安装各类终端工具

- windows直接在Github Release下载对应二进制版本，加入环境变量即可
- Linux、MacOS根据情况选择对应的包管理器安装，或者也能下载二进制版本

|工具|说明|主页|windows支持|Linux支持|MacOS支持|
|:-:|:-:|:-:|:-:|:-:|:-:|
|starship|Prompt美化|[官网](https://starship.rs/zh-cn/)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|yzai|终端文件|[Github](https://github.com/sxyazi/yazi)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|fzf|模糊搜索神器|[Github](https://github.com/junegunn/fzf)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|rg|grep增强|[Github](https://github.com/BurntSushi/ripgrep)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|fd|find增强|[Github](https://github.com/sharkdp/fd)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|zoxide|cd增强|[Github](https://github.com/ajeetdsouza/zoxide)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|eza|ls增强|[Github](https://github.com/eza-community/eza)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|
|neovim|vim|[官网](https://neovim.io/)|{{< icon "check" >}}|{{< icon "check" >}}|{{< icon "check" >}}|

## 配置

```bash
# 下载源码
git clone https://github.com/nipabupa/oneterm

# windows
.\config_for_windows.ps1
# linux
./config_for_linux.sh
```
