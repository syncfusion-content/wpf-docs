---
layout: post
title: Drill-down-report
description: drill down report
platform: wpf
control: OLAP Common 
documentation: ug
---

# Drill down report



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
measureElementColumn.Elements.Add(new MeasureElement { Name = 

                                 "Internet Sales Amount" });

DimensionElement dimensionElementRow = new DimensionElement();
//Specifying the Dimension Name
dimensionElementRow.Name = "Date";
dimensionElementRow.HierarchyName = "Fiscal";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2002");
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

                             MemberElements[0].ShowChildMembers = true;
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

                             MemberElements[0].Add("H1 FY 2002");
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

      MemberElements[0].ChildMemberElements[0].ShowChildMembers = true;
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

MemberElements[0].ChildMemberElements[0].Add("Q1 FY 2002");
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

MemberElements[0].ChildMemberElements[0].

ChildMemberElements[0].ShowChildMembers = true;
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

MemberElements[0].ChildMemberElements[0].

ChildMemberElements[0].Add("July 2001");
dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].

MemberElements[0].ChildMemberElements[0].

ChildMemberElements[0].ChildMemberElements[0].ShowChildMembers = true;

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

Dim olapReport As OlapReport = New OlapReport()

olapReport.CurrentCubeName = "Adventure Works"

Dim dimensionElementColumn As DimensionElement = New DimensionElement()

'Specifying the Name for the Dimension Element

dimensionElementColumn.Name = "Customer"

'Specifying the Hierarchy Name

dimensionElementColumn.HierarchyName = "Customer Geography"

Dim olapReport As OlapReport = New OlapReport()

olapReport.CurrentCubeName = "Adventure Works"

Dim dimensionElementColumn As DimensionElement = New DimensionElement()

'Specifying the Name for the Dimension Element

dimensionElementColumn.Name = "Customer"

'Specifying the Hierarchy Name

dimensionElementColumn.HierarchyName = "Customer Geography"

dimensionElementColumn.AddLevel("Customer Geography", "Country")



Dim measureElementColumn As MeasureElements = New MeasureElements()

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})



Dim dimensionElementRow As DimensionElement = New DimensionElement()

'Specifying the Dimension Name

dimensionElementRow.Name = "Date"

dimensionElementRow.HierarchyName = "Fiscal"

dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year").Add("FY 2002")

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ShowChildMembers = True

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).Add("H1 FY 2002")

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ChildMemberElements(0).ShowChildMembers = True

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ChildMemberElements(0).Add("Q1 FY 2002")

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ChildMemberElements(0). ChildMemberElements(0).ShowChildMembers = True

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ChildMemberElements(0). ChildMemberElements(0).Add("July 2001")

dimensionElementRow.Hierarchy.LevelElements("Fiscal Year"). MemberElements(0).ChildMemberElements(0). ChildMemberElements(0).ChildMemberElements(0).ShowChildMembers = True


{% endhighlight  %}








