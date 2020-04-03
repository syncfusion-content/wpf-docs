---
layout: post
title: Setting Value in WPF SfTimePicker control | Syncfusion
description: This page explains about how to set or select a time in various ways from the WPF SfTimePicker control.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Setting time in WPF SfTimePicker

We can change the value of [SfTimePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker.html) by using the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) and keyboard interaction.

## Setting Time using property

We can set or change the selected time by using [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~Value.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker  Value="04:45:00"
						  Name="sfTimePicker" />

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.Value = new TimeSpan(04, 45, 00);

{% endhighlight %}
{% endtabs %}

![SfTimePicker displaying selected value](Features_images/Features_img17.png)

## Setting Null Value

If we want to set null value for the `SfTimePicker`, set the [AllowNull](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~AllowNull.html) property as `true` and [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~Value.html) property as `null`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker  AllowNull="True" 
                          Value="{x:Null}"
						  Name="sfTimePicker" />

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.AllowNull = true;
sfTimePicker.Value = null;

{% endhighlight %}
{% endtabs %}

![SfTimePicker displaying null value](Features_images/Features_img13.png)

## Set selected value on lost focus

By default, the selected time of TimeSelector can be sets to the `SfTimePicker.Value` property by clicking the `OK` button. If We want to update the selected time of TimeSelector to the `SfTimePicker.Value` property automatically without clicking the OK button, use the [SetValueOnLostFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SetValueOnLostFocus.html) property value as `true`. This is value updated after the TimeSelector lost its focus. The default value of `SetValueOnLostFocus` property is false.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker  SetValueOnLostFocus="True"
				          Name="sfTimePicker" />

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.SetValueOnLostFocus = true;

{% endhighlight %}
{% endtabs %}

![SfTimePicker value updated on when SfTimeSelector lost its focus](Features_images/Features_img15.gif)

## Setting the Input Scope for the On-Screen Keyboard

We can change the input type of the on-screen keyboard by using the [InputScope](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~InputScope.html) property. When the `InputScope` property set to `Number`, only the numeric keypad will be visible in the on-screen keyboard.

N> The [AllowInlineEditing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~AllowInlineEditing.html) property must be set to `True` for this property to take effect.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker Name="sfTimePicker" 
                         AllowInlineEditing="True" 
                         InputScope="Time"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.AllowInlineEditing = true;
sfTimePicker.InputScope = InputScopeNameValue.Time;

{% endhighlight %}
{% endtabs %}

![SfTimePicker with Input Scope for the On-Screen Keyboard](Features_images/Features_img14.png)

## Restrict selecting time limit

we can restrict the user to select a time in the specific time limit by setting the value for the [MinTime](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~MinTime.html) and [MaxTime](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~MaxTime.html) properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker MinTime="07:00:00"
                         MaxTime="09:00:00" 
                         Name="sfTimePicker"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.MinTime = new TimeSpan(07,00,00);
sfTimePicker.MaxTime = new TimeSpan(09,00,00);

{% endhighlight %}
{% endtabs %}

![SfTimePicker with max-min time range](Features_images/Features_img16.png)

Here, the users can select the hour from 7 to 9 only. 

## Time changed notification

When the selected time of `SfTimePicker`is changed, it will be notified by using the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~ValueChanged_EV.html) event. You can get the details about the checked item in [ItemCheckedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.ItemCheckedEventArgs.html).

* **OldValue** : Gets a time which is previously selected.

* **NewValue** : Gets a time which is currently selected.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfTimePicker ValueChanged="SftimePicker_ValueChanged" 
                         Name="sfTimePicker"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.ValueChanged += SftimePicker_ValueChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void SftimePicker_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {          
    Console.WriteLine("The Old selected time: " + e.OldValue.ToString());
    Console.WriteLine("The Newly selected time: " + e.NewValue.ToString());            
}

{% endhighlight %}
{% endtabs %}

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/SfTimePicker-Value-setting) to download the sample that showcases the input types and selected time with its notification supports.