---
layout: post
title: Selector Item Customization | SfDatePicker | WPF | Syncfusion
description: Deals with the Selector Item Customization of the SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# SelectorItem Customization of WPF SfDatePicker

We can change the date selector items width, height and spacing.

## SfDateSelector item width and height

The item size in the `SfDateSelector` control can be changed by setting the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemWidth.html) and [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemHeight.html) properties. The default value of the `SelectorItemWidth` and `SelectorItemHeight` properties is `80` and `70`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker SelectorItemWidth="100" 
                         SelectorItemHeight="100" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorItemWidth = 100;
sfDatePicker.SelectorItemHeight = 100;

{% endhighlight %}
{% endtabs %}

![SfDateSelector item width and height changed](Customizing-DropDown_images/SelectorItemWidth.png)

## SfDateSelector item spacing
 
We can change the space between `SfDateSelector` date, month and year items by using the [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemSpacing.html). The default value of the `SelectorItemSpacing` property is `4`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker SelectorItemSpacing="50" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorItemSpacing = 50;

{% endhighlight %}
{% endtabs %}

![SfDateSelector item with custom spacing](Customizing-DropDown_images/SelectorItemSpacing.png)

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





