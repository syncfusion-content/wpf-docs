---
layout: post
title: Serialization in WPF Charts control | Syncfusion
description: Learn here all about Serialization support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
 documentation: ug
---

# Serialization in WPF Charts (SfChart)

SfChart provides the support for serializing and deserializing control. This section explains on how to serialize and deserialize SfChart.

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

{% highlight xaml %}

 <Grid >
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="350" />
            <ColumnDefinition Width="350" />
        </Grid.ColumnDefinitions>
        
        <!--Serialize-->
        <chart:SfChart Grid.Column="0" Margin="10" x:Name="chart">

            <chart:SfChart.PrimaryAxis>
                <chart:CategoryAxis />
            </chart:SfChart.PrimaryAxis>
            
            <chart:SfChart.SecondaryAxis>
                <chart:NumericalAxis />
            </chart:SfChart.SecondaryAxis>
            
            <chart:ColumnSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category"
                                YBindingPath="Value"  EnableAnimation="True">
                <chart:ColumnSeries.AdornmentsInfo>
                    <chart:ChartAdornmentInfo ShowLabel="True" ShowMarker="True" Symbol="Ellipse" Foreground="White"/>
                </chart:ColumnSeries.AdornmentsInfo>
            </chart:ColumnSeries>
        </chart:SfChart>

         <!--Assign the DeSerialize Chart-->
        <chart:SfChart Grid.Column="1" x:Name="deserializedChart"/>
 
    </Grid>

    {% endhighlight %}

{% highlight c# %}

        //Action to Serialize the Chart
       private void Button_Click(object sender, RoutedEventArgs e)
        {
            chart.Serialize();         
        }

        //Action to Deserialize the Chart
        private void Load_Click(object sender, RoutedEventArgs e)
        {
            deserializedChart = (SfChart)chart.Deserialize();
        }        

{% endhighlight %}

{% endtabs %} 


![Serialization in WPF Charts](Serialization_images/Serialization.png)
