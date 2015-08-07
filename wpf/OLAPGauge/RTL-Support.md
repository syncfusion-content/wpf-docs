---
layout: post
title: RTL-Support
description: rtl support
platform: wpf
control: OLAP Gauge
documentation: ug
---

# RTL Support

Right-to-left support has been provided for the OLAP Gauge control for WPF. Users can now display content from right to left by setting the flow direction option in the control. 

## Use Case Scenario

Some cultures have a written language that reads from right to left. Controls deployed for such cultures should be rendered from right to left. In these cases, we can utilize RTL support of the OLAP Gauge component. 

## Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td></tr>
<tr>
<td>
FlowDirection</td><td>
Gets or sets the flow direction for the OLAP Gauge control. </td><td>
Normal</td><td>
enum</td></tr>
</table>
# Adding RTL support for OLAP Gauge in an application 

To enable RTL support, the FlowDirection property of the OLAP Gauge control needs to be set as RightToLeft. The following code sample explains how to set the FlowDirection property. It can be set through XAML or C# code.

{% highlight xml %}

   [XAML]

<syncfusion:OlapGauge x:Name="olapGauge" FlowDirection="RightToLeft" Grid.Column="0" HorizontalAlignment="Stretch" ReportName="SalesReport" olapshared:DataSource.ConnectionString="{Binding OlapConnectionString}">


 {% endhighlight %}



 {% highlight c# %}
 
   [C#]

this.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

 {% endhighlight %}




 {% highlight vbnet %}
  
    [VB]

Me.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

 {% endhighlight %}












![](RTL-Support_images/RTL-Support_img1.jpeg)


_RTL support for OLAP Gauge_

## Sample Link

A sample is available locally in the following location:

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapGauge.WPF\Localization\LocalizationDemo

