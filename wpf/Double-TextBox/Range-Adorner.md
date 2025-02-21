---
layout: post
title: Range Adorner in WPF Double TextBox control | Syncfusion®
description: Learn about Range Adorner support in Syncfusion® WPF Double TextBox control, its elements and more details.
platform: WPF
control: DoubleTextBox 
documentation: ug
---

# Range Adorner in WPF Double TextBox

Value of DoubleTextBox can be visually indicated like a progress bar using range-adorner feature, this feature is disabled by default. You can show the adorner over [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) control by setting [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. default value of `EnableRangeAdorner` is `false`. The adorner layer can be filled in the control area on the basis of the minimum and maximum values with considering the given value. Range Adorner is not displayed when a `MinValue` or `MaxValue` property is not set.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="63" EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 63;
doubleTextBox.EnableRangeAdorner =true;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays RangeAdorner](Range-Adorner_images/wpf-double-textbox-range-adorner.png)

## Changing background of range-adorner

You can change the background color of the range adorner using [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 57;
doubleTextBox.EnableRangeAdorner = true;
doubleTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![Changing Background of RangeAdorner of WPF DoubleTextBox](Range-Adorner_images/wpf-double-textbox-range-adorner-background.png)
