---
layout: post
title: Minimum and Maximum in WPF Range Slider control | Syncfusion®
description: Learn here all about Minimum and Maximum support in Syncfusion® WPF Range Slider (SfRangeSlider) control and more.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Minimum and Maximum in WPF Range Slider (SfRangeSlider)

The [WPF Range Slider](https://www.syncfusion.com/wpf-controls/range-slider) supports setting the minimum and maximum possible values of the range. The WPF Range Slider is implemented through the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html) class.

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="500"
                    Maximum="100"
                    Minimum="0" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 500,
                Maximum = 100,
                Minimum = 0
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}
