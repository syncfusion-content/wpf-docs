---
layout: post
title: XAML Configuration| OlapGrid | Wpf | Syncfusion
description: xaml configuration
platform: wpf
control: OlapGrid
documentation: ug
---

# XAML Configuration

XAML configuration is one of the important features of OlapGrid, as it helps the user to configure the control entirely through XAML by eliminating the required code in code behind. 

### Properties 

* **DataSource.ConnectionString** - Specifies the connection string of the data manager.
* **DataSource.ConnectionName** - Specifies the connection name, which is available in App.Config file of the application.
* **DataSource.DataManagerName** - Specifies the data manager name.
* **SharedDataManagerName** - Specifies the data manager name, which is available in shared data manager collection.
* **ReportName** - Specifies the OlapReport name.
* **CurrentCubeName** - Specifies the current cube name of a OlapReport.
* **CategoricalAxis** - Specifies the categorical axis of the OlapReport.
* **SeriesAxis** - Specifies the series axis of the OlapReport.
* **SlicerAxis** - Specifies the slicer axis of the OlapReport.
* **CalculatedMembers** - Specifies the calculated members of the OlapReport.

Adding an OlapReport to OlapGrid in design time is described in the following code sample:

{% highlight xaml %}

<syncfusion:OlapGrid x:Name="olapGrid" 
    HorizontalAlignment="Stretch"
    ReportName="SalesReport"
    CurrentCubeName="Adventure Works" 
    SharedDataManagerName="localManager"
    olapshared:DataSource.DataManagerName="localManager"
	olapshared:DataSource.ConnectionString="datasource=localhost; initial catalog=adventure works dw">
    <!- Adding Elements to Categorical Axis -->
<syncfusion:OlapGrid.CategoricalAxis>
     <syncfusion:Dimension Name="Date" HierarchyName="Fiscal" LevelName="Fiscal Year" IncludeMembers="FY 2002, FY 2003"  /><!- Multiple members where specified by comma separate -->                 
     <syncfusion:Kpi Name="Revenue" ShowGoal="True" ShowStatus="True" ShowValue="True" ShowTrend="True" />
</syncfusion:OlapGrid.CategoricalAxis>
    <!- Adding Elements to Series Axis -->
<syncfusion:OlapGrid.SeriesAxis>
     <syncfusion:Dimension Name="Sales Channel" HierarchyName="Sales Channel" LevelName="Sales Channel" />
     <syncfusion:Dimension Name="Product" HierarchyName="Product Model Lines" LevelName="Product Line" IncludeMembers="Road" />
</syncfusion:OlapGrid.SeriesAxis>
</syncfusion:OlapGrid>

{% endhighlight %}

Run the application and the following output will be generated.

![](XAML-Configuration_images/XAML-Configuration_img1.png)

A sample demo is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Defining Reports\XAML Configuration 

