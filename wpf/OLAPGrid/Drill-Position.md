---
layout: post
title: Drill Position| OLAP Grid | Wpf | Syncfusion
description: drill position
platform: wpf
control: OLAP Grid
documentation: ug
---

# Drill Position

Drill position feature enables the user to drill only the current position of a selected member in the OlapReport. This will exclude the drilled data of the selected member in other positions by using MDX query.


### Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
DrillType</td><td>
Enables the user to set the drill type of an OlapReport</td><td>
CLR</td><td>
Enum</td><td>
-</td></tr>
</table>


### Sample Link

A sample is available in following locations:

#### Windows XP:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Data Relation\Drill Types Demo

####  Windows 7/Vista:

C:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\x.x.x.x\BI\WPF\OlapGrid.WPF\SamplesData Relation\Drill Types Demo

## Adding Drill Position to an Application 

Adding Drill position feature to an application is described in the following code snippet:

{% tabs %}
  {% highlight c# %}

    

dataManager.CurrentReport.DrillType = DrillType.DrillPosition;

    {% endhighlight %}



  {% highlight vbnet %}

   

dataManager.CurrentReport.DrillType = DrillType.DrillPosition

    {% endhighlight %}
{% endtabs %}




