---
layout: post
title: XAML Configuration in WPF Olap Chart control | Syncfusion
description: Learn about XAML Configuration support in Syncfusion WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
 documentation: ug
---

# XAML Configuration in WPF Olap Chart

XAML configuration is one of the important features of the OLAP chart, as it helps users to configure the control entirely through XAML by eliminating the required code in code behind. 

### Properties 
* **DataSource.ConnectionString**: Specifies the connection string of the data manager.
* **DataSource.ConnectionName**: Specifies the connection name, which is available in the App.Config file of the application.
* **DataSource.DataManagerName**: Specifies the data manager name.
* **SharedDataManagerName**: Specifies the data manager name, which is available in the shared data manager collection.
* **ReportName**: Specifies the OLAP report name.
* **CurrentCubeName**: Specifies the current cube name of an OLAP report.
* **CategoricalAxis**: Specifies the categorical axis of the OLAP report.
* **SeriesAxis**: Specifies the series axis of the OLAP report.
* **SlicerAxis**: Specifies the slicer axis of the OLAP report.
* **CalculatedMembers**: Specifies the calculated members of the OLAP report.

Adding an OLAP report to the OLAP chart in design time is described in the following code sample.

{% highlight xaml %}

<syncfusion:OlapChart x:Name="olapChart" HorizontalAlignment="Stretch" ReportName="SalesReport"
		CurrentCubeName="Adventure Works" SharedDataManagerName="localManager"
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

{% endhighlight %}
 
![XAML-Configuration_img1](XAML-Configuration_images/XAML-Configuration_img1.png)

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Defining Reports\ XAML Configuration Demo

