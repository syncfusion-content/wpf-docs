---
layout: post
title: KPI| OLAP Chart | Wpf | Syncfusion
description: KPI
platform: wpf
control: OLAP Chart
documentation: ug
---

# KPI

## Definition

Key Performance Indicator (KPI) is a collection of calculations that are associated with a measure group in a cube that are used to evaluate business success. Typically, these calculations are a combination of Multidimensional Expressions (MDX) or calculated members. KPIs also have additional metadata that provides information about how Grid applications should display the results of the KPI's calculations.

## What are the different types of Indicators available and how can it be configured?

The different types of Indicators are as follows:

* KPI Goal
* KPI Status
* KPI Trend
* KPI Value

### Sample Report


The KPI Elements can be defined in the OlapReport in the following way:


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

      kpiElement.Elements.Add(New KpiElement())



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


![](Core-Features_images/Core-Features_img38.png)
