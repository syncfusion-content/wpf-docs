---
layout: post
title: Ordered-Report
description: ordered report
platform: wpf
control: OLAP Common 
documentation: ug
---

# Ordered Report



{% highlight c# %}



OlapReport olapReport = new OlapReport();
olapReport.Name = "Customer Report";
olapReport.CurrentCubeName = "Adventure Works";
DimensionElement dimensionElementColumn = new DimensionElement();

//Specifying the Name for the Dimension Element
dimensionElementColumn.Name = "Customer";
//Specifying the Hierarchy Name
dimensionElementColumn.HierarchyName = "Customer Geography";
dimensionElementColumn.AddLevel("Customer Geography", "Country");

//Creating Measure Elements
MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
DimensionElement dimensionElementRow = new DimensionElement();

//Specifying the Dimension Name
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

SortElement sortElement = new SortElement(AxisPosition.Categorical, SortOrder.BDESC, true);
sortElement.Element.UniqueName = "[Measures].[Internet Sales Amount]";

///Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn);
///Adding Measure Element
olapReport.CategoricalElements.Add(measureElementColumn);
//Adding Sort Element
olapReport.CategoricalElements.Add(sortElement);
///Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow);



{% endhighlight  %}



{% highlight vbnet %}


Dim olapReport As OlapReport = New OlapReport()

olapReport.Name = "Customer Report"

olapReport.CurrentCubeName = "Adventure Works"

Dim dimensionElementColumn As DimensionElement = New DimensionElement()



'Specifying the Name for the Dimension Element

dimensionElementColumn.Name = "Customer"

'Specifying the Hierarchy Name

dimensionElementColumn.HierarchyName = "Customer Geography"

dimensionElementColumn.AddLevel("Customer Geography", "Country")



'Creating Measure Elements

Dim measureElementColumn As MeasureElements = New MeasureElements()

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})

Dim dimensionElementRow As DimensionElement = New DimensionElement()



'Specifying the Dimension Name

dimensionElementRow.Name = "Date"

dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")



Dim sortElement As SortElement = New SortElement(AxisPosition.Categorical, SortOrder.BDESC, True)

sortElement.Element.UniqueName = "[Measures].[Internet Sales Amount]"



'''Adding Column Members

olapReport.CategoricalElements.Add(dimensionElementColumn)

'''Adding Measure Element

olapReport.CategoricalElements.Add(measureElementColumn)

'Adding Sort Element

olapReport.CategoricalElements.Add(sortElement)

'''Adding Row Members

olapReport.SeriesElements.Add(dimensionElementRow)





{% endhighlight  %}
