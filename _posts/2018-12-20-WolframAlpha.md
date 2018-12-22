---
layout: article
title: 【WolframAlpha】工程应用中计算理论走线量的方法
key: 10004
tags: blog
category: blog
date: 018/12/21 星期五 24:00:53 
modify_date: 2018/12/21 星期五 24:00:53 

---


这类属于装载问题（packing problem），理论上可以抽象为一些数量的圆在更大的圆或正方形中的排布问题，WolframAlpha中提供这样的算例可以帮助我们计算。

<!--more-->

#【WolframAlpha】工程应用中计算理论走线量的方法#


在机柜或操作台设计过程中，经常遇到走线问题，例如机柜底部进线的圆孔，机柜内部前后穿线的方孔等。在遇到这类问题时，通常时采用经验法估算出开孔大小。虽然在实际应用中并不会出现太大问题，但在设计交流时并没有理论数据支撑。

这类属于装载问题（packing problem），理论上可以抽象为一些数量的圆在更大的圆或正方形中的排布问题。[WolframAlpha](https://www.wolframalpha.com/)中提供这样的算例。

![image](http://wx3.sinaimg.cn/mw690/e3dda551ly1fydlqte4ddj212a0cbjsi.jpg)

* * *

#### 情形一：已知线径及线量，计算理想情况下所需开孔的大小
##### 例1.1：计算50根半径为2mm的线理论情况下需要开多大的圆孔？
在WolframAlpha的计算框中输入以下命令即可得到三种情况下的开圆孔半径。
>pack 50 circles of radius 2mm in a circle

得到结果如下：

**1.Densest known packing：**

![image](http://wx2.sinaimg.cn/small/e3dda551ly1fydm7mq4x2g205k05kt8p.gif)

| 项目 |值  |
| --- | --- |
| radius（线缆半径 ）|  2mm|
| container radius（开孔半径） |15.9mm  |
|filled fraction（占用空间比例）  |79.16%  |
| empty fraction（剩余空间比例 ）|20.84% |
| symmetry（对称形）| 无 |

**2.Hexagonal packing:**

![image](http://wx4.sinaimg.cn/small/e3dda551ly1fydm81dv2cg205k05kdfs.gif)

| 项目 |值  |
| --- | --- |
| radius（线缆半径 ）|  2mm|
| container radius（开孔半径） |16.42mm  |
|filled fraction（占用空间比例）  |74.16%  |
| empty fraction（剩余空间比例 ）|25.84% |
| symmetry（对称形）|无 |


**3.Square packing:**

![image](http://wx4.sinaimg.cn/small/e3dda551ly1fydm8asaiag205k05kaa0.gif)

| 项目 |值  |
| --- | --- |
| radius（线缆半径 ）|  2mm|
| container radius（开孔半径） 17.23mm  |
|filled fraction（占用空间比例）  |67.36%  |
| empty fraction（剩余空间比例 ）|32.64% |
| symmetry（对称形）|镜像|

##### 例1.2：计算50根半径为2mm的线理论情况下需要开多大的方孔？
在WolframAlpha的计算框中输入以下命令即可得到不同情况下的开方孔尺寸。
>pack  50 circles of radius 2 mm  in a square 


详细结果可以查看[DEMO](https://www.wolframalpha.com/input/?i=pack++50+circles+of+radius+2+mm+in+a+square)。

* * *

#### 情形二：已经确定开孔大小，确定理论上可以走多少已知线径的线缆
##### 例2.1：开孔直径为53.5mm(半径为26.75mm)的开孔理论上可以穿过多少直径2.5mm的线？
>pack circles of radius 1.25 mm   in a circle of radius 26.75 mm

得到结果如下：

**1. 最密集排布（Densest known packing）**

![image](http://wx4.sinaimg.cn/small/e3dda551ly1fydn5w7gphg205k05kq2x.gif)


| 项目 |值  |
| --- | --- |
| number（数量） | 389 |
| radius（线缆半径 ）|  1.25mm|
| container radius（开孔半径） |26.75mm  |
|filled fraction（占用空间比例）  |84.94%  |
| empty fraction（剩余空间比例 ）| 15.06% |
| symmetry（对称形）| 否 |

**2. 六角形排布（Hexagonal packing）**

![image](http://wx1.sinaimg.cn/small/e3dda551ly1fydn5zq3ifg205k05kdfr.gif)

| 项目 |值  |
| --- | --- |
| number（数量） | 379 |
| radius（线缆半径 ）|  1.25mm|
| container radius（开孔半径） |26.75mm  |
|filled fraction（占用空间比例）  |82.76%  |
| empty fraction（剩余空间比例 ）| 17.24% |
| symmetry（对称形）| 否 |

**3. 正方形排布（Square packing）**

![image](http://wx3.sinaimg.cn/small/e3dda551ly1fydn64muzug205k05kt8m.gif)


| 项目 |值  |
| --- | --- |
| number（数量） | 333 |
| radius（线缆半径 ）|  1.25mm|
| container radius（开孔半径） |26.75mm  |
|filled fraction（占用空间比例）  |72.71%  |
| empty fraction（剩余空间比例 ）| 27.29% |
| symmetry（对称形）| 方形 |

##### 例2.2：边长为20mm的的方孔理论上可以穿过多少直径2.5mm的线？
在WolframAlpha的计算框中输入以下命令即可得到结果。

>pack circles of radius 1.25 mm in a square of side 20mm


详细结果可以查看[DEMO](https://www.wolframalpha.com/input/?i=pack+circles+of+radius+1.25+mm+in+a+square+of+side+20+mm)。


* * *

更多计算实例可以参考[Examples forGeometric Packing in 2D](https://www.wolframalpha.com/examples/mathematics/geometry/packing-and-covering-problems/geometric-packing-in-2d/)。这些都是理想化的情况，实际应用考虑线缆缠绕、弯曲等问题，需要乘以经验系数才能得到更为准确的数据。




