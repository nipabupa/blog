---
title: Python串口控制
description: 
date: 2025-02-21T00:47:57+08:00
draft: false
featureimage: https://free.picui.cn/free/2025/11/09/69105abf85acc.jpeg
categories:
    - Python
tags:
    - Python三方库
    - 串口控制
---

## 安装

```python
pip install pyserial
```

## 打开串口

```python
con = serial.Serial('COM3', 9600, timeout=60)  # Windows示例
```

## 写入数据

```python
# 发送字符串
con.write(b'command\n')
# 发送16进制字符串
con.write(bytes.fromhex('hex command\n'))
```

{{< alert >}}
交互型指令一般以\n或\r\n为结尾，可能存在不发送换行符不生效
{{< /alert >}}

## 读取数据

```python
# 读取1024字节
data = con.read(1024)
# 读取当前缓存中的所有数据
data = con.read(con.in_waiting)
# 读取数据直到某个标记
data = con.read_until(b'ok')
# 读取所有数据直到EOF
data = con.read_all()
```
