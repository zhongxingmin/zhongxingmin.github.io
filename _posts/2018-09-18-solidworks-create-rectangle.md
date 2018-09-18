---
layout: article
title: 矩形的创建
key: 10003
tags: blog
category: blog
date: 2018/9/3 星期一 23:00:53 
modify_date: 2018/9/3 星期一 23:01:00 
---

介绍solidworks二次开发创建矩形的几种命令

<!--more-->

#Solidworks API 矩形的创建#


操作示例：



 Public Class Form1
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click '创建边角矩形

        Dim sketchmer1 As SldWorks.SketchManager
        sketchmer1 = Getsketcher()
        sketchmer1.InsertSketch(True)
        sketchmer1.CreateCornerRectangle(-0.15, 0.1, 0, 0.15, -0.1, 0)
        sketchmer1.InsertSketch(True)
    End Sub

    Private Sub Button2_Click(sender As Object, e As EventArgs) Handles Button2.Click '创建中心矩形
        Dim sketcher2 As SldWorks.SketchManager
        sketcher2 = Getsketcher()
        sketcher2.InsertSketch(True)
        sketcher2.CreateCenterRectangle(0, 0, 0, 0.15, 0.15, 0)
        sketcher2.InsertSketch(True)
    End Sub

    Private Sub Button3_Click(sender As Object, e As EventArgs) Handles Button3.Click '创建3点边角矩形
        Dim sketcher3 As SldWorks.SketchManager
        sketcher3 = Getsketcher()
        sketcher3.InsertSketch(True)
        sketcher3.Create3PointCornerRectangle(0, 0, 0, 0.3 / (2 ^ (1 / 2)), 0.3 / (2 ^ (1 / 2)), 0, 0.2 * 2 ^ （1 / 2）, 0, 0)
        sketcher3.InsertSketch(True)
    End Sub

    Private Sub Button4_Click(sender As Object, e As EventArgs) Handles Button4.Click
        Dim sketcher4 As SldWorks.SketchManager
        sketcher4 = Getsketcher()
        sketcher4.InsertSketch(True)
        sketcher4.Create3PointCenterRectangle(0, 0, 0, 0.15 / (2 ^ (1 / 2)), 0.15 / (2 ^ (1 / 2)), 0, 0.1 * 2 ^ （1 / 2）, 0, 0)
        sketcher4.InsertSketch(True)
    End Sub

    Private Function Getsketcher() As SldWorks.SketchManager '创建子函数可重复调用
        Dim Swapp As SldWorks.SldWorks
        Dim Part As SldWorks.ModelDoc2
        Dim sketchmer As SldWorks.SketchManager
        Swapp = CreateObject("SldWorks.application")
        Part = Swapp.ActiveDoc
        sketchmer = Part.SketchManager
        Getsketcher = sketchmer
    End Function

    End Class




