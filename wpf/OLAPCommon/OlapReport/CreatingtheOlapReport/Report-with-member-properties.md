---
layout: post
title: Report-with-member-properties
description: report with member properties
platform: wpf
control: OLAP Common 
documentation: ug
---

# Report with member properties



{% highlight c# %}



OlapReport olapReport = new OlapReport();
olapReport.Name = "Employee Sales Report";
// Specifying the current cube name
olapReport.CurrentCubeName = "Adventure Works";

MeasureElements measureElementColumn = new MeasureElements();
// Specifying the Name for the Measure Element
measureElementColumn.Elements.Add(new MeasureElement { Name = 

                                                   "Sales Amount Quota" });

DimensionElement dimensionElementRow = new DimensionElement();
// Specifying the Dimension Name
dimensionElementRow.Name = "Employee";
// Specifying the Hierarchy and level name for the Dimension Element
dimensionElementRow.AddLevel("Employees", "Employee Level 02");
dimensionElementRow.Hierarchy.LevelElements["Employee Level 02"].

                                    IncludeAvailableMembers = true;


// Adding the Member properties to the Dimension Element
dimensionElementRow.MemberProperties.Add(new MemberProperty("Title", 

                                       "[Employee].[Employees].[Title]"));
dimensionElementRow.MemberProperties.Add(new MemberProperty("Phone", 

                                       "[Employee].[Employees].[Phone]"));
dimensionElementRow.MemberProperties.Add(new MemberProperty("Email Address", 

                                    "[Employee].[Employees].[Email Address]"));

DimensionElement dimensionElementColumn = new DimensionElement();
// Specifying the Dimension Name
dimensionElementColumn.Name = "Product";
// Specifying the Hierarchy and level name for the Dimension Element
dimensionElementColumn.AddLevel("Product Categories", "Category");
dimensionElementColumn.MemberProperties.Add(new MemberProperty("Dealer Price", "[Product].[Product Categories].[Dealer Price]"));
dimensionElementColumn.MemberProperties.Add(new MemberProperty("Standard Cost", "[Product].[Product Categories].[Standard Cost]"));

// Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow);

///Adding Column Members
olapReport.CategoricalElements.Add(measureElementColumn);



{% endhighlight  %}





{% highlight vbnet %}



Dim olapReport As OlapReport = New OlapReport()

olapReport.Name = "Employee Sales Report"

' Specifying the current cube name

olapReport.CurrentCubeName = "Adventure Works"



Dim measureElementColumn As MeasureElements = New MeasureElements()

' Specifying the Name for the Measure Element

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Sales Amount Quota"})



Dim dimensionElementRow As DimensionElement = New DimensionElement()

' Specifying the Dimension Name

dimensionElementRow.Name = "Employee"

' Specifying the Hierarchy and level name for the Dimension Element

dimensionElementRow.AddLevel("Employees", "Employee Level 02")

dimensionElementRow.Hierarchy.LevelElements("Employee Level 02"). IncludeAvailableMembers = True





' Adding the Member properties to the Dimension Element

dimensionElementRow.MemberProperties.Add(New MemberProperty("Title", "[Employee].[Employees].[Title]"))

dimensionElementRow.MemberProperties.Add(New MemberProperty("Phone", "[Employee].[Employees].[Phone]"))

dimensionElementRow.MemberProperties.Add(New MemberProperty("Email Address", "[Employee].[Employees].[Email Address]"))



Dim dimensionElementColumn As DimensionElement = New DimensionElement()

' Specifying the Dimension Name

dimensionElementColumn.Name = "Product"

' Specifying the Hierarchy and level name for the Dimension Element

dimensionElementColumn.AddLevel("Product Categories", "Category")

dimensionElementColumn.MemberProperties.Add(New MemberProperty("Dealer Price", "[Product].[Product Categories].[Dealer Price]"))

dimensionElementColumn.MemberProperties.Add(New MemberProperty("Standard Cost", "[Product].[Product Categories].[Standard Cost]"))



' Adding Row Members

olapReport.SeriesElements.Add(dimensionElementRow)



'''Adding Column Members

olapReport.CategoricalElements.Add(measureElementColumn)



{% endhighlight  %}



