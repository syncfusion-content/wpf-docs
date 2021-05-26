---
layout: post
title: Track ball in WPF Sparkline control | Syncfusion
description: Learn here all about Track ball support in Syncfusion WPF Sparkline (SfSparkline) control, its elements and more.
platform: wpf
control: SfSparkline
 documentation: ug
---

# Track ball in WPF Sparkline (SfSparkline)

This is used to indicate the value point on mouse move and this feature is applicable for line and area sparkline.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline 

                ItemsSource="{Binding UsersList}" 

                ShowTrackBall="True”

                YBindingPath="NoOfUsers">

  </Syncfusion:SfLineSparkline >
  
{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowTrackBall = true

};

{% endhighlight %}

{% endtabs %}

Following is the snapshot for track ball,

![Track-ball_img1](Track-ball_images/Track-ball_img1.png)

**Customizing TrackBall**

You can customize the default appearance of the Trackball style by using the TrackballStyle property. 

The following code shows how to apply the style for the Trackball line.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="Ellipse" x:Key="lineStyle1">

        <Setter Property="Fill" Value="Blue"></Setter>

        <Setter Property="Height" Value="12"></Setter>

        <Setter Property="Width" Value="12"></Setter>

    </Style>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Blue"/>

        <Setter Property="StrokeThickness" Value="2"></Setter>

        <Setter Property="StrokeDashArray" Value="1,2"></Setter>

    </Style>

</Grid.Resources>

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"   

BorderBrush="DarkGray" BorderThickness="1"

ItemsSource="{Binding UsersList}" ShowTrackBall="True" 

TrackBallStyle="{StaticResource lineStyle1}" 

LineStyle="{StaticResource lineStyle2}"

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().Data,

    YBindingPath = "Day",

    ShowTrackBall = true,

    Interior = new SolidColorBrush(Colors.Gray),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1),

    LineStyle = this.Resources["lineStyle1"] as Style,

    TrackBallStyle = this.Resources["lineStyle2"] as Style

};

{% endhighlight %}

{% endtabs %}

![Customizing TrackBall](Track-ball_images/Trackball_img2.jpeg)
