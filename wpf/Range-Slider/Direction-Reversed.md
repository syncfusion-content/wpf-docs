---
layout: post
title: Direction Reversed | SfRangeSlider | wpf | Syncfusion
description: This section provides how to use DirectionReversed property in Syncfusion WPF RangeSlider (SfRangeSlider).   
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# DirectionReversed in WPF RangeSlider(SfRangeSlider)   

The direction of increasing value can be changed using [IsDirectionReversed](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~IsDirectionReversed.html) property. When this property is set to True, the direction of increasing value is towards left in the horizontal orientation and down in the vertical orientation. The default is false. 

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



