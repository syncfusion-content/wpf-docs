---
layout: post
title: Minimum and Maximum in WPF Range Slider control | Syncfusion
description: Learn here all about Minimum and Maximum support in Syncfusion WPF Range Slider (SfRangeSlider) control and more.
platform: wpf
control: SfRangeSlider 
 documentation: ug
---

# Minimum and Maximum in WPF Range Slider (SfRangeSlider)

Gets or sets the minimum and maximum possible value of the range.

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
