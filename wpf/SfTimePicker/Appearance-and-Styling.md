---
layout: post
title: Appearance and Styling of SfTimePicker control for WPF
description: Appearance and Styling of SfTimePicker control for WPF
platform: wpf
control: SfTimePicker
documentation: ug
---

# Appearance and Styling

## Accent Brush

The AccentBrush property is used to decorate the hot spots of a control with a solid color.


{% highlight xaml %}




	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfTimePicker  VerticalAlignment="Center"

                                HorizontalAlignment="Center"

                                Width="200"

                                AccentBrush="Green"/>

	</Grid>

{% endhighlight %}

The following images showcase the control with various Accent Brushes:



![](Features_images/Features_img15.png)

## Selected Foreground

The SelectedForeground property is used to change the foreground color of  the Selected Time

{% highlight xaml %}



	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

       <syncfusion:SfTimePicker VerticalAlignment="Center"

                         HorizontalAlignment="Center"

                         Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="SelectedForeground" Value="Red"/>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>

      </syncfusion:SfTimePicker>

	</Grid>

{% endhighlight  %}


![](Features_images/Appearance-and-Styling_img2.png)