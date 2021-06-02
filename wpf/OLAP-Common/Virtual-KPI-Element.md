---
layout: post
title: Virtual KPI Element in WPF OLAP Common control | Syncfusion
description: Learn about Virtual KPI Element support in Syncfusion WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
documentation: ug
---

# Virtual KPI Element in WPF OLAP Common

KPI can be virtually defined during runtime. This feature enables users to create KPIs without storing them in SSAS (SQL Server Analysis Services). This feature is useful when users want to define KPIs at runtime and also minimize the time necessary to create KPIs.

### Properties

* **Name**: Gets or sets the name for VirtualKpiElement.
* **KpiValueExpression**: Gets or sets the value which indicates the value expression for VirtualKpiElement.
* **KpiGoalExpression**: Gets or sets the value which indicates the goal expression for VirtualKpiElement.
* **KpiStatusExpression**: Gets or sets the value which indicates the status expression for VirtualKpiElement.
* **KpiTrendExpression**: Gets or sets the value which indicates the trend expression for VirtualKpiElement.
* **KpiTrendGraphic**: Gets or sets the name of the graphic used to represent the result of the trend expression.
* **KpiStatusGraphic**: Gets or sets the name of the graphic used to represent the result of the status expression.


### OlapReport class properties

* **VirtualKpiElements**: Gets or sets the collection of VirtualKpiElement.


## Adding virtual KPI element to the OlapReport

OLAP report definition with VirtualKpiElement

{% tabs %}
{% highlight c# %}

public OlapReport VirtualKPIReport()

{

OlapReport olapReport = new OlapReport("Virtual KPI Report");

olapReport.CurrentCubeName = "Adventure Works";

MeasureElements measureElements = new MeasureElements();

measureElements.Add(new MeasureElement { Name = "Internet Sales Amount" });

olapReport.CategoricalElements.Add(measureElements);



VirtualKpiElement virtualKPIElement = new VirtualKpiElement();

virtualKPIElement.Name = "Sample KPI";

virtualKPIElement.KpiValueExpression = ""; //Value expression

virtualKPIElement.KpiGoalExpression = ""; //Goal expression

virtualKPIElement.KpiStatusExpression = ""; //Status expression

virtualKPIElement.KpiTrendExpression = ""; //Trend expression

virtualKPIElement.StatusGraphic = ""; //Status graphic

virtualKPIElement.TrendGraphic = ""; //Trend graphic

olapReport.VirtualKpiElements.Add(virtualKPIElement);

olapReport.CategoricalElements.Add(virtualKPIElement);



DimensionElement internalDimension = new DimensionElement();

internalDimension.Name = "Product";

internalDimension.AddLevel("Product Categories", "Category");

olapReport.SeriesElements.Add(internalDimension);

return olapReport;

}




{% endhighlight %}


{% highlight vbnet %}

Public Function VirtualKPIReport() As OlapReport

Dim olapReport As New OlapReport("Virtual KPI Report")

olapReport.CurrentCubeName = "Adventure Works"

Dim measureElements As New MeasureElements()

measureElements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})

olapReport.CategoricalElements.Add(measureElements)



Dim virtualKPIElement As New VirtualKpiElement()

virtualKPIElement.Name = "Sample KPI"

virtualKPIElement.KpiValueExpression = "" 'Value expression

virtualKPIElement.KpiGoalExpression = "" 'Goal expression

virtualKPIElement.KpiStatusExpression = "" 'Status expression

virtualKPIElement.KpiTrendExpression = "" 'Trend expression

virtualKPIElement.StatusGraphic = "" 'Status graphic

virtualKPIElement.TrendGraphic = "" 'Trend graphic

olapReport.VirtualKpiElements.Add(virtualKPIElement)

olapReport.CategoricalElements.Add(virtualKPIElement)



Dim internalDimension As New DimensionElement()

internalDimension.Name = "Product"

internalDimension.AddLevel("Product Categories", "Category")

olapReport.SeriesElements.Add(internalDimension)

Return olapReport

End Function





Sample of Value, Goal, Status, and Trend expressions

[Value Expression]

           [Measures].[Reseller Sales Amount]





[Goal Expression]

           [Measures].[Sales Amount Quota]





[Status Expression]

Case

    When [Measures].[Reseller Sales Amount] / [Measures].[Sales Amount Quota] >  1

    Then 1

    When [Measures].[Reseller Sales Amount] / [Measures].[Sales Amount Quota] <= 1

         And 

         [Measures].[Reseller Sales Amount] / [Measures].[Sales Amount Quota] >= .85

    Then 0

    Else -1

End







[Trend Expression]

Case

    When IsEmpty

         (

           ParallelPeriod

           (

             [Date].[Fiscal].[Fiscal Year],

             1,

             [Date].[Fiscal].CurrentMember

           )

         )

    Then 0  

    When VBA!Abs

         (

          ( 

            [Measures].[Reseller Sales Amount] 

            - 

            (

              [Measures].[Reseller Sales Amount],

              ParallelPeriod

              ( 

                [Date].[Fiscal].[Fiscal Year],

                1,

                [Date].[Fiscal].CurrentMember

              )

            )

          ) 

          /

          (

            [Measures].[Reseller Sales Amount],

            ParallelPeriod

            ( 

              [Date].[Fiscal].[Fiscal Year],

              1,

              [Date].[Fiscal].CurrentMember

            )

          )  

         ) <=.02

    Then 0

    When ( 

           [Measures].[Reseller Sales Amount] 

           - 

           (

             [Measures].[Reseller Sales Amount],

             ParallelPeriod

             ( 

               [Date].[Fiscal].[Fiscal Year],

               1,

               [Date].[Fiscal].CurrentMember

             )

           ) 

         )

         /

         (

           [Measures].[Reseller Sales Amount],

           ParallelPeriod

           ( 

             [Date].[Fiscal].[Fiscal Year],

             1,

             [Date].[Fiscal].CurrentMember

           )

         ) >.02

    Then 1

    Else -1

End
{% endhighlight %}

{% endtabs %}


