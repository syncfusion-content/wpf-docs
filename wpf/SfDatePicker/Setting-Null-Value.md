---
layout: post
title: Setting Null Value for SfDatePicker control for WPF
description: Setting Null Value for SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Setting Null Value

AllowNull property can be used to set the SfDatePicker value to Null.When this property is enabled along with the Value property whose value is Null, then the SfDatePicker control will not display any value 

The following code example and screen shot illustrate the usage of the AllowNull property.

{% highlight xaml %}


	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

	<syncfusion:SfDatePicker VerticalAlignment="Center" Width="200" Value="{x:Null}" AllowNull="True"/>

	</Grid>

{% endhighlight %}

![](Features_images/Features_img13.png)

## Setting the Input Scope for the On-Screen Keyboard


To set the input scope of the on-screen keyboard, use the InputScope property. When the InputScope property set to Number, only the numeric keypad will be visible in the on-screen keyboard
The following code example and screen shot illustrate this property.



N> The AllowInlineEditing property must be set to True for this property to take effect.



{% highlight xaml %}


	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

	<syncfusion:SfDatePicker VerticalAlignment="Center" Width="200"

	AllowInlineEditing="True" InputScope="Number"/>

	</Grid>

{% endhighlight  %}

![](Features_images/Features_img14.png)