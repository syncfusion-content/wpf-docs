---
layout: post
title: Serialize the SfChart| SfChart | Wpf | Syncfusion
description: Serialization and deserialization in Syncfusion Essential Studio WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# Serialization and Deserialization:

SfChart provides the support for serializing and deserializing control. This section explains on how to serialize and deserialize SfChart.

## Methods:

<table>
<tr>
<th>
Method Name</th><th>
Description</th></tr>
<tr>
<td>
Serialize()</td><td>
Serialize the control and saves as the XML file in the parent folder.</td></tr>
<tr>
<td>
Serialize(string filePath)</td><td>
Serialize the control and saves as the XML file in the given file path.</td></tr>
<tr>
<td>
Serialize(Stream stream)</td><td>
Serialize the control and saves as the XML file in the given stream.</td></tr>
<tr>
<td>
Deserialize()</td><td>
Deserialize the XML file from the parent folder and returns the SfChart control object.</td></tr>
<tr>
<td>
Deserialize(string filePath)</td><td>
Deserialize the XML file from the given file path and returns the SfChart control object.</td></tr>
<tr>
<td>
Deserialize(Stream stream)</td><td>
Deserialize the XML file from the given stream and returns the SfChart control object.</td></tr>
</table>
{% tabs %}

XAML

{% highlight xaml %}

<chart:SfChart x:Name=chart>

	<chart:ColumnSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category" YBindingPath="Value" Palette="RedChrome"/>

</chart:SfChart>

<StackPanel>

	<Button x:Name="Serialize" Content="Serialize" Height="50" Width="100" Margin="10" Click="Serialize_Click"/>

	<Button x:Name="Deserialize" Content="Deserialize" Height="50" Width="100" Margin="10" Click="Deserialize_Click"/>

</StackPanel>

{% endhighlight %}

C#

{% highlight c# %}

private void Serialize_Click(object sender, RoutedEventArgs e)

{

string filePath = @"E:/Documents/chart.xml";

chart.Serialize(filePath); 

}

private void Deserialize_Click(object sender, RoutedEventArgs e)

{

string filePath = @"E:/Documents/chart.xml";

var deserializedChart = (SfChart)chart.Deserialize();

}

{% endhighlight %}

{% endtabs %}

