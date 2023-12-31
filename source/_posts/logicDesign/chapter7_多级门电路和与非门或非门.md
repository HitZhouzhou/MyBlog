---
title: 第7章 多级门电路/与非门和或非门
description: "\U0001F967本文对数字电路第七章的内容进行总结"
mathjax: true
tags:
  - 数字电路
categories:
  - 数字电路
abbrlink: c8a56023
date: 2023-10-24 19:19:03
updated: 2023-10-24 22:00:00
---
# 多级门电路/与非门和或非门

## 主线

1. 多级门电路
2. 与非门和或非门
3. 两级与非门和或非门电路设计
4. 多级与非门和或非门电路设计
5. 用门代替符号转换电路
6. 二级多输出电路设计
7. 多输出与非门和或非门电路

## 7.1多级门电路

电路的级数:电路中串联的门的最大数目就是电路的级数.

### 7.1.1改变电路级数的方法:

1. 与或电路的级数会随着对推导出来的积之和式的因式分解而增加.
2. 或与电路的级数会随着对推导出来的和之积式的展开而增加.

> 有时通过因式分解/展开各项可以增加电路的级数,从而减少需要的门数和门输入数目,但有时增加电路的级数反而会增大制造成本.

### 7.1.2用树状图确定确定为了实现一个函数需要的门和门输入数

1. $Z_1=[(A+B)C+DE(F+G)H]$
2. $Z_2=A+B[C+DE(F+G)]$
   ![Alt text](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image.png)

### 7.1.3找出一个最简的二级结果,为什么必须要同时考虑函数的和之积式和积之和式

因为要比较和之积式和积之和式的化简结果才知道,哪种方式最终使用的门数最少,以及门输入量最少.

## 7.2与非门和或非门

### 逻辑电路设计者常使用与非门和或非门的原因

1. 和与门、或门相比,通常与非门和或非门速度更快,需要的元件更少.
2. 只使用与非门或者或非门就能实现任何逻辑电路.

![image-20230921154114950](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230921154114950.png)

### 确定一组门是否的功能完善的方法

1. 写出每个门所实现的函数的最简积之和表达式.
2. 如果出现了取反运算,那么可以通过适当选择对应门的输入来实现非门.
3. 尝试是否可以实现与运算或者或运算,一旦实现其中一个,则可实现另外一个(待补)

> 需要用与非门画出函数$F=((X+Y)'+(X'+Z)')'$的电路图

## 7.3两级与非门和或非门电路设计

根据Demorgan定律,可以很容易的将由与门和或门组成的电路转成由与非门或者或非门组成的电路.

> Demorgan定律:
> $$
> (X_1+X_2+...+X_n)'=X_1'X_2'...X_n'\\
> (X_1X_2...X_n)'=X_1'+X_2'+...+X_n'
> $$

举例:
$$
\begin{split}
F&=A+BC'+B'CD\\
&=[A'(BC')'(B'CD)']'(与非-与非)\\
&=[A'(B'+C)(B+C'+D')]'\\
&=A+(B'+C)'+(B+C'+D')'\\
&=[A+(B'+C)'+(B+C'+D')']'(或非-或非-取反)
\end{split}
$$
有上可知,我们得到了一个或非-或非-取反电路,但是如果我们想得到一个只含有或非门的电路,**就要先化简成最简和之积式**,**而不是最简积之和式**.

举例:我们将上式中的$F$改写成最简和之积式.
$$
\begin{split}
F=&(A+B+C)(A+B'+C')(A+C'+D)\\
=&\{[(A+B+C)(A+B'+C')(A+C'+D)]'\}'\\
=&\{(A+B+C)'+(A+B'+C')+(A+C'+D)'\}'(或非-或非)\\
=&\{(A'B'C')+(A'BC)+(A'CD')\}'\\
=&(A'B'C')'(A'BC)'(A'CD')'\\
\end{split}
$$
在最简和之积式的情况下,可以化简为只含或非门的电路,在最简积之和式的条件下,可以化简为只含与非门的电路.

### 二级电路的八种形式

1. 与-或
2. 与非-与非
3. 或非-或
4. 或-与非
5. 或-与
6. 或非-或非
7. 与-或非
8. 与非-或非

![image-20230923150136864](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923150136864.png)

![image-20230923150150564](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923150150564.png)
$$

$$
对于二级电路,共有:$2^4=16$种组合,但是其它八种是不完善的,他们不能表示所有的开关函数.



因为集成电路中的与非门和或非门易于得到,所以最常用的两种电路是:与非-与非,或非-或非.

### 设计最简两级与非-与非电路的步骤:

1. 找出F的**最简积之和式**

2. 画出对应的与或电路

3. 用与非门代替所有门,保持原有门的相互连接方式不变.如果门有任何单个输入变量,则对其取反.

   ![image-20230923150933787](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923150933787.png)

   ### 设计最简两级或非-或非电路的步骤:

   1. 找出F的**最简和之积式**
   2. 画出对应的或-与电路
   3. 用或非门代替所有的门,并保留原有门的相互连接方式不变.如果对输出门有任何作为输入的单个变量,则将这些变量取反.

   ## 多级与非门和或非门的电路设计

   ### 设计多级**与非门**的具体步骤:

   1. 化简要实现的开关函数
   2. 设计多级与门和或门电路,且输出级必须为或门.与门的输出不能作为其他与门的输入;或门的输出不能作为其他或门的输入.
   3. 将输出门作为第一级来标识电路的级数.将所有门替换为与非门,保留所有门之间的连接方式不变,对1,3,5…级的门输入取反,而对2,4,6…级门输入保持不变.

   ![image-20230923151854252](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923151854252.png)![image-20230923151901391](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923151901391.png)

## 用门的替代符号转换电路

![image-20230923152059863](/Users/zhouzhou/Library/Application Support/typora-user-images/image-20230923152059863.png)

将与-或电路转换成为与非电路的一般步骤:

1. 通过在门的输出端添加取反圆圈,将所有的与门替换为与非门.通过在门的输入端添加取反符号,将所有的或门替换成与非门.
2. 每当反相输出连接到反向输入,则不需要进行任何操作,因为两次取反可以抵消.
3. 每当非反相输出连接到反相输入,或者反过来,则要插入一个反相器,以抵消掉取反圆圈.
4. 如果一个变量连接到反相输入,那么对该变量取反.

![image-20230923154958341](http://hitszzhou.oss-cn-shenzhen.aliyuncs.com/assets/image-20230923154958341.png)

## 7.6二级、多输出电路设计

