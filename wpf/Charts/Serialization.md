---
layout: post
title: Serialization in Syncfusion SfChart WPF.
description: Essental WPF Chart (SfChart) supports serialization and deserialization to save the settings of the chart and reload.
platform: wpf
control: SfChart
documentation: ug
---

# Serialization in WPF Charts (SfChart)

SfChart supports serialization and deserialization to save the settings of the chart and reload. 

This can be done using [`Serialize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~Serialize.html#) and [`Deserialize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~Deserialize.html#) methods as in below code example:

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