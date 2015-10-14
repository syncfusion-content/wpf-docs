---
layout: post
title: ToolTip| OLAP Chart | Wpf | Syncfusion
description: ToolTip
platform: wpf
control: OLAP Chart
documentation: ug
---

# ToolTip

The OLAP Chart for WPF provides series information (Measure, Primary x-axis and y-axis values, and series name) through Series ToolTips, when the mouse pointer is moved over chart points.

## How to enable or disable a chart tool tip?

The tooltip in an OlapChart can be enabled or disabled by setting the ShowToolTip property.

The following code snippet shows how to disable the series tooltip:


 {% highlight c# %}
 
    



this.olapchart1.Series[0].ShowToolTip = false;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Me.olapchart1.Series(0).ShowToolTip = False

 {% endhighlight %}