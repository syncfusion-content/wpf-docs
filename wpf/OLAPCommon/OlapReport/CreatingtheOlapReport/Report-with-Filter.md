---
layout: post
title: Report-with-Filter
description: report with filter
platform: wpf
control: OLAP Common 
documentation: ug
---

# Report with Filter



{% highlight c# %}



OlapReport olapReport = new OlapReport();

olapReport.Name = "Customer Report";
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementColumn = new DimensionElement();
//Specifying the Name for the Dimension Element
dimensionElementColumn.Name = "Customer";
dimensionElementColumn.AddLevel("Customer Geography", "Country");

//Creating Measure Element
MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name =                                        "Internet Sales Amount" });

DimensionElement dimensionElementRow = new DimensionElement();
//Specifying the Dimension Name
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

FilterElement filterElement = new FilterElement(AxisPosition.Categorical);
filterElement.Elements.Add(measureElementColumn);
filterElement.Elements.Add(dimensionElementColumn);
filterElement.FilterCase = FilterCase.GreaterThan;
filterElement.FilterValue.Add(new MeasureElement { Name = 

                                  "Internet Sales Amount", Visible = true });
filterElement.FilterValue.Add(new FilterValue { Filter_Value = 2700000.00 });
filterElement.IsFilterCondition = true;
/// Adding Column Members
olapReport.CategoricalElements.Add(new Item { ElementValue = 

dimensionElementColumn });
olapReport.CategoricalElements.IsFilterOrSortOn = true;
olapReport.FilterElements.Add(new Item { ElementValue = filterElement });

olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight  %}



{% highlight vbnet %}


Dim olapReport As OlapReport = New OlapReport()

olapReport.Name = "Customer Report"

olapReport.CurrentCubeName = "Adventure Works"



Dim dimensionElementColumn As DimensionElement = New DimensionElement()

'Specifying the Name for the Dimension Element

dimensionElementColumn.Name = "Customer"

dimensionElementColumn.AddLevel("Customer Geography", "Country")



'Creating Measure Element

Dim measureElementColumn As MeasureElements = New MeasureElements()

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})



Dim dimensionElementRow As DimensionElement = New DimensionElement()

'Specifying the Dimension Name

dimensionElementRow.Name = "Date"

dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")



Dim filterElement As FilterElement = New FilterElement(AxisPosition.Categorical)

filterElement.Elements.Add(measureElementColumn)

filterElement.Elements.Add(dimensionElementColumn)

filterElement.FilterCase = FilterCase.GreaterThan



filterElement.FilterValue.Add(New MeasureElement With {.Name = "Internet Sales Amount", .Visible = True})



filterElement.FilterValue.Add(New FilterValue With {.Filter_Value = 2700000.00})

filterElement.IsFilterCondition = True

olapReport.CategoricalElements.Add(New Item With {.ElementValue = dimensionElementColumn})

olapReport.CategoricalElements.IsFilterOrSortOn = True

olapReport.FilterElements.Add(New Item With {.ElementValue = filterElement})


{% endhighlight  %}


