---
layout: post
title: Drill-Position
description: drill position
platform: wpf
control: OLAP Chart
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
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
DrillType</td><td>
Enables the user to set the drill type of OlapReport</td><td>
CLR</td><td>
Enum</td></tr>
</table>


## Sample Link

A sample is available in the following locations:

## Windows XP

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapChart.WPF\Samples\Data Relation\Drill Types Demo

## Windows 7/Vista

C:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\x.x.x.x\BI\WPF\OlapChart.WPF\Samples\Data Relation\Drill Types Demo

# Adding Drill Position to an Application 

The following code snippet explains the implementation of Drill Position feature in an application:

 {% highlight c# %}
 
   [CS]



dataManager.CurrentReport.DrillType = DrillType.DrillPosition;

 {% endhighlight %}




 {% highlight vbnet %}
  
 [VB]



dataManager.CurrentReport.DrillType = DrillType.DrillPosition

 {% endhighlight %}












