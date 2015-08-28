---
layout: post
title: Report-with-dicing-operation
description: report with dicing operation
platform: wpf
control: OLAP Common 
documentation: ug
---

# Report with dicing operation



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

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });

DimensionElement dimensionElementRow = new DimensionElement();
//Specifying the Dimension Name
dimensionElementRow.Name = "Date";
dimensionElementRow.HierarchyName = "Fiscal";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

//Specifying Excluded column elements
DimensionElement excludedColumnElement = new DimensionElement();
excludedColumnElement.Name = "Customer";
excludedColumnElement.HierarchyName = "Customer Geography";
excludedColumnElement.AddLevel("Customer Geography", "Country");
excludedColumnElement.Hierarchy.LevelElements["Country"].Add("Canada");
excludedColumnElement.Hierarchy.LevelElements["Country"].Add("France");
excludedColumnElement.Hierarchy.LevelElements["Country"].Add("United Kingdom");
excludedColumnElement.Hierarchy.LevelElements["Country"].Add("United States");


//Spefifying the Excluded row elements
DimensionElement excludedRowElement = new DimensionElement();
excludedRowElement.Name = "Date";
excludedRowElement.AddLevel("Fiscal", "Fiscal Year");
excludedRowElement.AddLevel("Fiscal", "Month");
excludedRowElement.AddLevel("Fiscal", "Fiscal Quarter");
excludedRowElement.AddLevel("Fiscal", "Fiscal Semester");
excludedRowElement.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2002");
excludedRowElement.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2004");
excludedRowElement.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2005");
excludedRowElement.Hierarchy.LevelElements["Fiscal Semester"].Add("H2 FY 2003");
excludedRowElement.Hierarchy.LevelElements["Month"].Add("August 2002");
excludedRowElement.Hierarchy.LevelElements["Month"].Add("September 2002");
excludedRowElement.Hierarchy.LevelElements["Fiscal Quarter"].Add("Q2 FY 2003");
excludedRowElement.Hierarchy.LevelElements["Fiscal Quarter"].Add("Q2 FY 2003");

///Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn,excludedColumnElement);
///Adding Measure Element
olapReport.CategoricalElements.Add(measureElementColumn);
///Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow,excludedRowElement);

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



Dim measureElementColumn As MeasureElements = New MeasureElements()

measureElementColumn.Elements.Add(New MeasureElement { Name = "Internet Sales Amount" });

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})



Dim dimensionElementRow As DimensionElement = New DimensionElement()

'Specifying the Dimension Name

dimensionElementRow.Name = "Date"

dimensionElementRow.HierarchyName = "Fiscal"

dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")



'Specifying Excluded column elements

Dim excludedColumnElement As DimensionElement = New DimensionElement()

excludedColumnElement.Name = "Customer"

excludedColumnElement.HierarchyName = "Customer Geography"

excludedColumnElement.AddLevel("Customer Geography", "Country")

excludedColumnElement.Hierarchy.LevelElements("Country").Add("Canada")

excludedColumnElement.Hierarchy.LevelElements("Country").Add("France")

excludedColumnElement.Hierarchy.LevelElements("Country").Add("United Kingdom")

excludedColumnElement.Hierarchy.LevelElements("Country").Add("United States")





'Spefifying the Excluded row elements

Dim excludedRowElement As DimensionElement = New DimensionElement()

excludedRowElement.Name = "Date"

excludedRowElement.AddLevel("Fiscal", "Fiscal Year")

excludedRowElement.AddLevel("Fiscal", "Month")

excludedRowElement.AddLevel("Fiscal", "Fiscal Quarter")

excludedRowElement.AddLevel("Fiscal", "Fiscal Semester")

excludedRowElement.Hierarchy.LevelElements("Fiscal Year").Add("FY 2002")

excludedRowElement.Hierarchy.LevelElements("Fiscal Year").Add("FY 2004")

excludedRowElement.Hierarchy.LevelElements("Fiscal Year").Add("FY 2005")

excludedRowElement.Hierarchy.LevelElements("Fiscal Semester").Add("H2 FY 2003")

excludedRowElement.Hierarchy.LevelElements("Month").Add("August 2002")

excludedRowElement.Hierarchy.LevelElements("Month").Add("September 2002")

excludedRowElement.Hierarchy.LevelElements("Fiscal Quarter").Add("Q2 FY 2003")

excludedRowElement.Hierarchy.LevelElements("Fiscal Quarter").Add("Q2 FY 2003")



'''Adding Column Members

olapReport.CategoricalElements.Add(dimensionElementColumn,excludedColumnElement)

'''Adding Measure Element

olapReport.CategoricalElements.Add(measureElementColumn)

'''Adding Row Members

olapReport.SeriesElements.Add(dimensionElementRow,excludedRowElement)









{% endhighlight  %}








