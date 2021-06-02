---
layout: post
title: Rename and remove a report| OLAPCommon | Wpf | Syncfusion
description: Rename and remove a report in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Rename and remove a report

Once the report collection is loaded with reports, you can rename or remove any reports in that collection by using the RenameReport and RemoveReport methods.

## RenameReport

A report in the report collection of OlapDataManager can be renamed by invoking RenameReport method with arguments such as, index of the report and new name for the report or with old name and new name of the report. The following code snippet will illustrate this: 

{% tabs %}
{% highlight c# %}



olapDataManager.RenameReport(2, "SalesAnalysisOn2003");

olapDataManager.RenameReport("RevenueAnalysis", "RevenueAnalysisOn2003");

{% endhighlight  %}

{% highlight vbnet %}



olapDataManager.RenameReport(2, "SalesAnalysisOn2003")

olapDataManager.RenameReport("RevenueAnalysis", "RevenueAnalysisOn2003")

{% endhighlight  %}
{% endtabs %}

## RemoveReport

A report in the report collection of the OlapDataManager can be removed by invoking the RemoveReport method. This method will accept the report name as argument and remove that report from report collection of OlapDataManager.

The following code snippet will illustrate the removal of a report:

{% tabs %}
{% highlight c# %}

olapDataManager.RemoveReport("SalesAnalysisOn2005");

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.RemoveReport("SalesAnalysisOn2005")

{% endhighlight  %}
{% endtabs %}
