---
layout: post
title: Orientation in WPF Range Slider control | Syncfusion
description: Learn here all about Orientation support in Syncfusion WPF Range Slider (SfRangeSlider) control and more.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Orientation in WPF Range Slider (SfRangeSlider)

The [Orientation](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~Orientation.html) property has the following two options.  

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

![Horizontal](Orientation_images/Orientation_img1.png)


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

![Vertical](Orientation_images/Orientation_img2.png)



