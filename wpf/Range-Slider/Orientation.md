---
layout: post
title: Orientation Settings in WPF Range Slider Control | Syncfusion®
description: Discover how to configure orientation settings for the Syncfusion® WPF Range Slider (SfRangeSlider) control.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Orientation Settings in WPF Range Slider (SfRangeSlider)

The [Orientation](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~Orientation.html) property of the SfRangeSlider allows you to specify its alignment either horizontally or vertically. The default setting is Horizontal.

1. Horizontal  
2. Vertical  

The default option is Horizontal.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    Orientation="Horizontal"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 50,
                Orientation = Orientation.Horizontal
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;;

{% endhighlight %}

{% endtabs %}

![Horizontal Orientation](Orientation_images/Orientation_img1.png)


The following code sample illustrates how to set vertical orientation to [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html).  

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Height="300"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Maximum="100"
                    Minimum="0"
                    Orientation="Vertical"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                Value = 50,
                Orientation = Orientation.Vertical
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;;

{% endhighlight %}

{% endtabs %}

![Vertical Orientation](Orientation_images/Orientation_img2.png)
