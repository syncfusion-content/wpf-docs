---
layout: post
title: Drill Position Support for OLAPReport
description: Drill position support for OLAPreport
platform: wpf
control: OLAP Common
documentation: ug
---

# Drill Position Support for OLAPReport

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


