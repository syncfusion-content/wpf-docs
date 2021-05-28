---
layout: post
title: Header in WPF Charts control | Syncfusion
description: Learn here all about Header support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
 documentation: ug
---

# Header in WPF Charts (SfChart)

[`Header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Header) property is used to define the title for the chart. This allows you to add any object (.Net object) as content for chart title. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart  Header="Chart Area Header" />

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.Header = "Usage of Metals";

{% endhighlight %}

{% endtabs %}

![SfChart with header.](Area_images/Area_img1.jpeg)


Header can be positioned left or right side of the chart using [`HorizontalHeaderAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_HorizontalHeaderAlignment) property.

Also you can add more customization for the header as below: 

{% tabs %}

{% highlight xaml %}

<chart:SfChart.Header>

<Border BorderThickness="0.5" BorderBrush="Black" Margin="10" CornerRadius="5">

<TextBlock FontSize="14" Text="Chart Area Header" Margin="5">

<TextBlock.Effect>

<DropShadowEffect Color="Black" 

Opacity="0.5" />

</TextBlock.Effect>

</TextBlock>

</Border>

</chart:SfChart.Header>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

Border border = new Border()
{

BorderThickness = new Thickness(0.5),

BorderBrush = new SolidColorBrush(Colors.Black),

Margin = new Thickness(10),

CornerRadius = new CornerRadius(5)

};

TextBlock textBlock = new TextBlock()
{

Text = "Chart Area Header",

Margin = new Thickness(5),

FontSize = 14

};

textBlock.Effect = new DropShadowEffect()
{

Color = Colors.Black,

Opacity = 0.5

};

border.Child = textBlock;

chart.Header = border;

{% endhighlight %}

{% endtabs %}

![Header customization in SfChart](Area_images/Area_img2.jpeg)


N> Here, HorizontalHeaderAlignment is set as ‘Right’.

