---
layout: post
title: Minimum | SfRangeSlider | wpf | Syncfusion
description: This section provides how to use the Minimum and Maximum properties in WPF RangeSlider (SfRangeSlider).
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Minimum and Maximum in WPF RangeSlider(SfRangeSlider)

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
