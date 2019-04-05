---
layout: post
title: Setting Null Value | SfDatePicker | WPF | Syncfusion
description: Setting Null Value for SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Setting Null Value

[AllowNull](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~AllowNull.html) property can be used to set the SfDatePicker value to Null.When this property is enabled along with the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Value.html) property whose value is Null, then the SfDatePicker control will not display any value 

The following code example and screen shot illustrate the usage of the AllowNull property.

{% highlight xaml %}


	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

	<syncfusion:SfDatePicker VerticalAlignment="Center" Width="200" Value="{x:Null}" AllowNull="True"/>

	</Grid>

{% endhighlight %}

![Setting null value](Features_images/Features_img13.png)

## Setting the Input Scope for the On-Screen Keyboard


To set the input scope of the on-screen keyboard, use the [InputScope](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~InputScope.html) property. When the [InputScope](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~InputScope.html) property set to Number, only the numeric keypad will be visible in the on-screen keyboard
The following code example and screen shot illustrate this property.



N> The [AllowInlineEditing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~AllowInlineEditing.html) property must be set to True for this property to take effect.



{% highlight XAML %}


	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

	<syncfusion:SfDatePicker VerticalAlignment="Center" Width="200"

	AllowInlineEditing="True" InputScope="Number"/>

	</Grid>

{% endhighlight  %}

![Setting the Input Scope for the On-Screen Keyboard](Features_images/Features_img14.png)