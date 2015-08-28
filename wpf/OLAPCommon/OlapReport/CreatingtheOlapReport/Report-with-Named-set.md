---
layout: post
title: Report-with-Named-set
description: report with named set
platform: wpf
control: OLAP Common 
documentation: ug
---

# Report with Named set



{% highlight c# %}



OlapReport olapReport = new OlapReport();
olapReport.Name = "Customer Report";
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementColumn = new DimensionElement();
//Specifying the dimension Name
dimensionElementColumn.Name = "Customer";
//Specifying the Hierarchy Name
dimensionElementColumn.HierarchyName = "Customer Geography";
dimensionElementColumn.AddLevel("Customer Geography", "Country");

MeasureElements measureElementColumn = new MeasureElements();
//Specifying the measure elements
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });

//Specifying the NamedSet Element
NamedSetElement dimensionElementRow = new NamedSetElement();
//Specifying the dimension name
dimensionElementRow.Name = "Core Product Group";

///Adding the Column members
olapReport.CategoricalElements.Add(dimensionElementColumn);
///Adding the Measure elements
olapReport.CategoricalElements.Add(measureElementColumn);
///Adding the Row members
olapReport.SeriesElements.Add(dimensionElementRow);



{% endhighlight  %}

{% highlight vbnet %}



Dim olapReport As OlapReport = New OlapReport()

olapReport.Name = "Customer Report" 

olapReport.CurrentCubeName = "Adventure Works"



Dim dimensionElementColumn As DimensionElement = New DimensionElement()

'Specifying the dimension Name

dimensionElementColumn.Name = "Customer"

'Specifying the Hierarchy Name

dimensionElementColumn.HierarchyName = "Customer Geography"

dimensionElementColumn.AddLevel("Customer Geography", "Country")



Dim measureElementColumn As MeasureElements = New MeasureElements()

'Specifying the measure elements

measureElementColumn.Elements.Add(New MeasureElement With {.Name = 

                                       "Internet Sales Amount"})



'Specifying the NamedSet Element

Dim dimensionElementRow As NamedSetElement = New NamedSetElement()

'Specifying the dimension name

dimensionElementRow.Name = "Core Product Group"



'''Adding the Column members

olapReport.CategoricalElements.Add(dimensionElementColumn)

'''Adding the Measure elements

olapReport.CategoricalElements.Add(measureElementColumn)

'''Adding the Row members

olapReport.SeriesElements.Add(dimensionElementRow)


{% endhighlight  %}


