---
layout: post
title: LoadReportDefinitionFromStream| OLAPCommon | Wpf | Syncfusion
description: loadreportdefinitionfromstream
platform: wpf
control: OLAPCommon
documentation: ug
---

# LoadReportDefinitionFromStream



You can load the OlapReport as a stream to the OlapDataManager using LoadReportDefinitionFromStream method. This contains two steps as follows:

1. Loading the report stream 
2. Loading the specific report in that stream by giving its name

The following code snippet will illustrate the loading of the report definition from a stream:


{% tabs %}
{% highlight c# %}

olapDataManager.LoadReportDefinitionFromStream(reportStream);
olapDataManager.LoadReport("SalesOn2003");
{% endhighlight  %}


{% highlight vbnet %}

olapDataManager.LoadReportDefinitionFromStream(reportStream)
olapDataManager.LoadReport("SalesOn2003")

{% endhighlight  %}
{% endtabs %}

## Sequential Diagram

The following sequential diagram shows the workflow of OlapBase when user gives input as OlapReport.

![](LoadReportDefinitionFromStream_images/LoadReportDefinitionFromStream_img1.png)





OLAP Base sequential diagram
{:.caption}



