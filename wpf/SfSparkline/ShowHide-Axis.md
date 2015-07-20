---
layout: post
title: ShowHide-Axis
description: show/hide axis
platform: wpf
control: Sparkline
documentation: ug
---

# Show/Hide Axis

Following code used to enable the axis and this feature applicable for all the sparkline except WinLoss sparkline, also you can style the axis by AxisStyle property and position the axis by AxisOrigin property.

[XAML]

<Syncfusion:SfLineSparkline ShowAxis="True" ItemsSource="{Binding UsersList}"                     YBindingPath="NoOfUsers" >

</Syncfusion:SfLineSparkline>

Following is the snapshot for axis visibility,

{{ '![C:/Users/ApoorvahR/Desktop/11.png](ShowHide-Axis_images/ShowHide-Axis_img1.png)' | markdownify }}
{:.image }


