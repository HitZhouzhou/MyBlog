---
title: 第一章 随机事件与概率
description: "\U0001F967本文对概率率第一章的内容进行总结"
mathjax: true
tags:
  - 概率论
categories:
  - 概率论
abbrlink: c8a56023
date: 2023-10-24 19:19:03
updated: 2023-10-24 22:00:00
---

# 第一章总结

## 主线
1. 古典概率
2. 几何概率
3. 统计概率
4. 概率的公理化定义
## 1.古典概率
定义:若$E $为一个古典概型的实验,则E满足:  
1. 只有有限个基本事件
2. 每个基本事件发生的可能性相等

$P(A)=\frac{A中包含的基本事件个数}{基本事件总数} $  
> 用此公式计算时常常要用到排列组合的知识来计算分子分母的基本事件数  

## 2.几何概率
提出:概率的古典定义是在样本空间的基本事件的个数有限时给出的,当基本事件的个数无穷多时就不适用了,因此提出了几何概率.  
定义: 向一个区域S中掷一质点M,M必然落在S中且M落在S中的区域A上的可能性只与A的度量有关,与其他因素无关,则这个试验为几何概型试验.
$$P(A)=\frac{L(A)}{L(S)} $$

## 3.统计概率
提出:古典概率和几何概率都只在基本事件的发生是等可能的条件下才成立,有很大的局限性.实际上,很多试验不具有等可能的性质.
> 如接电话次数为:0,1,2,3...次,这些试验结果不是等可能的.

设$A $为联系于某一试验的事件,将试验在相同条件下重复n次,用m表示A出现的个数,则$\frac{m}{n} $称为事件A的**相对频率**,记作$f_n(A) $
$$f_n(A)=\frac{m}{n} $$

定义:在一组固定条件下,重复做n次试验,当n增大时,事件A出现的频率$f_(A) $围绕着某一常数p摆动,且随着n的增大,这个摆动幅度越来越小,则称p为事件A的概率.
$$P(A)=p $$ 

## 概率的公理化定义
提出:由于以上三种概率都满足三条相同的性质,根据这三条相同的性质提出概率的三条公理:

**公理1**$$P(A)\geq 0 $$

**公理2**$$P(S)=1 $$

**公理3** 对于互不相容的事件$A_1,A_2,...A_n... $,有$$P(A_1+A_2+A_3\dots+A_n\dots)=P(A_1)+P(A_2)+\dots+P(A_n)+... $$
