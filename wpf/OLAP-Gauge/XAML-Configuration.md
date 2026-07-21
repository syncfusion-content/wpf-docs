---
layout: post
title: XAML Configuration in WPF OLAP Gauge control | Syncfusion
description: Learn about XAML Configuration support in Syncfusion WPF OLAP Gauge control, its elements and more details.
platform: wpf
control: OLAP Gauge
documentation: ug
---

# XAML Configuration in WPF OLAP Gauge

XAML configuration is an important feature of the OLAP gauge because it allows users to configure the control entirely in XAML, eliminating the need for code-behind.

## Properties

* **DataSource.ConnectionString**: Specifies the connection string of the data manager.
* **DataSource.ConnectionName**: Specifies the connection name, which is available in the App.Config file of the application.
* **DataSource.DataManagerName**: Specifies the data manager name.
* **SharedDataManagerName**: Specifies the name of the data manager available in the shared data manager collection.
* **ReportName**: Specifies the name of the OLAP report.
* **CurrentCubeName**: Specifies the current cube name of the OLAP report.
* **CategoricalAxis**: Specifies the categorical axis of the OLAP report.
* **SeriesAxis**: Specifies the series axis of the OLAP report.
* **SlicerAxis**: Specifies the slicer axis of the OLAP report.
* **CalculatedMembers**: Specifies the calculated members of the OLAP report.

The following code snippet illustrates how to add an OLAP report to the OLAP gauge at design time.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="olapGauge"
                      CurrentCubeName="Adventure Works"
                      ReportName="SalesReport"
                      SharedDataManagerName="localManager"
                      olapshared:DataSource.DataManagerName="localManager"
                      olapshared:DataSource.ConnectionString="datasource=localhost; initial catalog=adventure works dw">

    <!-- Adding Elements to Categorical Axis -->
    <syncfusion:OlapGauge.CategoricalAxis>
        <syncfusion:Dimension Name="Date"
                              HierarchyName="Fiscal"
                              LevelName="Fiscal Year"
                              IncludeMembers="FY 2002, FY 2003" />

        <!-- Multiple Members where specified by comma separate -->
        <syncfusion:Kpi Name="Revenue"
                        ShowGoal="True"
                        ShowStatus="True"
                        ShowValue="True"
                        ShowTrend="True" />
    </syncfusion:OlapGauge.CategoricalAxis>

    <!-- Adding Elements to Series Axis -->
    <syncfusion:OlapGauge.SeriesAxis>
        <syncfusion:Dimension Name="Sales Channel"
                              HierarchyName="Sales Channel"
                              LevelName="Sales Channel" />
        <syncfusion:Dimension Name="Product"
                              HierarchyName="Product Model Lines"
                              LevelName="Product Line"
                              IncludeMembers="Road" />
    </syncfusion:OlapGauge.SeriesAxis>
</syncfusion:OlapGauge>

{% endhighlight %}

{% endtabs %}

![XAML-Configuration_img1](XAML-Configuration_images/XAML-Configuration_img1.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Defining Reports\XAML Configuration\
