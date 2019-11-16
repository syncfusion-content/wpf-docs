---
layout: post
title: Selector Item Customization | SfDatePicker | WPF | Syncfusion
description: Deals with the Selector Item Customization of the SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# SelectorItem Customization

## SelectorItemWidth and SelectorItemHeight

The item size in the SfDateSelector control can be changed by setting the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemWidth.html) and [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemHeight.html) properties.



## SelectorItemSpacing 

The [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemSpacing.html) property provides the space between the items in SfDateSelector.



## SelectorItemCount

The [SelectorItemCount](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemCount.html) property is used to specify the number of items to be used in SfDateSelector.

The following code sample shows the usage of the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemWidth.html), [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemHeight.html), [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemSpacing.html), and [SelectorItemCount](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemCount.html) properties. 

{% highlight xaml %}



	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfDatePicker VerticalAlignment="Center"

                                   Width="200"

	SelectorItemWidth="100"

                SelectorItemHeight="100"

                SelectorItemSpacing="50"

                SelectorItemCount="4"/>



	</Grid>

{% endhighlight %}

The output is displayed in the following image:

![Selector item count](Features_images/Features_img10.png)





