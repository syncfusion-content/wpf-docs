---
layout: post
title: Bind an OlapReport with OlapDataManager| OLAPCommon | Wpf | Syncfusion
description: bind an olapreport with olapdatamanager
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Bind an OlapReport with OlapDataManager

Once the connection is established, you can create and bind the OlapReport to the manger by using any one of the following property and methods:

### Property

1. CurrentReport

### Methods

1. SetCurrentReport
2. LoadOlapDataManager
3. LoadReportDefinitionFile
4. LoadReportDefinitionFromStream  

### Methods for Silverlight

1. SetCurrentReport
2. LoadReportFromStream



The following code snippet will illustrate the binding of OlapReport using these methods with a sample OlapReport:

## Sample OlapReport

{% tabs %}

{% highlight c# %}

OlapDataManager OlapDataManager = new OlapDataManager

(@"DataSource=localhost; Initial Catalog=Adventure Works DW");

OlapReport olapReport = new OlapReport();

olapReport.Name = "Customer Report";
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementColumn = new DimensionElement();
//Specifying the Name for the Dimension Element
dimensionElementColumn.Name = "Customer";
dimensionElementColumn.AddLevel("Customer Geography", "Country");

MeasureElements measureElementColumn = new MeasureElements();
//Specifying the Name for the Measure Element
measureElementColumn.Elements.Add(new MeasureElement 

{ Name = "Internet Sales Amount" });

DimensionElement dimensionElementRow = new DimensionElement();
//Specifying the Dimension Name
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

///Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn);
///Adding Measure Element
olapReport.CategoricalElements.Add(measureElementColumn);
///Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight  %}

{% highlight vbnet %}



Dim OlapDataManager As OlapDataManager = New OlapDataManager                  ("DataSource=localhost; Initial Catalog=Adventure Works DW") Dim olapReport1 As OlapReport = New OlapReport()

olapReport.Name = "Customer Report"
olapReport1.CurrentCubeName = "Adventure Works" 
Dim dimensionElementColumn As DimensionElement = 

New DimensionElement()
'Specifying the Name for the Dimension Element
dimensionElementColumn.Name = "Customer"
dimensionElementColumn.AddLevel("Customer Geography", "Country")

Dim measureElementColumn As MeasureElements = New MeasureElements()
'Specifying the Name for the Measure Element

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})

Dim dimensionElementRow As DimensionElement = New DimensionElement()
'Specifying the Dimension Name
dimensionElementRow.Name = "Date"
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")

'Adding Column Members
olapReport1.CategoricalElements.Add(dimensionElementColumn)
'Adding Measure Element

olapReport1.CategoricalElements.Add(measureElementColumn)
'Adding Row Members
olapReport1.SeriesElements.Add(dimensionElementRow)

{% endhighlight  %}
{% endtabs %}
