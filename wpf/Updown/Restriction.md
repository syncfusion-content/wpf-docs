---
layout: post
title: Restriction | UpDown | WPF | Syncfusion
description: This section describes about how to set the Value and restrict the maximum and minimum value for UpDown
platform: wpf
control: UpDown
documentation: ug
---

# Restriction

The value for `UpDown` can be specified using the Value property. 

## Value

You can get the current value or change the it using  [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Value.html) property of [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control. A value can be set for the UpDown control as shown in the following code example.

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

The UpDown control notifies the value changes through [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~ValueChanged_EV.html) and [ValueChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~ValueChanging_EV.html) events. You can use the `OldValue` and `NewValue` property to get the old and new value in `ValueChanged` event. In `ValueChanging` event, you can use the `Cancel` property in event argument to avoid the changes.

{% tabs %}

{% highlight C# %}

updown.ValueChanged += Up_ValueChanged;
updown.ValueChanging += Up_ValueChanging;

private void Up_ValueChanging(object sender, ValueChangingEventArgs e)
{
    // To cancel the change
    e.Cancel = true;            
}

private void Up_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}

{% endtabs %}

## Null value

The [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control accepts null value.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="{x:Null}" />

{% endhighlight %}

{% highlight C# %}

updown.Value = null;

{% endhighlight %}

{% endtabs %}

![Shows before set the null value in WPF UpDown](Restriction_images/Updown_beforenull.png)

When value is set to null, `UpDown` control will show zero value by default. You can change this to display some other numerical value using 
[NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NullValue.html) property. The [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~UseNullOption.html) property must be enabled to see the `NullValue` specified.


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

The [NullValueText](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NullValueText.html) property enables the `UpDown` control to show watermark text instead of numeric value when  [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Value.html) is null. The [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~UseNullOption.html) property must be enabled to see the `NullValue` specified.

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


N> The `UseNullOption` property must be enabled if you want to see the `NullValue` or `NullValueText` in UpDown command. If both `NullValue` and `NullValueText` is specified, you will see only `NullValue` but not `NullValueText`.


## Minimum and Maximum value

The Value of `UpDown` control can be restricted within maximum and minimum limit. The spin button helps to increase or decrease the value by using mouse interaction. Once the increase or decrease value reached the predefined maximized or minimized value, the value does not change.

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

You can choose when to validate the maximum and minimum limit, while changing the values by using [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) and [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) property.

* **OnKeyPress** - On setting the [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) or [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) to OnKeyPress, then the value in the UpDown control is validated soon after a key is pressed. So, it is not possible to provide any invalid input at all.

* **OnLostFocus** - On setting the [MaxValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MaxValidation.html) or [MinValidation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~MinValidation.html) to OnLostFocus, then the value in the UpDown control is validated when the UpDown control loses focus. That is, `UpDown` will accept any value, validation will be happen only after control loose its keyboard focus. After validation, when the value of the UpDown control is greater than the MaxValue or lesser than the MinValue, the value will be changed automatically is set to MaxValue or MinValue respectively.

* **MaxValueOnExceedMaxDigit** - When you give input greater than specified maximum limt, `MaxValueOnExceedMaxDigit` property will decide either it should retain the old value or reset to maximum limit that is specified. For example, if `MaxValue` is set to 100 and you are trying to input 200. Value will changed to 100 when `MaxValueOnExceedMaxDigit` is enabled. When `MaxValueOnExceedMaxDigit` is falue, 20 will be retained and last entered 0 will be ignored.

* **MinValueOnExceedMinDigit** - Similarly, When you give input lesser than specified minimum limt, `MinValueOnExceedMinDigit` property will decide either it should retain the old value or reset to minimum limit that is specified.

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

The UpDown control will indicate value like a progress bar, based on minimum and maximum value specified. You can see the color applied based on the range values by allowing the [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~EnableRangeAdorner.html) property and the color of the range can be specified using  [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~RangeAdornerBackground.html) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="40" RangeAdornerBackground="Red" EnableRangeAdorner="True" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.RangeAdornerBackground = Brushes.Blue;
updown.EnableRangeAdorner = true;

{% endhighlight %}

{% endtabs %}


