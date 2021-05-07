---
layout: post
title: Range Adorner in WPF Currency TextBox control | Syncfusion
description: Learn about Range Adorner support in Syncfusion WPF Currency TextBox control, its elements and more details.
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Range Adorner in WPF Currency TextBox

[Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_Value) of [CurrencyTextBox](https://www.syncfusion.com/wpf-ui-controls/currency-textbox) can be visually indicated like a progress bar using range-adorner feature, this feature is disabled by default. You can show the adorner over `CurrencyTextBox` control by setting [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. Default value of `EnableRangeAdorner` is `false`. The adorner layer can be filled in the control area on the basis of the minimum and maximum values with considering the given value. Range Adorner is not displayed when a `MinValue` or `MaxValue` property is not set.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" MinValue="0" MaxValue="100" Value="630"  EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.MinValue = 0;
currencyTextBox.MaxValue = 1000;
currencyTextBox.Value = 630;
currencyTextBox.EnableRangeAdorner =true;

{% endhighlight %}
{% endtabs %}

![CurrencyTextBox default background of Range Adorner ](Range-Adorner_images/Range-Adorner_img1.png)

## Changing background of range-adorner

You can change the background color of the range adorner using [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" MinValue="0" MaxValue="1000" Value="570"  EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.MinValue = 0;
currencyTextBox.MaxValue = 100;
currencyTextBox.Value = 570;
currencyTextBox.EnableRangeAdorner = true;
currencyTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![CurrencyTextBox customized background of Range Adorner ](Range-Adorner_images/Range-Adorner_img2.png)
