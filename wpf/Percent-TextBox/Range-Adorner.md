---
layout: post
title: Range Adorner in WPF Percent TextBox control | Syncfusion
description: Learn about Range Adorner support in Syncfusion WPF Percent TextBox control and more.
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Range Adorner in WPF Percent TextBox

[Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html) of [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) can be visually indicated like a progress bar using range-adorner feature, this feature is disabled by default. You can show the adorner over `PercentTextBox` control by setting [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableRangeAdorner) property to `true`. default value of `EnableRangeAdorner` is `false`. The adorner layer can be filled in the control area on the basis of the minimum and maximum values with considering the given value. Range Adorner is not displayed when a `MinValue` or `MaxValue` property is not set.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" MinValue="0" PercentValue="63" MaxValue="100" EnableRangeAdorner="True" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.MinValue = 0;
percentTextBox.MaxValue = 100;
percentTextBox.PercentValue = 63;
percentTextBox.EnableRangeAdorner =true;

{% endhighlight %}
{% endtabs %}

![PercentTextBox default background of Range Adorner ](Range-Adorner_images/Range-Adorner_img1.png)

## Changing background of range-adorner

You can change the background color of the range adorner using [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_RangeAdornerBackground) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" MinValue="0" MaxValue="100" PercentValue="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.MinValue = 0;
percentTextBox.MaxValue = 100;
percentTextBox.PercentValue = 57;
percentTextBox.EnableRangeAdorner = true;
percentTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

![PercentTextBox customized background of Range Adorner ](Range-Adorner_images/Range-Adorner_img2.png)
