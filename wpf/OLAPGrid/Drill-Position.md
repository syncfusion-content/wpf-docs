---
layout: post
title: Drill Position| OlapGrid | Wpf | Syncfusion
description: Support to drill only the current position of the selected member by using MDX query in OLAP Grid control.
platform: wpf
control: OlapGrid
documentation: ug
---

# Drill Position

Drill position allows users to drill only the current position of the selected member and exclude the drilled data of selected member in other positions by using the MDX query. This can be enabled by setting the **"DrillType"** enumeration to **"DrillPosition"** in the OLAP report.

{% tabs %}

{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition;

{% endhighlight %}

{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition

{% endhighlight %}

{% endtabs %}

A sample demo is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Data Relation\Drill Types





