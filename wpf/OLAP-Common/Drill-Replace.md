---
layout: post
title: Drill Replace in WPF OLAP Common control | Syncfusion
description: Learn about Drill Replace support in Syncfusion WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
 documentation: ug
---

# Drill Replace in WPF OLAP Common

Drill replace displays only the immediate child members and ancestors on drill-down and drill-up respectively.

The following code illustrates how to achieve drill replace support in a current report.

{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace;


{% endhighlight %}


{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace

{% endhighlight %}
{% endtabs %}


