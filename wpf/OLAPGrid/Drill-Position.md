---
layout: post
title: Drill-Position
description: drill position
platform: wpf
control: OLAP Grid
documentation: ug
---

# Drill Position

Drill position feature enables the user to drill only the current position of a selected member in the OlapReport. This will exclude the drilled data of the selected member in other positions by using MDX query.

## Use Case Scenarios

This feature is useful when the objective of analysis is to view the drilled data only in current position of selected member.

## Tables for Properties, Methods, and Events

### Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td><td>
{{ '**Reference links**' | markdownify }}</td></tr>
<tr>
<td>
DrillType</td><td>
Enables the user to set the drill type of an OlapReport</td><td>
CLR</td><td>
Enum</td><td>
-</td></tr>
</table>


## Sample Link

A sample is available in following locations:

## Windows XP:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Data Relation\Drill Types Demo

## Windows 7/Vista:

C:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\x.x.x.x\BI\WPF\OlapGrid.WPF\SamplesData Relation\Drill Types Demo

# Adding Drill Position to an Application 

Adding Drill position feature to an application is described in the following code snippet:

  {% highlight c# %}

    [CS]

dataManager.CurrentReport.DrillType = DrillType.DrillPosition;

    {% endhighlight %}



  {% highlight vbnet %}

   [VB]

dataManager.CurrentReport.DrillType = DrillType.DrillPosition

    {% endhighlight %}





