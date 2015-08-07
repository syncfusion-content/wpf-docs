---
layout: post
title: XAML-Configuration
description: xaml configuration
platform: wpf
control: OLAP Grid
documentation: ug
---

# XAML Configuration

XAML configuration is one of the important features of OlapGrid. It helps you to configure the control entirely using XAML by eliminating the required code in code behind. 



## Use Case Scenarios

This feature will help you to set the Data source, Report and UI properties in a simple and elegant manner, when you want to perform the entire configuration in XAML.

## Property

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data  Type**' | markdownify }}</td><td>
{{ '**Reference Link**' | markdownify }}</td></tr>
<tr>
<td>
DataSource.ConnectionString</td><td>
Specifies the connection string of the DataManager</td><td>
Attached Property</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
DataSource.ConnectionName</td><td>
Specifies the connection name which is available in App.Config file of the application</td><td>
Attached Property</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
DataSource.DataManagerName</td><td>
Specifies the DataManager name</td><td>
Attached Property</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
SharedDataManagerName</td><td>
Specifies the DataManager name which is available in shared data manager collection</td><td>
Attached Property</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
ReportName</td><td>
Species the OLAP report name</td><td>
CLR</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
CurrentCubeName</td><td>
Specifies the current cube name of a OLAP report</td><td>
CLR</td><td>
String</td><td>
-</td></tr>
<tr>
<td>
CategoricalAxis</td><td>
Specifies the Categorical axis of the OLAP report</td><td>
Dependency Property</td><td>
CategoricalAxis</td><td>
-</td></tr>
<tr>
<td>
SeriesAxis</td><td>
Specifies the Series axis of the OLAP report</td><td>
Dependency Property</td><td>
SeriesAxis</td><td>
-</td></tr>
<tr>
<td>
SlicerAxis</td><td>
Specifies the Slicer axis of the OLAP report</td><td>
Dependency Property</td><td>
SlicerAxis</td><td>
-</td></tr>
<tr>
<td>
CalculatedMembers</td><td>
Specifies the Calculated Members of the OLAP report</td><td>
Dependency Property</td><td>
CalculatedMembers</td><td>
-</td></tr>
</table>


## Adding report to OLAP Grid

Adding an OLAP report to OLAP Grid control in design time is described in the following code snippet:

  {% highlight xml %}

   [XAML]



<syncfusion:OlapGrid x:Name="olapGrid" 

                      HorizontalAlignment="Stretch"

                      ReportName="SalesReport"

                      CurrentCubeName="Adventure Works" 

                      SharedDataManagerName="localManager"

                      olapshared:DataSource.DataManagerName="localManager"

olapshared:DataSource.ConnectionString="datasource=localhost; initial catalog=adventure works dw">



<!- Adding Elements to Categorical Axis -->

<syncfusion:OlapGrid.CategoricalAxis>

                    <syncfusion:Dimension Name="Date" HierarchyName="Fiscal" LevelName="Fiscal Year" IncludeMembers="FY 2002, FY 2003"  />   <!- Multiple Members where specified by comma separate -->                 

                    <syncfusion:Kpi Name="Revenue" ShowGoal="True" ShowStatus="True" ShowValue="True" ShowTrend="True" />

</syncfusion:OlapGrid.CategoricalAxis>



<!- Adding Elements to Series Axis -->

<syncfusion:OlapGrid.SeriesAxis>

                    <syncfusion:Dimension Name="Sales Channel" HierarchyName="Sales Channel" LevelName="Sales Channel" />

                    <syncfusion:Dimension Name="Product" HierarchyName="Product Model Lines" LevelName="Product Line" IncludeMembers="Road" />

</syncfusion:OlapGrid.SeriesAxis>



</syncfusion:OlapGrid>

    {% endhighlight %}







![](XAML-Configuration_images/XAML-Configuration_img1.png)

_OLAP Grid with SalesReport created by XAML code_



## Sample Link

To access a XAML Configuration Demo sample:

1. Open the Syncfusion Dashboard.
2. Select Business Intelligence.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to OlapGrid.WPF -> Samples -> Defining Reports -> XAML Configuration Demo.

Or

Navigate to:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Defining Reports\XAML Configuration Demo 

