---
layout: post
title: RTL Support | OLAPGauge | wpf | Syncfusion
description: rtl support
platform: wpf
control: OLAP Gauge
documentation: ug
---

# RTL Support

Right-to-left support has been provided for the OLAP Gauge control for WPF. Users can now display content from right to left by setting the flow direction option in the control. 

# Adding RTL support for OLAP Gauge in an application 

To enable RTL support, the FlowDirection property of the OLAP Gauge control needs to be set as RightToLeft. The following code sample explains how to set the FlowDirection property. It can be set through XAML or C# code.


{%tabs%}
{% highlight xaml %}

   

<syncfusion:OlapGauge x:Name="olapGauge" FlowDirection="RightToLeft" Grid.Column="0" HorizontalAlignment="Stretch" ReportName="SalesReport" olapshared:DataSource.ConnectionString="{Binding OlapConnectionString}">


 {% endhighlight %}



 {% highlight c# %}
 
   

this.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

 {% endhighlight %}




 {% highlight vbnet %}
  
    

Me.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

 {% endhighlight %}




{%endtabs%}







![](RTL-Support_images/RTL-Support_img1.jpeg)


RTL support for OLAP Gauge
{:.caption}

## Sample Link

A sample is available locally in the following location:

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapGauge.WPF\Localization\LocalizationDemo

