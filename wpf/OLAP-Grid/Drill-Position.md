---
layout: post
title: Drill Position in WPF OLAP Grid | Syncfusion®
description: The drill position support in OLAP Grid allows drilling only current position of selected member while excluding drilled data of that member in other positions.
platform: wpf
control: OLAP Grid
documentation: ug
---

#  Drill Position in WPF OLAP Grid

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





