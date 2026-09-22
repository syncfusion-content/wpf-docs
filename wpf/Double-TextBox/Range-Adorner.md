---
layout: post
title: Range Adorner in WPF DoubleTextBox | Syncfusion®
description: Visualize the current value within a range using the built-in range adorner of the Syncfusion WPF DoubleTextBox control.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Range Adorner in WPF Double TextBox

The value of `WPF Double TextBox` can be visually indicated like a progress bar using the range adorner feature. This feature is disabled by default. You can show the adorner over the [WPF Double TextBox](https://www.syncfusion.com/wpf-controls/double-textbox) control by setting the [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. The default value of `EnableRangeAdorner` is `false`. The adorner layer fills the control area on the basis of the minimum and maximum values, taking the current `Value` into account. The Range Adorner is not displayed when the `MinValue` or `MaxValue` property is not set. When the `Value` is outside the `[MinValue, MaxValue]` range, the adorner is clamped to the nearest bound.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="63" EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 63;
doubleTextBox.EnableRangeAdorner = true;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays RangeAdorner](Range-Adorner_images/wpf-double-textbox-range-adorner.png)

## Changing the Background of the Range Adorner

You can change the background color of the range adorner using the [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property. The default value of `RangeAdornerBackground` is a light-blue brush.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Windows.Media;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 57;
doubleTextBox.EnableRangeAdorner = true;
doubleTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![Changing Background of RangeAdorner of WPF DoubleTextBox](Range-Adorner_images/wpf-double-textbox-range-adorner-background.png)
