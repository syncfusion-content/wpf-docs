---
layout: post
title: Set the Value for UpDown | UpDown | WPF | Syncfusion
description: This section describes about how to set the Value and restrict the maximum and minimum value for UpDown
platform: wpf
control: UpDown
documentation: ug
---

# Restriction

The value for `UpDown` can be specified by the Value property. 

## Value

You can change the value of [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control using [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Value.html) property. A value can be set for the UpDown control as shown in the following code example.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="10" />

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Height = 25;
updown.Width = 90;
updown.Value = 10;
grid.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

![Applied the value in WPF UpDown](Restriction_images/Updown_value.png)

### Value event

The UpDown control notifies the changing value by handling [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~ValueChanged_EV.html) and [ValueChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~ValueChanging_EV.html) events. You can use the `OldValue` and `NewValue` property to get the old and new value in `ValueChanged` event. In `ValueChanging` event, you can use the `Cancel` property to avoid the changing value.

{% tabs %}

{% highlight C# %}

updown.ValueChanged += Up_ValueChanged;
updown.ValueChanging += Up_ValueChanging;

private void Up_ValueChanging(object sender, ValueChangingEventArgs e)
{
    e.Cancel = true;            
}

private void Up_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}

{% endtabs %}

## Null value

The [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control allows the null value.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="{x:Null}" />

{% endhighlight %}

{% highlight C# %}

updown.Value = null;

{% endhighlight %}

{% endtabs %}

![Shows before set the null value in WPF UpDown](Restriction_images/Updown_beforenull.png)


The [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NullValue.html) property can be used to show a null value in the `UpDown` control. The [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~UseNullOption.html) property must be allowed if you want to see the null value.


{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="{x:Null}" NullValue="2" UseNullOption="True" />

{% endhighlight %}

{% highlight C# %}

updown.UseNullOption = true;
updown.Value = null;
updown.NullValue = 2;

{% endhighlight %}

{% endtabs %}

![Show the null value in WPF UpDown](Restriction_images/Updown_nullvalue.png)

## Watermark

The [NullValueText](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NullValueText.html) property enables the `UpDown` control to accept null values when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Value.html) is null.

The [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~UseNullOption.html) property must be allowed to display the text of the null value in [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control. You can use the `NullValueText` property if you want to see the null value as a watermark text.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="{x:Null}" NullValueText="Enter a value" UseNullOption="True" />

{% endhighlight %}

{% highlight C# %}

updown.Value = null;
updown.NullValueText = "Enter a value";

{% endhighlight %}

{% endtabs %}

![Show the null value text in WPF UpDown](Restriction_images/Updown_nullvaluetext.png)


N> The `UseNullOption` property must be allowed if you want to see the `NullValue` or `NullValueText` in UpDown command. If you used simultaneously `NullValue` and `NullValueText` properties, you will see only the null value.


## Minimum and Maximum value

The UpDown control allows the maximum and minimum value to be restricted. The spin button helps to increase or decrease the value by using mouse interaction. Once the increase or decrease value reached the predefined maximized or minimized value, the value not changed by clicking the spin button.

Another way,

By using the keyboard, you can not enter the value above or below the predefined maximized or minimized value.

* **MaxValue** - The [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValue.html) property is the maximum value that can be set for the `UpDown` control.

* **MinValue** - The [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValue.html) property is the minimum value that can be set for the `UpDown` control.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.MaxValue = 100;
updown.MinValue = 0;

{% endhighlight %}

{% endtabs %}

![Show the minimum and maximum value in WPF UpDown](Restriction_images/Updown_min_and_max.png)


### Minimum and Minimum validation

You can validate the maximum and minimum value while entering the values by using [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) and [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) property.

* **OnKeyPress** - On setting the [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) or [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) to OnKeyPress, then the value in the UpDown control is validated when editing the value in the UpDown control. After validation, when the value is greater than the MaxValue or lesser than the MinValue, the UpDown control cannot let to edit the value.

* **OnLostFocus** - On setting the [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) or [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) to OnLostFocus, then the value in the UpDown control is validated when the UpDown control loses focus. After validation, when the value of the UpDown control is greater than the MaxValue or lesser than the MinValue, the value will be changed automatically is set to MaxValue or MinValue respectively.

* **MaxValueOnExceedMaxDigit** - On enabling the `MaxValueOnExceedMaxDigit` property and setting the `MaxValidation` to the OnKeyPress, then MaxValue is assigned to the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Value.html) property when the value is greater than the `MaxValue`. However, when the [MaxValueOnExceedMaxDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValueOnExceedMaxDigit.html) property is disabled, the UpDown control cannot let to enter the text, when the value be greater than the `MaxValue`. For example, if you think to enter the values like 2, 20 and 200, the value will be changed to the maximized value when the `MaxValueOnExceedMaxDigit` property is enabled. Otherwise, you can't enter the values above maximized value.

* **MinValueOnExceedMinDigit** - Similarly, on enabling the `MinValueOnExceedMinDigit` property and setting the `MinValidation` to the OnKeyPress, the `MinValue` is assigned to the Value property when the value is lesser than the MinValue. However, when the [MinValueOnExceedMinDigit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValueOnExceedMinDigit.html) property is disabled, the text cannot enter in the UpDown control should the value be lesser than MinValue. For example, if you think to enter the values like negative values, the value will be changed to the minimized value when the `MinValueOnExceedMaxDigit` property is enabled. Otherwise, you can't enter the values below minimized value.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" MinValueOnExceedMinDigit="True" MaxValueOnExceedMaxDigit="True" MaxValidation="OnKeyPress" MinValidation="OnKeyPress" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.MaxValidation = MaxValidation.OnKeyPress;
updown.MinValidation = MinValidation.OnKeyPress;
updown.MinValueOnExceedMinDigit = true;
updown.MaxValueOnExceedMaxDigit = true;

{% endhighlight %}

{% endtabs %}


## AllowEdit

The [AllowEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~AllowEdit.html) property is used to restrict the editing in `UpDown` control by setting it's value to `False`. The default value is `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" AllowEdit="False" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.AllowEdit = false;

{% endhighligt %}

{% endtabs %}

## Range Adorner

The UpDown control promotes Range adorner features depending on the values entered. You can see the color application based on the range values by allowing the [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~EnableRangeAdorner.html) property and the color will be implemented using the [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~RangeAdornerBackground.html) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="40" RangeAdornerBackground="Red" EnableRangeAdorner="True" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.RangeAdornerBackground = Brushes.Blue;
updown.EnableRangeAdorner = true;

{% endhighlight %}

{% endtabs %}


