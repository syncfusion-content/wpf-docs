---
layout: post
title: Key Performance Indicator KPI| OlapGrid | Wpf | Syncfusion
description: key performance indicator (kpi)
platform: wpf
control: OlapGrid
documentation: ug
---

# Key Performance Indicator (KPI)

KPI is a collection of calculations that are associated with a measure group in a cube that are used to evaluate business success. Typically, these calculations are a combination of multi-dimensional expressions (MDX) or calculated members. KPIs also have additional metadata that provides information about how Grid applications should display the results of KPIs calculations.

The following are the different types of Indicators:

* KPI Goal
* KPI Status
* KPI Trend
* KPI Value

{% tabs %}
 
{% highlight c# %}
     
    /// <summary>
    /// OlapReport with KPI Elements
    /// </summary>
    /// <returns></returns>
    private OlapReport LoadBasicKPI()
    {
       OlapReport olapReport = new OlapReport();
       // Selecting the Cube
       olapReport.CurrentCubeName = "Adventure Works";
       KpiElements kpiElement = new KpiElements();
       // Specifying the KPI Element name and configuring its Indicators
       kpiElement.Elements.Add(new KpiElement
       {
           Name = "Internet Revenue",
           ShowKPIGoal = true,
           ShowKPIStatus = true,
           ShowKPIValue = true,
           ShowKPITrend = true
       });
       DimensionElement dimensionElementRow = new DimensionElement();
       // Specifying the Name for Row Dimension Element
       dimensionElementRow.Name = "Date";
       // Specifying the Level element
       dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
       // Adding Row Elements
       olapReport.SeriesElements.Add(dimensionElementRow);
       // Adding Column Elements
       olapReport.CategoricalElements.Add(kpiElement);
       return olapReport;
     }

{% endhighlight %}

{% highlight vbnet %}

    ''' <summary>
    ''' OlapReport with KPI Elements
    ''' </summary>
    ''' <returns></returns>
    Private Function LoadBasicKPI() As OlapReport
       Dim olapReport As New OlapReport()
       ' Selecting the Cube
       olapReport.CurrentCubeName = "Adventure Works"
       Dim kpiElement As New KpiElements()
       ' Specifying the KPI Element name and configuring its Indicators
       kpiElement.Elements.Add(New KpiElement()
       {
           Name = "Internet Revenue",
           ShowKPIGoal = true,
           ShowKPIStatus = true,
           ShowKPIValue = true,
           ShowKPITrend = true
       })
       Dim dimensionElementRow As New DimensionElement()
       ' Specifying the Name for Row Dimension Element
       dimensionElementRow.Name = "Date"
       ' Specifying the Level element
       dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
       ' Adding Row Elements
       olapReport.SeriesElements.Add(dimensionElementRow)
       ' Adding Column Elements
       olapReport.CategoricalElements.Add(kpiElement)
       Return olapReport
    End Function

{% endhighlight %}
 
{% endtabs%}

![](Key-Performance-Indicator-KPI_images/Key-Performance-Indicator-KPI_img1.png)

A sample demo is available at the following location:

[system drive]:\Users\\{User Name} \AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Product Showcase\KPI

