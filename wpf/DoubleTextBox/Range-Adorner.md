---
layout: post
title: Range Adorner in WPF DoubleTextBox control | Syncfusion
description: Learn about Range Adorner support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Range Adorner in WPF DoubleTextBox 

An Adorner can be used to draw on top of the control. You can show the adorner over `DoubleTextBox` control by setting [EnableRangeAdorner](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableRangeAdorner.html) property to `true`. The default value of `EnableRangeAdorner` is false.The adorner layer can be filled in the control area on the basis of the minimum and maximum values with considering the given value. You can also change the background color of the range adorner using [RangeAdornerBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~RangeAdornerBackground.html) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="57" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new doubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 57;
doubleTextBox.EnableRangeAdorner =true;
doubleTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}
{% endtabs %}

**Default RangeAdornerBackground**

![DoubleTextBox default background of Range Adorner ](Range-Adorner_images/Range-Adorner_img1.png)

**RangeAdornerBackground = "LightGreen"**

![DoubleTextBox customized background of Range Adorner ](Range-Adorner_images/Range-Adorner_img2.png)
