---
title: 第8章 用门电路设计和模拟组合电路
description: "\U0001F967本文对数字电路第8章的内容进行总结"
mathjax: true
tags:
  - 数字电路
categories:
  - 数字电路
abbrlink: c8a56023
date: 2023-10-24 19:19:03
updated: 2023-10-24 22:00:00
---
# 用门电路设计和模拟组合电路

## 主线

1. 门延迟和时序图
2. 组合逻辑的冒险
3. 逻辑电路的仿真和测试

## 8.3 门延迟和时序图

### 门延迟的原因

当改变逻辑电路的输入时,输出并不会立刻发生该变.门内的晶体管或者其他开关器件需要一定的时间对输入的变化做出反应,以至于对应门输入的改变,门输出的改变会延迟.![image-20230923164004537](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923164004537.png)

时序图常用来分析时序电路.这种图给出了电路中信号相对于时间函数的变化规律.通常把几个变量画在一张图中,这样很容易的观察出这些变量相对于其他变量随时间的变化.

## 组合逻辑的冒险

当组合电路的输入发生变化时,输出端可能会出现不期望的瞬变.当从输入到输出的不同路径有不同的传输延迟时就会发生这种瞬变.

### 静态1-冒险

由于任何单个变量的变化和某种传输延迟组成,电路输出可能会瞬间发生翻转变成0,而它本应该是1.

### 静态0-冒险

同理,输出由本来的恒定值0瞬间变成1.

### 动态冒险

电路的输出从本来的1变成0,或0变成1,发生了3次或者3次以上.

### 判断两级与-或电路冒险的方法

1. 写出电路的最简积之和表达式
2. 画出卡诺图,并圈定每个项
3. 如果任何两个相邻的1不能被同一个圈涵盖,那么这两个1之间转换就会有一个1-冒险.对于n变量的卡诺图,当一个变量变化,而其他n-1个变量不变的情况下就会发生这种转换.



---

对于多级电路的冒险的判断还未清楚