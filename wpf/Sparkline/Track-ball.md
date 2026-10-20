---
layout: post
title: Trackball in WPF Sparkline | Syncfusion®
description: Trackball in the WPF Sparkline displays data values at specific points, enabling precise inspection and analysis of chart data.
platform: wpf
control: SfSparkline
documentation: ug
---

# Trackball in WPF Sparkline

The track ball is used to indicate the value point on mouse move. This feature is applicable for line and area sparklines.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 
    ItemsSource="{Binding UsersList}" 
    ShowTrackBall="True"
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>
  
{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    ShowTrackBall = true
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the track ball.

![Track-ball_img1](Track-ball_images/Track-ball_img1.png)

**Customizing the track ball**

**Customizing the track ball**

You can customize the default appearance of the track ball by using the `TrackBallStyle` property. 

The following code shows how to apply the style for the track ball line.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>
    <Style TargetType="Ellipse" x:Key="lineStyle1">
        <Setter Property="Fill" Value="Blue"></Setter>
        <Setter Property="Height" Value="12"></Setter>
        <Setter Property="Width" Value="12"></Setter>
    </Style>

    <Style TargetType="Line" x:Key="lineStyle2">
        <Setter Property="Stroke" Value="Blue" />
        <Setter Property="StrokeThickness" Value="2"></Setter>
        <Setter Property="StrokeDashArray" Value="1,2"></Setter>
    </Style>
</Grid.Resources>

<Syncfusion:SfLineSparkline
    Height="250"
    Width="350"
    Interior="#4a4a4a"
    BorderBrush="DarkGray"
    BorderThickness="1"
    ItemsSource="{Binding UsersList}"
    ShowTrackBall="True"
    TrackBallStyle="{StaticResource lineStyle1}"
    LineStyle="{StaticResource lineStyle2}"
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    ShowTrackBall = true,
    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),
    BorderBrush = new SolidColorBrush(Colors.DarkGray),
    BorderThickness = new Thickness(1),
    TrackBallStyle = this.Resources["lineStyle1"] as Style,
    LineStyle = this.Resources["lineStyle2"] as Style
};

{% endhighlight %}

{% endtabs %}

![Customizing TrackBall](Track-ball_images/Trackball_img2.jpeg)
