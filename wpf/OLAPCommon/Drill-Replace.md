---
layout: post
title: Drill Replace| OLAPCommon  | Wpf | Syncfusion
description: drill replace
platform: wpf
control: OLAPCommon 
documentation: ug
---

# Drill Replace

Drill Replace displays only the immediate child members and ancestors on drill-down and drill-up respectively.

The following code illustrates how to achieve drill replace support in a current report:

{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace;


{% endhighlight %}


{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillReplace

{% endhighlight %}
{% endtabs %}


