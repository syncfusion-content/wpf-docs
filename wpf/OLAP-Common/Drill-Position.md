---
layout: post
title: Drill Position in WPF OLAP Common control | Syncfusion
description: Learn about Drill Position support in Syncfusion WPF OLAP Common control and more.
platform: wpf
control: OLAP Common
documentation: ug
---

# Drill Position in WPF OLAP Common

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


