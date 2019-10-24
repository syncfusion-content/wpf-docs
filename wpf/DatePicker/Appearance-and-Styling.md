---
layout: post
title: Appearance and Styling | SfDatePicker | WPF | Syncfusion
description: Appearance and Styling of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Appearance and Styling

## Accent Brush	

The [AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~AccentBrush.html) property is used to decorate the hot spots of a control with a solid color.

{% highlight XAML %}


	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfDatePicker  VerticalAlignment="Center"

                                HorizontalAlignment="Center"

                                Width="200"

                                AccentBrush="Green"/>

	</Grid>

{% endhighlight  %}

The following image shows the control with various Accent brushes:

![Appearance](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)


## Selected Foreground

The SelectedForeground property is used to change the foreground color of  the Selected Date

{% highlight XAML %}

	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfDatePicker VerticalAlignment="Center"

                         HorizontalAlignment="Center"

                         Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">
                 
                    <Setter Property="SelectedForeground" Value="Red"/>
                    
                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>

        </syncfusion:SfDatePicker>

	</Grid>

{% endhighlight  %}


![Selected Foreground](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)