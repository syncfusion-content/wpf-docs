---
layout: post
title: Serialize the SfChart | SfChart | WPF | Syncfusion
description: Learn about serialization and deserialization in Syncfusion Essential Studio WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# Serialization and Deserialization

SfChart provides support for serializing and deserializing the control. This section explains how to serialize and deserialize SfChart.

## Methods

<table>
<tr>
<th>Method Name</th>
<th>Description</th>
</tr>
<tr>
<td>Serialize()</td>
<td>Serializes the control and saves as an XML file in the parent folder.</td>
</tr>
<tr>
<td>Serialize(string filePath)</td>
<td>Serializes the control and saves as an XML file in the specified file path.</td>
</tr>
<tr>
<td>Serialize(Stream stream)</td>
<td>Serializes the control and saves as an XML file in the specified stream.</td>
</tr>
<tr>
<td>Deserialize()</td>
<td>Deserializes the XML file from the parent folder and returns the SfChart control object.</td>
</tr>
<tr>
<td>Deserialize(string filePath)</td>
<td>Deserializes the XML file from the specified file path and returns the SfChart control object.</td>
</tr>
<tr>
<td>Deserialize(Stream stream)</td>
<td>Deserializes the XML file from the specified stream and returns the SfChart control object.</td>
</tr>
</table>

{% tabs %}

{% highlight xaml %}

<chart:SfChart x:Name="chart">
    <chart:ColumnSeries ItemsSource="{Binding CategoricalDatas}" 
                        XBindingPath="Category" 
                        YBindingPath="Value" 
                        Palette="RedChrome"/>
</chart:SfChart>

<StackPanel>
    <Button x:Name="Serialize" 
            Content="Serialize" 
            Height="50" 
            Width="100" 
            Margin="10" 
            Click="Serialize_Click"/>
    <Button x:Name="Deserialize" 
            Content="Deserialize" 
            Height="50" 
            Width="100" 
            Margin="10" 
            Click="Deserialize_Click"/>
</StackPanel>

{% endhighlight %}

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