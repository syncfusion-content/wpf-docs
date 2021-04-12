---
layout: post
title: Header|Axis| SfChart | Wpf | Syncfusion 
description: Explains the Axis Header, Header Style, it's behavior and customization Header apperance in WPF Chart
platform: wpf
control: SfChart
documentation: ug
---

# Header in Chart Axis WPF Chart

## Header

In Chart Axis you can define any object as header using [`Header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_Header) property. The following code example demonstrates the defining header in primary and secondary axis. 

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.PrimaryAxis>            
 
<chart:CategoryAxis Header="Metals" />

</chart:SfChart.PrimaryAxis>        

<chart:SfChart.SecondaryAxis>
 
<chart:NumericalAxis Header="Values(In Tonnes)"/>

</chart:SfChart.SecondaryAxis>        

<chart:SfChart.Series>                

<chart:ColumnSeries ItemsSource="{Binding Metals}" XBindingPath="Category" YBindingPath="Value"/>

</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new CategoryAxis()
{ 
    Header = "Medals" 
};

chart.SecondaryAxis = new NumericalAxis()
{ 
    Header = "Values(In Tonnes)" 
};

ColumnSeries series = new ColumnSeries();

series.ItemsSource = (new ViewModel()).Metals;

series.XBindingPath = "Category";

series.YBindingPath = "Value";

chart.Series.Add(series);

this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Header support for ChartAxis in WPF](Axis_image/WPF_Header.png)

## HeaderStyle

[`HeaderStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_HeaderStyle) property is used to provide style for the axis header. The following code example explains header style customization.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis Header="Metals"> 
    
<chart:CategoryAxis.HeaderStyle>

<chart:LabelStyle FontFamily="Algerian" FontSize="13" Foreground="Black"/>

</chart:CategoryAxis.HeaderStyle>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>            

<chart:NumericalAxis Header="Values(In Tonnes)">

<chart:NumericalAxis.HeaderStyle>

<chart:LabelStyle FontFamily="Algerian" FontSize="13" Foreground="Black"/>

</chart:NumericalAxis.HeaderStyle>
    
</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>            

<chart:ColumnSeries x:Name="series" ItemsSource="{Binding Metals}" XBindingPath="Category" YBindingPath="Value"/>

</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

LabelStyle style = new LabelStyle()
{

    FontFamily = new FontFamily("Algerian"),

    FontSize = 13,

    Foreground = new SolidColorBrush(Colors.Black)

};

chart.PrimaryAxis = new CategoryAxis()
{

    Header = "Medals",

    LabelStyle = style

};

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Values(In Tonnes)",

    LabelStyle = style

};

ColumnSeries series = new ColumnSeries();

series.ItemsSource = (new ViewModel()).Metals;

series.XBindingPath = "Category";

series.YBindingPath = "Value";

chart.Series.Add(series);

this.Content = chart;

{% endhighlight %}

{% endtabs %}

![HeaderStyle for header support in WPF](Axis_image/WPF_HeaderStyle.png)

## Customize Header Appearance

Default appearance of the header can be customized using [`HeaderTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_HeaderTemplate) property. The following code snippet demonstrates the header customization.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<syncfusion:SfChart.Resources>
 
       <DataTemplate x:Key="headerTemplate1">

       <Border BorderBrush="Black" CornerRadius="5" BorderThickness="1">

       <TextBlock Text="Demands" FontSize="12"           FontStyle="Italic" FontWeight="Bold" Margin="3"/>

       </Border>

       </DataTemplate>

       <DataTemplate x:Key="headerTemplate2">

       <Border BorderBrush="Black" CornerRadius="5" BorderThickness="1">

       <TextBlock FontSize="12" Margin="3"
       FontStyle="Italic" FontWeight="Bold"/>

       </Border>

       </DataTemplate>

</syncfusion:SfChart.Resources>

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis HeaderTemplate="{StaticResource headerTemplate1}"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis Header="Values(In Tonnes)"
  HeaderTemplate="{StaticResource headerTemplate2}"/>

</syncfusion:SfChart.SecondaryAxis>
   
<chart:SfChart.Series>
    
<chart:ColumnSeries x:Name="series" ItemsSource="{Binding Metals}" XBindingPath="Category" YBindingPath="Value"/>
        
</chart:SfChart.Series>
        
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new CategoryAxis()
{
    HeaderTemplate = chart.Resources["headerTemplate1"] as DataTemplate

};

chart.SecondaryAxis = new NumericalAxis()
{
    HeaderTemplate = chart.Resources["headerTemplate2"] as DataTemplate

};

ColumnSeries series = new ColumnSeries();

series.ItemsSource = (new ViewModel()).Metals;

series.XBindingPath = "Category";

series.YBindingPath = "Value";

chart.Series.Add(series);

this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Header customization apperance for ChartAxis in WPF](Axis_image/WPF_Customize_Header_Appearance.png)