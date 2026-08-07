---
layout: post
title: ShowHide Axis in WPF Sparkline | Syncfusion®
description: Show and hide the axis in the WPF Sparkline to control axis visibility and customize the chart appearance based on data requirements.
platform: wpf
control: SfSparkline
documentation: ug
---

# ShowHide Axis in WPF Sparkline

The following code is used to enable the axis. This feature is applicable for all sparklines except the WinLoss sparkline. You can also style the axis using the `AxisStyle` property and position the axis using the `AxisOrigin` property.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 
    ShowAxis="True" 
    ItemsSource="{Binding UsersList}" 
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    ShowAxis = true
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the axis visibility.

![ShowHide-Axis_img1](ShowHide-Axis_images/ShowHide-Axis_img1.png)

**Axis origin**

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline
    Height="250"
    Width="350"
    Interior="#4a4a4a"
    BorderBrush="DarkGray"
    BorderThickness="1"
    ShowAxis="True"
    AxisOrigin="2"
    ItemsSource="{Binding UsersList}"
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    ShowAxis = true,
    AxisOrigin = 2,
    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),
    BorderBrush = new SolidColorBrush(Colors.DarkGray),
    BorderThickness = new Thickness(1)
};

{% endhighlight %}

{% endtabs %}

![Axis origin](ShowHide-Axis_images/ShowHideAxis_img2.jpeg)


**Axis line style**

{% tabs %}

{% highlight xaml %}

<Grid.Resources>
    <Style TargetType="Line" x:Key="lineStyle2">
        <Setter Property="Stroke" Value="Blue"></Setter>
        <Setter Property="StrokeThickness" Value="2"></Setter>
        <Setter Property="StrokeDashArray" Value="1,1"></Setter>
    </Style>
</Grid.Resources>

<Syncfusion:SfLineSparkline
        Height="250"
        Width="350"
        Interior="#4a4a4a"
        BorderBrush="DarkGray"
        BorderThickness="1"
        ShowAxis="True"
        AxisStyle="{StaticResource lineStyle2}"
        AxisOrigin="1"
        ItemsSource="{Binding UsersList}"
        YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    ShowAxis = true,
    AxisOrigin = 1,
    AxisStyle = this.Resources["lineStyle2"] as Style,
    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),
    BorderBrush = new SolidColorBrush(Colors.DarkGray),
    BorderThickness = new Thickness(1)
};

{% endhighlight %}

{% endtabs %}

![Customizing Axis line](ShowHide-Axis_images/ShowHideAxis_img3.jpeg)