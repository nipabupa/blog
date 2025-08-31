---
title: C语言字符串操作
description: 
date: 2025-08-12T08:14:12+08:00
draft: false
featuredimg: https://img.remit.ee/api/file/BQACAgUAAyEGAASHRsPbAAKH2WihUpufvuakb4xH9siasX-uMyPJAAJIGAADcwhV-bOcKe0Qlq42BA.jpeg
categories:
    - C语言
tags:
    - 字符串
---

## 字符串含义

字符实际意义上就是一个有特殊含义的非负整数，与整数类型无实质差异。

- `char`即是一个字节的非负整数，范围0-127，表示所有ASCII字符
- `UTF-8`等编码下的字符，是由多个字节表示的非负整数（按照一定的编码方式排列）

```
# 第一位0表示单字节char
01000000: 对应十进制64，代表字符`@`
# UTF-8通过字节的高位标识长度
# 首字节的连续1的数量表示总字节数（如110xxxxx为2字节，1110xxxx为3字节），后续字节以10xxxxxx开头
110XXXXX 10XXXXXX: 对应数字为各个字节的X拼接后的二进制数字，根据转换表转换为对应字符
```
```c
printf("%d\n", 64);
// -> 64
printf("%c\n", 64);
// -> @
```

## 字符串定义

```c
// 常量字符串
const char* str1 = "Hello World 1";
// 可变字符串(字符数组)
char str2[] = "Hello World 2";
// 可变字符串(字符数组)，手动长度，注意需要字符数量+1，最后一位存放\0字符
char str3[12] = "Hello World 3";

printf("%s\n", str1); // -> Hello World 1
printf("%s\n", str2); // -> Hello World 2
printf("%s\n", str3); // -> Hello World 3
```

## 字符串基本信息


### 获取字符串长度

```c
#include <stdio.h>
#include <string.h>

const char* str1 = "Hello World 1";
char str2[] = "Hello World 2";
char str3[14] = "Hello World 3";

int len1 = strlen(str1);
int len2 = strlen(str2);
int len3 = strlen(str3);

printf("%d\n", len1); // -> 13
printf("%d\n", len2); // -> 13
printf("%d\n", len3); // -> 13
```

### 遍历字符串

```c
#include <stdio.h>
#include <string.h>

const char* str1 = "Hello World 1";
char str2[] = "Hello World 2";

for (int i; i<strlen(str1); i++) {
    printf("%c", str1[i]); // H e l l o   W o r l d 1
}
```

### 字符串裁减与拼接

```c

```

### 字符串分割

#### 基于`strtok`或`s_strtok`的字符分割

非线程安全strtok
```c
char* str = "hello,my,world";  
char* delim = ",";  
// 首次调用传入要分割的字符串与分割字符串
char* token = strtok(str, delim);  // token = "Hello"
// 之后只需传入NULL与分割字符串，strtok内部记录了剩余字符串，因此多线程环境下不安全
token = strtok(NULL, delim);  // token = "my"
token = strtok(NULL, delim);  // token = "world"
```
线程安全s_strtok
```c
char* str = "hello,my,world";  
char* delim = ",";  
char* lastToken = NULL;
// 首次调用传入要分割的字符串与分割字符串
char* token = strtok(str, delim);  // token = "Hello"
// 之后只需传入NULL与分割字符串，strtok内部记录了剩余字符串，因此多线程环境下不安全
token = strtok(NULL, delim);  // token = "my"
token = strtok(NULL, delim);  // token = "world"
```

#### 基于`sscanf`的模式匹配

```c
#include <stdio.h>

char str1[20] = "192.168.0.100/24";
char res[15];
int mask;
// 先匹配到非/字符，在匹配一个/，然后匹配一个整数
sscanf(str1, "%[^/]/%d", res, &mask);
printf("%s %d\n", res, mask); // 192.168.0.100 24

char str2[20] = "192.168.0.100/22";
int ip[4];
sscanf(str2, "%d.%d.%d.%d/%d", &ip[0], &ip[1], &ip[2], &ip[3], &mask);
printf("%d %d %d %d %d\n", ip[0], ip[1], ip[2], ip[3], mask);  // -> 192 168 0 100 22
```

### 字符串替换


### 字符串查找

```

```

### 字符串转数字
