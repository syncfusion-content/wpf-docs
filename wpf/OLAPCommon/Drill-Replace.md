---
layout: post
title: Drill-Replace
description: drill replace
platform: wpf
control: OLAP Common 
documentation: ug
---

# Drill Replace

Drill Replace displays only the immediate child members and ancestors on drill-down and drill-up respectively.

The following code illustrates how to achieve drill replace support in a current report:

{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace;


{% endhighlight %}


{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace

{% endhighlight %}



