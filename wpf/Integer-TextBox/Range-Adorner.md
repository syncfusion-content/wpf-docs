---
layout: post
title: Range Adorner in WPF IntegerTextBox control | Syncfusion
description: Learn about Range Adorner support in Syncfusion WPF IntegerTextBox control and more details about the control features.
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Range Adorner in WPF IntegerTextBox 

[Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) of [IntegerTextBox](https://www.syncfusion.com/wpf-ui-controls/integer-textbox) can be visually indicated like a progress bar using range-adorner feature, this feature is disabled by default. You can show the adorner over `IntegerTextBox` control by setting [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. Default value of `EnableRangeAdorner` is `false`. The adorner layer can be filled in the control area on the basis of the minimum and maximum values with considering the given value.  Range Adorner is not displayed when a `MinValue` or `MaxValue` property is not set.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Value="63" MinValue="0" MaxValue="100" EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.MinValue = 0;
integerTextBox.MaxValue = 100;
integerTextBox.Value = 63;
integerTextBox.EnableRangeAdorner =true;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Range Adorner](Range-Adorner_images/wpf-integer-textbox-range-adorner.png)

## Changing background of range-adorner

You can change the background color of the range adorner using [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" MinValue="0" MaxValue="100" Value="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.MinValue = 0;
integerTextBox.MaxValue = 100;
integerTextBox.Value = 57;
integerTextBox.EnableRangeAdorner = true;
integerTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![Changing Background of RangeAdorner of WPF IntegerTextBox](Range-Adorner_images/wpf-integer-textbox-range-adorner-background.png)
