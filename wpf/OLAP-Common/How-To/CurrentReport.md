---
layout: post
title: CurrentReport| OLAPCommon | Wpf | Syncfusion
description: currentreport
platform: wpf
control: OLAPCommon
 documentation: ug
---

# CurrentReport

Once the OlapReport is created by assigning the report to the CurrentReport property of the OlapDataManager, you can bind the OlapReport to the OlapDataManager.

The following code snippet explains the assigning of an OlapReport to CurrentReport property:

{% tabs %}
{% highlight c# %}

OlapDataManager.CurrentReport = olapReport;
{% endhighlight  %}



{% highlight vbnet %}

OlapDataManager.CurrentReport = olapReport


{% endhighlight %}
{% endtabs %}
