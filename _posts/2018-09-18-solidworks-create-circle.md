---
layout: article
title: 【草图】圆的创建
key: 10002
tags: SolidworksAPI
category: blog
date: 2018/9/3 星期一 23:00:53 
modify_date: 2018/9/3 星期一 23:01:00 

---

介绍solidworks二次开发创建圆的几种命令

<!--more-->

#Solidworks API 圆的创建#

其中用到的命令有：

> 三点确定一个圆 ：PerimeterCircle（x1,y1,x2,y2,x3,y3）

> 圆心和圆上一点确定一个圆：CreateCircle（x1,y1,z1,x2,y2,z2）

>圆心和半径确定一个圆： CreateCircleByRadius(x,y,z,radius)


操作示例：



    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
    Dim Swapp As SldWorks.SldWorks
    Dim Part As SldWorks.ModelDoc2
    Dim sketchmer As SldWorks.SketchManager
    Swapp = CreateObject("SldWorks.Application")
    Part = Swapp.ActiveDoc
    sketchmer = Part.SketchManager
    sketchmer.InsertSketch(True)
    sketchmer.CreateLine(-0.05, 0, 0, 0.05, 0, 0)
    sketchmer.CreateLine(0.05, 0, 0, 0, 0.05 * 3 ^ (1 / 2), 0)
    sketchmer.CreateLine(-0.05, 0, 0, 0, 0.05 * 3 ^ (1 / 2), 0)
    sketchmer.PerimeterCircle(0, 0, -0.025, 0.025 * 3 ^ （1 / 2）, 0.025, 0.025 * 3 ^ （1 / 2）)
    sketchmer.CreateCircle(0, 0.05 / 3 ^ (1 / 2), 0, 0.05, 0, 0)
    sketchmer.CreateCircleByRadius(0, 0.05 / 3 ^ (1 / 2), 0, 0.1)
    sketchmer.InsertSketch(True)
    End Sub



