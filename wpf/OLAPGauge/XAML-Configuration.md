---
layout: post
title: XAML Configuration | OLAPGauge | wpf | Syncfusion
description: xaml configuration
platform: wpf
control: OLAP Gauge
documentation: ug
---

# XAML Configuration

XAML configuration is one of the important features of OlapGauge, as it helps the user to configure the control entirely using XAML by eliminating the required code in code behind. 

## Adding a Report to OLAP Gauge

Adding an OLAP report to OLAP Gauge control in design time is described in the following code snippet:

 {% highlight xaml %}

    

<syncfusion:OlapGauge x:Name="olapChart" 

                      HorizontalAlignment="Stretch"

                      ReportName="SalesReport"

                      CurrentCubeName="Adventure Works" 

                      SharedDataManagerName="localManager"

                      olapshared:DataSource.DataManagerName="localManager"

olapshared:DataSource.ConnectionString="datasource=localhost; initial catalog=adventure works dw">



<!- Adding Elements to Categorical Axis -->

<syncfusion:OlapGauge.CategoricalAxis>

                    <syncfusion:Dimension Name="Date" HierarchyName="Fiscal" LevelName="Fiscal Year" IncludeMembers="FY 2002, FY 2003"  />     <!- Multiple Members where specified by comma separate -->               

                    <syncfusion:Kpi Name="Revenue" ShowGoal="True" ShowStatus="True" ShowValue="True" ShowTrend="True" />

</syncfusion:OlapGauge.CategoricalAxis>



<!- Adding Elements to Series Axis -->

<syncfusion:OlapGauge.SeriesAxis>

                    <syncfusion:Dimension Name="Sales Channel" HierarchyName="Sales Channel" LevelName="Sales Channel" />

                    <syncfusion:Dimension Name="Product" HierarchyName="Product Model Lines" LevelName="Product Line" IncludeMembers="Road" />

</syncfusion:OlapGauge.SeriesAxis>



</syncfusion:OlapGauge>

 {% endhighlight %}







![](XAML-Configuration_images/XAML-Configuration_img1.png)


OLAP Gauge with SalesReport created by XAML code
{:.caption}

## Sample Link

A sample demo is available at the following link:     

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGauge.WPF\Samples\Defining Reports\XAML Configuration Demo 

