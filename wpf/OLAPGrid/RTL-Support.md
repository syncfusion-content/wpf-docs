---
layout: post
title: RTL Support| OLAP Grid | Wpf | Syncfusion
description: rtl support
platform: wpf
control: OLAP Grid
documentation: ug
---

# RTL Support

Right-to-left support has been provided for the OLAP Grid control for WPF. Users can now display content from right to left by setting the flow direction option in the control. 

## Adding RTL support for OLAP Grid in an application 

To enable RTL support, the FlowDirection property of the OLAP Grid control needs to be set as RightToLeft. The following code sample explains how to set the FlowDirection property. It can be set through XAML or C# code.

{% tabs %}
  {% highlight xaml %}

   

<syncfusion:OlapGrid x:Name="olapGrid" FlowDirection="RightToLeft" ReportName="SalesReport" SharedDataManagerName="localManager" olapshared:DataSource.DataManagerName="localManager">  


    {% endhighlight %}


  {% highlight c# %}

   

  this.olapGrid.FlowDirection = System.Windows.FlowDirection.RightToLeft;

    {% endhighlight %}





    {% highlight vbnet %}

    

  Me.olapGrid.FlowDirection = System.Windows.FlowDirection.RightToLeft;

    {% endhighlight %}


{% endtabs %}


![](RTL-Support_images/RTL-Support_img1.png)


RTL support for OLAP Grid
{:.caption}

### Sample Link

A sample is locally available in the following location:

SystemDrive

\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapGrid.WPF\Localization\LocalizationDemo

