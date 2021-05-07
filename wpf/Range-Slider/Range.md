---
layout: post
title: Range in WPF Range Slider control | Syncfusion
description: Learn here all about Range support in Syncfusion WPF Range Slider (SfRangeSlider) control, its elements and more.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Range in WPF Range Slider (SfRangeSlider)

The [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control provides support to select the range of value using two thumbs.  

## ShowRange  

When ShowRange property is set to true, two thumbs are placed in the track. One thumb is used to update the start of the range selection and another thumb is used to update the end of the range selection.  

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

N> When the `ShowRange` property is set to true, both ToolTip will display RangeStart and RangeEnd. 

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

The `AllowRangeDrag` API allows the range in the Range Slider to be adjusted and the range to be dragged without changing the start and end ranges individually. The default value of `AllowRangeDrag` is false.

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

