---
layout: post
title: Minimum and Maximum Settings in WPF Range Slider Control | Syncfusion®
description: Discover how to configure minimum and maximum values in the Syncfusion® WPF Range Slider (SfRangeSlider) control.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Minimum and Maximum Settings in WPF Range Slider (SfRangeSlider)

The `Minimum` and `Maximum` properties in the SfRangeSlider control allow you to define the upper and lower bounds of the range slider.

## Defining Minimum and Maximum Properties

Here is how you can set up these properties using XAML and C#:
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
