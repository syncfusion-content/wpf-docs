---
layout: post
title: XAML Configuration| OLAP Grid | Wpf | Syncfusion
description: xaml configuration
platform: wpf
control: OLAP Grid
documentation: ug
---

# XAML Configuration

XAML configuration is one of the important features of OlapGrid. It helps you to configure the control entirely using XAML by eliminating the required code in code behind. 


### Property 

* **DataSource.ConnectionString** - Specifies the connection string of the DataManager
* **DataSource.ConnectionName** - Specifies the connection name which is available in App.Config file of the application
* **DataSource.DataManagerName** - Specifies the DataManager name
* **SharedDataManagerName** - Specifies the DataManager name which is available in shared data manager collection
* **ReportName** - Species the OLAP report name
* **CurrentCubeName** - Specifies the current cube name of a OLAP report
* **CategoricalAxis** - Specifies the Categorical axis of the OLAP report
* **SeriesAxis** - Specifies the Series axis of the OLAP report
* **SlicerAxis** - Specifies the Slicer axis of the OLAP report
* **CalculatedMembers** - Specifies the Calculated Members of the OLAP report


## Adding report to OLAP Grid

Adding an OLAP report to OLAP Grid control in design time is described in the following code snippet:

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

OLAP Grid with SalesReport created by XAML code
{:.caption}



### Sample Link

To access a XAML Configuration Demo sample:

1. Open the Syncfusion Dashboard.
2. Select Business Intelligence.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to OlapGrid.WPF -> Samples -> Defining Reports -> XAML Configuration Demo.

Or

### Navigate to:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Defining Reports\XAML Configuration Demo 

