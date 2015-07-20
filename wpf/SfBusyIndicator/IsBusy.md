---
layout: post
title: IsBusy
description: isbusy
platform: wpf
control: Busy Indicator
documentation: ug
---

# IsBusy

The IsBusy property in the BusyIndicator control is used to determine whether an animation needs to be executed or not.

[XAML]



<Grid Background="CornflowerBlue">

    <Navigation:SfBusyIndicator IsBusy="True"/>

</Grid>



[C#]



SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.IsBusy = true;





{{ '![C:/Users/ApoorvahR/Desktop/1.png](IsBusy_images/IsBusy_img1.png)' | markdownify }}
{:.image }




