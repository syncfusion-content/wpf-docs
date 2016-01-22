---
layout: post
title: Printing| SfChart | Wpf | Syncfusion
description: printing
platform: wpf
control: SfChart
documentation: ug
---

# Printing

SfChart supports printing that enables you to print the chart. This support works in Windows 8.1 but not in Windows 8.



<table>
<tr>
<th>
Prototype</th><th>
 Description</th></tr>
<tr>
<td>
Print()</td><td>
This method is used to print the chart by invoking the Charm window listing with output options.</td></tr>
</table>


The following code example illustrates the Printing feature.
{% tabs %}
{% highlight xaml %}



<syncfusion:SfChart HorizontalAlignment="Right" VerticalAlignment="Top" Height="400" Width="650" Margin="0,50,100,0"

Palette="Metro" Loaded="ChartOnLoaded"

>

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:NumericalAxis Interval="2" FontSize="14" />

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis FontSize="14"/>

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}



{% highlight C# %}



private void ChartOnLoaded(object sender, RoutedEventArgs routedEventArgs)

{

var chart = sender as SfChart;

if (chart != null)

chart.Print();

}

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates Printing.

![C:/Users/rachel/Desktop/snaps/20.png](Printing_images/Printing_img1.png)



