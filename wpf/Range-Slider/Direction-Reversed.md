---
layout: post
title: Direction Reversed in WPF Range Slider | Syncfusion®
description: Reverse the value progression direction in horizontal or vertical WPF Range Slider orientations using the IsDirectionReversed property.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Direction Reversed in WPF Range Slider (SfRangeSlider)

The [WPF Range Slider](https://www.syncfusion.com/wpf-controls/range-slider) allows you to change the direction of increasing values by using the [IsDirectionReversed](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~IsDirectionReversed.html) property. When this property is set to `True`, the direction of increasing values is toward the left in horizontal orientation and down in vertical orientation. The default value is `false`. The WPF Range Slider is implemented through the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html) class.

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



