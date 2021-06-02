---
layout: post
title: OlapDataManager as a stream in WPF OLAPCommon control | Syncfusion
description: Get the reports in the olapdatamanager as a stream in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Get the reports in the OlapDataManager as a stream

You can get the report collection in the OlapDataManager as a stream by using GetReportAsStream method. This method will return the current report collection of the OlapDataManager as a stream.

The following code snippet will explain obtaining the report as a stream:

{% tabs %}
{% highlight c# %}

Stream reportStream = olapDataManager.GetReportAsStream();

{% endhighlight  %}

{% highlight vbnet %}

Dim reportStream As Stream = olapDataManager.GetReportAsStream()


{% endhighlight  %}
{% endtabs %}