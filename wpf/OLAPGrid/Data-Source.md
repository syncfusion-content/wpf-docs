---
layout: post
title: Data Source| OLAP Grid | Wpf | Syncfusion
description: data source
platform: wpf
control: OLAP Grid
documentation: ug
---

# Data Source

## Binding to OLAP Data

OlapData can be bound to OlapGrid with the help of OlapDataManager. OlapDataManager requires OlapReport which contains Dimension and Measure elements. 

Refer here for OLAP Data binding


## XAML Configuration

XAML configuration is one of the important features of OlapGrid. It helps you to configure the control entirely using XAML by eliminating the required code in code behind. 

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







![](Data-Source_images/Data-Source_img1.png)


OLAP Grid with SalesReport created by XAML code
{:.caption}

### Sample Link

To access a XAML Configuration Demo sample:

1. Open the Syncfusion Dashboard
2. Select Business Intelligence
3. Click the WPF drop-down list and select Explore Samples
4. Navigate to OlapGrid.WPF -> Samples -> Defining Reports -> XAML Configuration Demo

Or

### Navigate to:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Defining Reports\XAML Configuration Demo 

