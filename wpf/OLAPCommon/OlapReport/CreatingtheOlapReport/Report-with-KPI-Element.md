---
layout: post
title: Report-with-KPI-Element
description: report with kpi element
platform: wpf
control: OLAP Common 
documentation: ug
---

# Report with KPI Element



{% highlight c# %}



OlapReport olapReport = new OlapReport();
olapReport.Name = "Products Sales Report";
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementColumn = new DimensionElement();
// Specifying the name for Dimension Element for Column
dimensionElementColumn.Name = "Product";
dimensionElementColumn.AddLevel("Product Categories", "Category");
dimensionElementColumn.Hierarchy.LevelElements["Category"].Add(this.productName);
dimensionElementColumn.Hierarchy.LevelElements["Category"].IncludeAvailableMembers = true;

MeasureElements measureElementColumn = new MeasureElements();
// Specifying the name for Measure Element
measureElementColumn.Elements.Add(new MeasureElement { Name = "Gross Profit" });

DimensionElement dimensionElementRow = new DimensionElement();
// Specifying the Name for Row Dimension Element
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

KpiElements kpiElement = new KpiElements();
kpiElement.Elements.Add(new KpiElement { Name = "Revenue", ShowKPIStatus = true, ShowKPIGoal = false, ShowKPITrend = true, ShowKPIValue = true });

// Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn);
olapReport.CategoricalElements.Add(kpiElement);
// Adding Measure Elements
olapReport.CategoricalElements.Add(measureElementColumn);
// Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow);


{% endhighlight  %}




{% highlight vbnet %}



Dim olapReport As OlapReport = New OlapReport()

olapReport.Name = "Products Sales Report"

olapReport.CurrentCubeName = "Adventure Works"



Dim dimensionElementColumn As DimensionElement = New DimensionElement()

' Specifying the name for Dimension Element for Column

dimensionElementColumn.Name = "Product"

dimensionElementColumn.AddLevel("Product Categories", "Category")

dimensionElementColumn.Hierarchy.LevelElements("Category").Add(Me.productName)

dimensionElementColumn.Hierarchy.LevelElements("Category").IncludeAvailableMembers = True



Dim measureElementColumn As MeasureElements = New MeasureElements()

' Specifying the name for Measure Element

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Gross Profit"})



Dim dimensionElementRow As DimensionElement = New DimensionElement()

' Specifying the Name for Row Dimension Element

dimensionElementRow.Name = "Date"

dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")



Dim kpiElement As KpiElements = New KpiElements()

kpiElement.Elements.Add(New KpiElement With {.Name = "Revenue", .ShowKPIStatus = True, .ShowKPIGoal = False, .ShowKPITrend = True, .ShowKPIValue = True})



' Adding Column Members

olapReport.CategoricalElements.Add(dimensionElementColumn)

olapReport.CategoricalElements.Add(kpiElement)

' Adding Measure Elements

olapReport.CategoricalElements.Add(measureElementColumn)

' Adding Row Members

olapReport.SeriesElements.Add(dimensionElementRow)








{% endhighlight  %}










