---
layout: post
title: Key-Performance-Indicator-KPI-Element
description: key performance indicator (kpi) element
platform: wpf
control: OLAP Common
documentation: ug
---

# Key Performance Indicator (KPI) Element

Key Performance Indicator (KPI) is a collection of calculations that are associated with a measure group in a cube that are used to evaluate business success. Typically, these calculations are a combination of Multidimensional Expressions (MDX) or calculated members. The KPIs also have an additional metadata that provides information about how client applications should display the results of the KPI's calculations.

## The different types of KPI Indicators are:

* KPI Goal
* KPI Status
* KPI Trend
* KPI Value

We can create a KPI element by specifying its name and giving details of the indicator that are included in the element. 

{% highlight c# %}

KpiElements kpiElement = new KpiElements();

// Specifying the KPI Element name and configuring its Indicators

kpiElement.Elements.Add(new KpiElement { Name = "Internet Revenue",  

ShowKPIGoal = true, ShowKPIStatus = true, ShowKPIValue = true, 

ShowKPITrend = true });

{% endhighlight  %}

{% highlight vbnet %}

Dim kpiElement As KpiElements = New KpiElements()

' Specifying the KPI Element name and configuring its Indicators

kpiElement.Elements.Add(New KpiElement With {.Name =  

"Internet Revenue", .ShowKPIGoal = True, .ShowKPIStatus = True, 

 .ShowKPIValue = True, .ShowKPITrend = True})

{% endhighlight  %}

