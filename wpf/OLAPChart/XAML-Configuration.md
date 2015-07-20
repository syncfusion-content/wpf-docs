---
layout: post
title: XAML-Configuration
description: xaml configuration
platform: wpf
control: OLAP Chart
documentation: ug
---

# XAML Configuration

XAML configuration is an important feature of OlapChart, as it helps the user to configure the control entirely using XAML by eliminating the need code in code behind. 

Use Case Scenarios

If a user wants to perform an entire configuration in XAML, then this feature will help the user to set the Data source, Report and UI properties in a simple and elegant manner by using XAML.

Property

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td></tr>
<tr>
<td>
DataSource.ConnectionString</td><td>
Specifies the connection string of the data manager</td><td>
Attached Property</td><td>
String</td></tr>
<tr>
<td>
DataSource.ConnectionName</td><td>
Specifies the connection name which is available in App.Config file of the application</td><td>
Attached Property</td><td>
String</td></tr>
<tr>
<td>
DataSource.DataManagerName</td><td>
Specifies the DataManagerName</td><td>
Attached Property</td><td>
String</td></tr>
<tr>
<td>
SharedDataManagerName</td><td>
Specifies the data manager name which is available in shared data manager collection</td><td>
Attached Property</td><td>
String</td></tr>
<tr>
<td>
ReportName</td><td>
Species the OLAP ReportName</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
CurrentCubeName</td><td>
Specifies the CurrentCube Name of a OLAP report</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
CategoricalAxis</td><td>
Specifies the CategoricalAxis of the OLAP report</td><td>
Dependency Property</td><td>
CategoricalAxis</td></tr>
<tr>
<td>
SeriesAxis</td><td>
Specifies the SeriesAxis of the OLAP report</td><td>
Dependency Property</td><td>
SeriesAxis</td></tr>
<tr>
<td>
SlicerAxis</td><td>
Specifies the SlicerAxis of the OLAP report</td><td>
Dependency Property</td><td>
SlicerAxis</td></tr>
<tr>
<td>
CalculatedMembers</td><td>
Specifies the CalculatedMembers of the OLAP report</td><td>
Dependency Property</td><td>
CalculatedMembers</td></tr>
</table>


Adding report to OLAP Chart

Adding an OLAP report to OLAP Chart control in design time is described in the following code snippet:

[XAML]



<syncfusion:OlapChart x:Name="olapChart" 

                      HorizontalAlignment="Stretch"

                      ReportName="SalesReport"

                      CurrentCubeName="Adventure Works" 

                      SharedDataManagerName="localManager"

                      olapshared:DataSource.DataManagerName="localManager"

olapshared:DataSource.ConnectionString="datasource=localhost; initial catalog=adventure works dw">



<!- Adding Elements to Categorical Axis -->

<syncfusion:OlapChart.CategoricalAxis>

                    <syncfusion:Dimension Name="Date" HierarchyName="Fiscal" LevelName="Fiscal Year" IncludeMembers="FY 2002, FY 2003"  />   <!- Multiple Members where specified by comma separate -->                 

                    <syncfusion:Kpi Name="Revenue" ShowGoal="True" ShowStatus="True" ShowValue="True" ShowTrend="True" />

</syncfusion:OlapChart.CategoricalAxis>



<!- Adding Elements to Series Axis -->

<syncfusion:OlapChart.SeriesAxis>

                    <syncfusion:Dimension Name="Sales Channel" HierarchyName="Sales Channel" LevelName="Sales Channel" />

                    <syncfusion:Dimension Name="Product" HierarchyName="Product Model Lines" LevelName="Product Line" IncludeMembers="Road" />

</syncfusion:OlapChart.SeriesAxis>



</syncfusion:OlapChart>





Sample Link

To access a XAML Configuration Demo sample:

1. Open the Syncfusion Dashboard
2. Select Business Intelligence
3. Click the WPF drop-down list and select Explore Samples
4. Navigate to OlapChart.WPF -> Samples -> Defining Reports -> XAML Configuration Demo



{{ '![](XAML-Configuration_images/XAML-Configuration_img1.png)' | markdownify }}
{:.image }


_OLAP Chart with SalesReport created using XAML code_

