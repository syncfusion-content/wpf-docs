---
layout: post
title: MDX Query Parsing in WPF OLAP Common control | Syncfusion
description: Learn about MDX Query Parsing support in Syncfusion WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
documentation: ug
---

# MDX Query Parsing in WPF OLAP Common

## MDX Query binding with drill-up and drill-down operations


This feature provides support for drill-up and drill-down operations for BI components such as BI grid, BI chart, and BI client to view the OLAP data through different levels using an MDX query instead of the OlapReport class. Previously, the drill-up and drill-down operations were supported by the OlapReport class only.


### Properties

* **AllowMdxToReportParse**: Gets or sets a value indicating whether to parse the given MDX into the OlapReport class or not. The default value is true.

### Sample links



OlapGrid [WPF]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<version>\WPF\OlapGrid.WPF\Samples\Defining Reports\MDX Query Demo

OlapChart [WPF]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<version>\WPF\OlapChart.WPF\Samples\Defining Reports\MDX Query Demo

OlapClient [WPF]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<Version>\WPF\OlapClient.WPF\Samples\Product Showcase\MDX Query Demo

OlapGrid [Silverlight]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<Version>\BI\Silverlight\OlapGrid.Silverlight\ReportDefinition\GridMDXQueryDemo

OlapChart [Silverlight]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<Version>\BI\Silverlight\OlapChart.Silverlight\DefiningReports\ChartMDXQueryDemo

OlapClient [Silverlight]

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<Version>\BI\Silverlight\OlapClient.Silverlight\ProductShowcase\MDXQueryDemo

## Adding MDX Query binding with drill-up and drill-down operations to an application

The following code samples are used to enable and disable the MDX to OLAP parsing and processing of an MDX query into OLAP data.

{% tabs %}
{% highlight c# %}

     //Enable MDX to OLAP parsing.

            OlapDataManager olapDataManager = new OlapDataManager();     

            olapDataManager.MdxQuery = "MDX Query Here";

            olapDataManager.ExecuteCellSet();



     //Disable MDX to OLAP parsing.

            OlapDataManager olapDataManager = new OlapDataManager();

            olapDataManager.AllowMdxToOlapReportParse = false;

            olapDataManager.MdxQuery = "MDX Query Here";

            olapDataManager.ExecuteCellSet();

{% endhighlight  %}  

{% highlight vbnet %}

     ‘Enable MDX to OLAP parsing.

            Dim olapDataManager As New OlapDataManager()

            olapDataManager.MdxQuery = "MDX Query Here"

            olapDataManager.ExecuteCellSet()



     ‘Enable MDX to OLAP parsing.

            Dim olapDataManager As New OlapDataManager()

            olapDataManager.AllowMdxToOlapReportParse = False

            olapDataManager.MdxQuery = "MDX Query Here"

            olapDataManager.ExecuteCellSet()

{% endhighlight  %}  
{% endtabs %}

