---
layout: post
title: Range Adorner in WPF IntegerTextBox control | Syncfusion®
description: Learn about Range Adorner support in Syncfusion® WPF IntegerTextBox control and more details about the control features.
platform: WPF
control: IntegerTextBox 
documentation: ug
---

# Range Adorner in WPF IntegerTextBox

The [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) of the [IntegerTextBox](https://www.syncfusion.com/wpf-controls/integer-textbox) can be visually indicated like a progress bar using the range adorner feature. This feature is disabled by default. You can show the adorner over the `IntegerTextBox` control by setting the [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. The default value of `EnableRangeAdorner` is `false`. The adorner layer fills the control area on the basis of the minimum and maximum values, taking the current `Value` into account. The Range Adorner is not displayed when the `MinValue` or `MaxValue` property is not set. When the `Value` is outside the `[MinValue, MaxValue]` range, the adorner is clamped to the nearest bound.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Value="63" MinValue="0" MaxValue="100" EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.MinValue = 0;
integerTextBox.MaxValue = 100;
integerTextBox.Value = 63;
integerTextBox.EnableRangeAdorner = true;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Range Adorner](Range-Adorner_images/wpf-integer-textbox-range-adorner.png)

## Changing the Background of the Range Adorner

You can change the background color of the range adorner using the [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property. The default value of `RangeAdornerBackground` is a light-blue brush.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" MinValue="0" MaxValue="100" Value="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Windows.Media;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.MinValue = 0;
integerTextBox.MaxValue = 100;
integerTextBox.Value = 57;
integerTextBox.EnableRangeAdorner = true;
integerTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![Changing Background of RangeAdorner of WPF IntegerTextBox](Range-Adorner_images/wpf-integer-textbox-range-adorner-background.png)
