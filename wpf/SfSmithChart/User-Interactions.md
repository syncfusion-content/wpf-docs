---
layout: post
title: User Interactions| ToolTip | SfSmithChart | Wpf | Syncfusion
description: user interactions
platform: wpf
control: SfSmithChart
documentation: ug
---

# User Interaction

## ToolTip

The ToolTip for data points can be enabled by setting the *ShowToolTip* property as True. ToolTip displays the  duration that is defined by the *ToolTipDuration* property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
     <syncfusion:LineSeries ShowToolTip="True" ToolTipDuration="0:0:3">
     </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.ShowToolTip = true;
series.ToolTipDuration = TimeSpan.FromSeconds(3);
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![](User-Interactions_images/User-Interactions_img1.png)

**ToolTipTemplate**

*ToolTipTemplate* property allows to customize the default appearance of the tooltip as illustrated in the below code  example.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
   <syncfusion:SfSmithChart.Resources>
   <DataTemplate x:Key="toolTipTemplate">
      <Border CornerRadius="4" Background="{Binding Interior}" BorderBrush="Yellow" BorderThickness="2">
          <Grid HorizontalAlignment="Center" Margin="8,8,8,8">
              <Grid.RowDefinitions>
                  <RowDefinition/>
                  <RowDefinition/>
              </Grid.RowDefinitions>
              <Grid.ColumnDefinitions>
                  <ColumnDefinition/>
                  <ColumnDefinition/>
                  <ColumnDefinition/>
              </Grid.ColumnDefinitions>

              <TextBlock Grid.Row="0" Grid.Column="0" Text="Resistance" Foreground="{Binding ForeColor}" FontSize="13" />
              <TextBlock Grid.Row="0" Grid.Column="1" Text=" : " Foreground="{Binding ForeColor}" FontSize="13" Margin="0,-1,0,0" />
              <TextBlock Grid.Row="0" Grid.Column="2" Text="{Binding Resistance}" Foreground="{Binding ForeColor}" FontSize="13" Margin="3,0,0,0" />
              <TextBlock Grid.Row="1" Grid.Column="0" Text="Reactance" Foreground="{Binding ForeColor}" FontSize="13" />
              <TextBlock Grid.Row="1" Grid.Column="1" Text=" : " Foreground="{Binding ForeColor}" FontSize="13" Margin="0,-1,0,0" />
              <TextBlock Grid.Row="1" Grid.Column="2" Text="{Binding Reactance}" Margin="3,0,0,0" Foreground="{Binding ForeColor}" FontSize="13" />
          </Grid>
      </Border>
  </DataTemplate>
 </syncfusion:SfSmithChart.Resources>

   <syncfusion:LineSeries ShowToolTip="True" ToolTipTemplate="{StaticResource toolTipTemplate}" ShowMarker="True" MarkerType="Custom" MarkerTemplate="{StaticResource Ellipse}" ItemsSource="{Binding Data}" ResistancePath="Resistance" ReactancePath="Reactance">
   </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.ShowToolTip = true;
series.ToolTipTemplate = this.Grid1.Resources["toolTipTemplate"] as DataTemplate;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![](User-Interactions_images/User-Interactions_img2.png)