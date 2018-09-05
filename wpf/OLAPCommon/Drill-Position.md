---
layout: post
title: Drill Position Support for OLAP Report
description: Drill position support for OLAP report
platform: wpf
control: OLAP Common
documentation: ug
---

# Drill Position Support for OLAP Report

Drill position enables users to drill the current position of the selected member in the OLAP report. This excludes the drilled data of the selected member in other positions by using the MDX query.



The following code illustrates how to achieve drill position support in the current report.

{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition;

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition

{% endhighlight %}
{% endtabs %}


