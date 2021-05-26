---
layout: post
title: ShowHide Axis in WPF Sparkline control | Syncfusion
description: Learn here all about ShowHide Axis support in Syncfusion WPF Sparkline (SfSparkline) control and more.
platform: wpf
control: SfSparkline
 documentation: ug
---

# ShowHide Axis in WPF Sparkline (SfSparkline)

Following code used to enable the axis and this feature applicable for all the sparkline except WinLoss sparkline, also you can style the axis by AxisStyle property and position the axis by AxisOrigin property.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline ShowAxis="True" ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for axis visibility,

![ShowHide-Axis_img1](ShowHide-Axis_images/ShowHide-Axis_img1.png)

**Axis Origin**

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"

ShowAxis="True" 

AxisOrigin="2" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true,

    AxisOrigin = 2,

    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

{% endhighlight %}

{% endtabs %}

![Axis Origin](ShowHide-Axis_images/ShowHideAxis_img2.jpeg)


**Axis LineStyle**

{% tabs %}

{%highlight xaml%}

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Blue"/>

        <Setter Property="StrokeThickness" Value="2"></Setter>

        <Setter Property="StrokeDashArray" Value="1,1"></Setter>

    </Style>

</Grid.Resources>

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"   

BorderBrush="DarkGray"  BorderThickness="1"

ShowAxis="True" AxisStyle="{StaticResource lineStyle2}"   

AxisOrigin="1" ItemsSource="{Binding UsersList}"   

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true,

    AxisOrigin = 1,

    AxisStyle = grid.Resources["lineStyle2"] as Style,

    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

{% endhighlight %}

{% endtabs %}

![Customizing Axis line](ShowHide-Axis_images/ShowHideAxis_img3.jpeg)
