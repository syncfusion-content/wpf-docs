---
layout: post
title: Multi level DrillDown| OLAP Chart | Wpf | Syncfusion
description: Multi-level DrillDown
platform: wpf
control: OLAP Chart
documentation: ug
---

# Multi-level DrillDown

While binding hierarchical dimensions (for example, the time dimension could include 3 levels namely Year, Quarter, and Month), the Chart allows you to visualize the data for different levels by using the collapsible labels. This is illustrated in the following screenshot:

![](Core-Features_images/Core-Features_img36.png)


A sample, which demonstrates the multiple level Drill-Down feature, is available in the following sample installation location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Creating Reports\Reports In Code



## How to show/hide the expanders in an OlapChart?

The visibility of the expanders in the OlapChart can be toggled by using the ShowExpanders property available in the OlapReport. 

The following code snippet describes this in detail:


 {% highlight c# %}
 
   



this.olapchart1.OlapDataManager.CurrentReport.ShowExpanders = false;

 {% endhighlight %}

 {% highlight vbnet %}
  
  

 Me.olapchart1.OlapDataManager.CurrentReport.ShowExpanders = False

 {% endhighlight %}


The following image shows an OlapChart with expanders disabled:

![](Core-Features_images/Core-Features_img37.png)


N> Since this property interacts with the OlapDataManager you need to assign this property before the call to DataBind() or DataBind() method in the OlapChart and should be invoked after changing this property to see this in effect.
