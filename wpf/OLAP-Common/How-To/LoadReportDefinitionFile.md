---
layout: post
title: LoadReportDefinitionFile| OLAPCommon | Wpf | Syncfusion
description: loadreportdefinitionfile
platform: wpf
control: OLAPCommon
 documentation: ug
---

# LoadReportDefinitionFile



You can bind the OlapReport as XML file to OlapDataManager using the LoadReportDefinitionFile method. This contains two steps as follows:

1. Loading the report definition file and
2. Loading a specific report in that file by giving its name



The following code snippet will illustrate the loading of the report definition file:


{% tabs %}
{% highlight c# %}

olapDataManager.LoadReportDefinitionFile(@"C:\SampleReports\SalesAnalysis.xml");
olapDataManager.LoadReport("SalesOn2003");

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.LoadReportDefinitionFile("C:\SampleReports\SalesAnalysis.xml")
olapDataManager.LoadReport("SalesOn2003")
{% endhighlight  %}
{% endtabs %}

