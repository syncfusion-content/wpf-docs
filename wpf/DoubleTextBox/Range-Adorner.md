---
layout: post
title: Range Adorner| DoubleTextBox  | Wpf | Syncfusion
description: Range Adorner represents to enabling the Range Adorner background to the control and customization of the Range Adorner Background  
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Range Adorner

The [EnableRangeAdorner](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableRangeAdorner.html) property is used to show the adorner range based on the minimum and maximum values given to that control.

![Range Adorner](Range-Adorner_images/Range-Adorner_img1.png)

## Adding Range Adorner 

The [EnableRangeAdorner](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableRangeAdorner.html) property must be set either in XAML or the code file.


{% tabs %}
{% highlight xaml %}  
EnableRangeAdorner="True"
{% endhighlight %}

{% highlight C# %}  
 control.EnableRangeAdorner = true;
 {% endhighlight %}
{% endtabs %}


## Range Adorner Background

The [RangeAdornerBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~RangeAdornerBackground.html) property is used to set the background color of the range adorner. 

![Range adorner background](Range-Adorner_images/Range-Adorner_img2.png)

### Adding Range Adorner background 

The [RangeAdornerBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~RangeAdornerBackground.html) property must be set either in XAML or the code file.


{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" MinValue="0" MaxValue="100" Value="50" EnableRangeAdorner="True" RangeAdornerBackground="LightGreen"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new doubleTextBox();
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 50;
doubleTextBox.EnableRangeAdorner =true;
doubleTextBox.RangeAdornerBackground = Brushes.LightGreen;

{% endhighlight %}

{% endtabs %}

