---
layout: post
title: Range Management in WPF Range Slider Control | Syncfusion®
description: Discover how to manage ranges in the Syncfusion® WPF Range Slider (SfRangeSlider) control, including configuration and draggable range features.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Range Management in WPF Range Slider (SfRangeSlider)

The [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control supports selecting a range of values using two thumbs for precision.

## ShowRange  

When the `ShowRange` property is set to `true`, the SfRangeSlider displays two thumbs on the track, allowing users to define both the start and end of the range.
{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    RangeEnd="70"
                    RangeStart="40"
                    ShowRange="True" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ShowRange = true,
                RangeStart = 40,
                RangeEnd = 70
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![ShowRange](Range_images/Range_img1.png)

> **Note**: When `ShowRange` is enabled, tooltips will display both `RangeStart` and `RangeEnd`.

## RangeStart  

Gets or sets the start value of the range start.  

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    RangeEnd="70"
                    RangeStart="40"
                    ShowRange="True" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ShowRange = true,
                RangeStart = 40,
                RangeEnd = 70
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![RangeStart](Range_images/Range_img2.png)

## RangeEnd 

Gets or sets the end value of the range end.  

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    RangeEnd="70"
                    RangeStart="40"
                    ShowRange="True" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ShowRange = true,
                RangeStart = 40,
                RangeEnd = 70
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![RangeEnd](Range_images/Range_img3.png)

## Drag Selected Range

The `AllowRangeDrag` property enables dragging the range as a whole, without changing the start and end values individually. Its default value is `false`.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    AllowRangeDrag="True"
                    Maximum="100"
                    Minimum="0"
                    RangeEnd="20"
                    RangeStart="0"
                    ShowRange="True"
                    ShowValueLabels="True"
                    TickFrequency="20" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ShowRange = true,
                RangeStart = 0,
                RangeEnd = 20,
                ShowValueLabels = true,
                TickFrequency = 20,
                AllowRangeDrag = true
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![Drag Range](Range_images/RangeSlider.gif)

