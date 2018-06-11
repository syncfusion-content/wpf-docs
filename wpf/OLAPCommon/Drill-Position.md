---
layout: post
title: Drill Position Support for OLAP Report
description: Drill position support for OLAP report
platform: wpf
control: OLAP Common
documentation: ug
---

# Drill Position Support for OLAP Report

Drill position enables the user to drill the current position of a selected member in the OlapReport. This will exclude the drilled data of the selected member in other positions by using MDX query.



The following code illustrates how to achieve drill position support in current report:

{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition;

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.CurrentReport.DrillType = DrillType.DrillPosition

{% endhighlight %}
{% endtabs %}


