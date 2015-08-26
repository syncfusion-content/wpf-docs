---
layout: post
title: RTL support
description: RTL support
platform: wpf
control: PivotGrid
documentation: ug
---

## RTL support

Right-to-left support has been provided for the PivotGrid control for WPF. Users can now display content from right to left by setting the flow direction option in the control. 

#### Use Case Scenario

Some cultures have a written language that reads from right to left. Controls deployed for such cultures should be rendered from right to left. In these cases, we can utilize RTL support of the OLAP Gauge component. 

#### Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }} </td><td>
{{ '**Description**' | markdownify }} </td><td>
{{ '**Type**' | markdownify }} </td><td>
{{ '**Data Type**' | markdownify }} </td></tr>
<tr>
<td>
FlowDirection</td><td>
Gets or sets the flow direction for the PivotGrid control.</td><td>
Normal</td><td>
enum</td></tr>
</table> 

### Adding RTL support for PivotGrid in an Application 

To enable RTL support, the FlowDirection property of the PivotGrid control needs to be set as RightToLeft. The following code sample explains how to set the FlowDirection property. It can be set through XAML or C# code.

{% highlight xml %} 



<syncfusion:PivotGridControl FlowDirection="RightToLeft" x:Name="pivotGrid1" ItemSource="{Binding ProductSalesData}" >  

{% endhighlight %} 

{% highlight C# %}  



  this.pivotGrid1.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %} 

{% highlight vbnet %} 



  Me.pivotGrid1.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %} 

![](Features_images/Features_img57.jpeg)


_RTL support for PivotGrid_

#### Sample Link

A sample is available locally in the following location:

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\PivotAnalysis.WPF\Localization\LocalizationDemo



