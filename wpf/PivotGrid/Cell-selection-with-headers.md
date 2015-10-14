---
layout: post
title: Cell selection with headers| PivotGrid | Wpf | Syncfusion
description: Cell selection with headers
platform: wpf
control: PivotGrid
documentation: ug
---

# Cell selection with headers

PivotGrid control provides cell selection feature that is used to select values along the row and column headers according to their covered ranges.

### Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Parameters</th><th>
    Type</th><th>
Return Type</th></tr>
<tr>
<td>
EnableSelectionWithHeaders</td><td>
Used to enable the selection behavior.</td><td>
</td><td>
bool</td><td>
bool</td></tr>
</table>

### Adding cell selection option with headers for PivotGridControl in an application

The following code example explains the usage of the "EnableAllowSelctionWithHeaders" property. You can use the mentioned 
property either in XAML or C#.

{% tabs %}
{% highlight xml %}  


<syncfusion:PivotGridControl Margin="5" Grid.Row="0" x:Name="pivotGrid1" ShowGroupingBar="False" ItemSource="{Binding ProductSalesData}" AllowSelectionWithHeaders="True">

{% endhighlight %}

{% highlight C# %}  

this.pivotGrid1.AllowSelectionWithHeaders = true;

{% endhighlight %} 
{% endtabs %}

It is used to select the header cells along with the value cells while selecting the respective row(s) or column(s). Refer the following screenshots.

![D:/Capture15.PNG](Features_images/Features_img67.png)



Selecting the sub-columns along with headers
{:.caption}

![D:/Capture16.PNG](Features_images/Features_img68.png)



Selecting the entire row along with headers
{:.caption}

### Sample Link

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version    number>\BI\WPF\PivotAnalysis.Wpf\Samples\Selection\Cell Selection Demo

