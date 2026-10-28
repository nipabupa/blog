---
title: Dearpygui基本使用
description: 
date: 2025-02-22T00:47:57+08:00
draft: false
featureimage: https://free.picui.cn/free/2025/11/09/69105ac665965.png
series: ['document']
series_order: 1
categories:
    - Python
tags:
    - Python三方库
    - GUI
---

{{< github repo="hoffstadt/DearPyGui" >}}

## 安装

```shell
pip install dearpygui
```

## 概念


## 基本样例

```python
import dearpygui.dearpygui as dpg
import dearpygui.demo as demo

dpg.create_context()
dpg.create_viewport(title='Custom Title', width=600, height=300)

with dpg.window(label="Example Window"):
    dpg.add_text("Hello, world")
    dpg.add_button(label="Save")
    dpg.add_input_text(label="string", default_value="Quick brown fox")
    dpg.add_slider_float(label="float", default_value=0.273, max_value=1)

demo.show_demo()
dpg.setup_dearpygui()
dpg.show_viewport()
dpg.start_dearpygui()
dpg.destroy_context()
```

## 生命周期





