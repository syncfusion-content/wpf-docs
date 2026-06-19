---
layout: post
title: Direction Reversed in WPF Range Slider Control | Syncfusion®
description: Discover how to configure Direction Reversed in the Syncfusion® WPF Range Slider (SfRangeSlider) control.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Direction Reversed in WPF Range Slider (SfRangeSlider)

The direction of the increasing value can be altered using the [IsDirectionReversed](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~IsDirectionReversed.html) property. When set to `true`, the direction of increasing value is towards the left in horizontal orientation and downwards in vertical orientation. By default, this property is set to `false`.

## Code Examples

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    IsDirectionReversed="True"
                    Maximum="100"
                    Minimum="0"
                    Value="30" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 30,
                IsDirectionReversed = true
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![DirectionReversed](Direction-Reversed_images/Direction-Reversed_img1.png)



