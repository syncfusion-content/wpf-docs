---
layout: post
title: Retrieve the MDX Query of a CurrentReport| OLAPCommon | Wpf | Syncfusion
description: retrieve the mdx query of a currentreport
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Retrieve the MDX Query of a CurrentReport

The MDX query of a current report is used to display data in Grid/Chart control and it can be retrieved by calling the GetMDXQuery() method.

The following code explains how to retrieve MDX Query from the OlapDataManager:

{% tabs %}
{% highlight c# %}

olapDataManager.GetMDXQuery();

{% endhighlight %}

{% highlight vbnet %}

olapDataManager.GetMDXQuery()

{% endhighlight  %}
{% endtabs %}

## In Silverlight:


{% tabs %}
{% highlight c# %}

string currentMdxQuery = null;

//// Invoke the service call to retrieve the MDX query from the Server based on current report. 

_olapDataManager.GetMdxQuery(_olapDataManager.CurrentReport);

_olapDataManager.MdxQueryObtained += () =>

{

    ////MDX Query retrieved.

    currentMdxQuery = _olapDataManager.CurrentReport.CurrentMdxQuery;

};

{% endhighlight  %}

{% highlight vbnet %}

Dim currentMdxQuery As String

'Invoke the service call to retrieve the MDX query from the Server based on current report. 

_olapDataManager.GetMdxQuery(_olapDataManager.CurrentReport)

_olapDataManager.MdxQueryObtained += Function() 

'MDX Query retrieved.

currentMdxQuery = _olapDataManager.CurrentReport.CurrentMdxQuery

End Function

{% endhighlight  %}
{% endtabs %}
