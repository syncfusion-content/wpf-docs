---
layout: post
title: Drill Replace
description: Drill replace
platform: wpf
control: OLAP Common
documentation: ug
---

# Drill Replace

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


