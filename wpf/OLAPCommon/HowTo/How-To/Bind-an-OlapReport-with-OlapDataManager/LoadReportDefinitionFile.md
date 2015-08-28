---
layout: post
title: LoadReportDefinitionFile
description: loadreportdefinitionfile
platform: wpf
control: OLAP Common
documentation: ug
---

# LoadReportDefinitionFile



You can bind the OlapReport as xml file to OlapDataManager using the LoadReportDefinitionFile method. This contains two steps as follows:

1. Loading the report definition file and
2. Loading a specific report in that file by giving its name



The following code snippet will illustrate the loading of the report definition file:



{% highlight c# %}

olapDataManager.LoadReportDefinitionFile(@"C:\SampleReports\SalesAnalysis.xml");
olapDataManager.LoadReport("SalesOn2003");

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.LoadReportDefinitionFile("C:\SampleReports\SalesAnalysis.xml")
olapDataManager.LoadReport("SalesOn2003")
{% endhighlight  %}


