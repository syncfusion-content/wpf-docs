---
layout: post
title: KPI in WPF Olap Grid control | Syncfusion
description: Learn about KPI support in Syncfusion Essential Studio WPF Olap Grid control, its elements and more details.
platform: wpf
control: OlapGrid
 documentation: ug
---

# KPI in WPF Olap Grid

KPI is a collection of calculations that are associated with a measure group in a cube that are used to evaluate business success. Typically, these calculations are a combination of multi-dimensional expressions (MDX) or calculated members. KPIs also have additional metadata that provides information about how grid applications should display the results of KPI calculations.

The following are the different types of indicators:

* KPI goal
* KPI status
* KPI trend
* KPI value

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
    Dim olapReport As OlapReport = New OlapReport()
    olapReport.CurrentCubeName = "Adventure Works"
    Dim kpiElement As KpiElements = New KpiElements()
    kpiElement.Elements.Add(New KpiElement With {.Name = "Internet Revenue", .ShowKPIGoal = True, .ShowKPIStatus = True, .ShowKPIValue = True, .ShowKPITrend = True})
    Dim dimensionElementRow As DimensionElement = New DimensionElement()
    dimensionElementRow.Name = "Date"
    dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
    olapReport.SeriesElements.Add(dimensionElementRow)
    olapReport.CategoricalElements.Add(kpiElement)
    Return olapReport
End Function

{% endhighlight %}
 
{% endtabs %}

![OlapGrid with KPI](Key-Performance-Indicator-KPI_images/Key-Performance-Indicator-KPI_img1.png)

A sample demo is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Product Showcase\KPI

