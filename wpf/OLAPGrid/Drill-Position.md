---
layout: post
title: Drill Position| OlapGrid | Wpf | Syncfusion
description: drill position
platform: wpf
control: OlapGrid
documentation: ug
---

# Drill Position

Drill position allows the user to drill only the current position of a selected member and it will exclude the drilled data of the selected member in other positions by using MDX query. It can be enabled by setting the **"DrillType"** enumeration to **"DrillPosition"** in the OlapReport.

{% tabs %}

{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition;

{% endhighlight %}

{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Data Relation\Drill Types





