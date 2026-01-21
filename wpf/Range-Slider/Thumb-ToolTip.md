---
layout: post
title: Thumb ToolTip in WPF Range Slider Control | Syncfusion®
description: Explore the Thumb ToolTip configurations in the Syncfusion® WPF Range Slider (SfRangeSlider) control, including precision, format, and positioning.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Thumb ToolTip in WPF Range Slider (SfRangeSlider)

The Thumb tooltip in the SfRangeSlider displays the current value at the thumb's position on the slider.

![ToolTip](Thumb-ToolTip_images/Thumb-ToolTip_img1.png)

## Thumb ToolTip Precision  

The [`ThumbToolTipPrecision`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbToolTipPrecision.html) property defines the precision of the value shown in the tooltip.


{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    VerticalAlignment="Center"
                    Maximum="100"
                    Minimum="0"
                    ThumbToolTipPrecision="2"
                    Value="50" />

{% endhighlight %}

{% endtabs %}

![Precision](Thumb-ToolTip_images/Thumb-ToolTip_img2.png)

> **Note**: `ThumbToolTipPrecision` is applicable only if `ToolTipFormat` value is set to "N".

## Thumb ToolTip Format

The [`ToolTipFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfRangeSlider.html#Syncfusion_Windows_Controls_Input_SfRangeSlider_ToolTipFormat) property specifies the format specifier for the tooltip display value.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    ToolTipFormat="C0"
                    Value="50" />

{%endhighlight%}

{%highlight C#%}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ToolTipFormat= C0,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{%endhighlight%}

{% endtabs %}

![Format](Thumb-ToolTip_images/ToolTip-Format.png)

> **Note**: The default value of `ToolTipFormat` is "N".

## Thumb ToolTip Position 

The [`ThumbToolTipPlacement`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbToolTipPlacement.html) property controls the tooltip's position relative to the thumb, offering three options:
1. BottomRight 
2. TopLeft 
3. None 

### BottomRight  

Places the tooltip below the thumb in horizontal orientation and to the right in vertical orientation.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    ThumbToolTipPlacement="BottomRight"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ThumbToolTipPlacement = ThumbToolTipPlacement.BottomRight,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![BottomRight](Thumb-ToolTip_images/Thumb-ToolTip_img4.png)

> **Note**: Displays tooltip to the right in vertical orientation.

### TopLeft 

Places the tooltip above the thumb in horizontal orientation and to the left in vertical orientation.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    ThumbToolTipPlacement="TopLeft"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ThumbToolTipPlacement = ThumbToolTipPlacement.TopLeft,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![TopLeft](Thumb-ToolTip_images/Thumb-ToolTip_img3.png)

> **Note**: Displays tooltip to the left in vertical orientation.

### None 

Disables the tooltip display.
{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    ThumbToolTipPlacement="None"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ThumbToolTipPlacement = ThumbToolTipPlacement.None,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![None](Thumb-ToolTip_images/Thumb-ToolTip_img5.png)

## Thumb Interval

The [`ThumbInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbInterval.html) property defines the interval between two thumbs, preventing movement within this range.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
            Width="300"
            Maximum="100"
            Minimum="0"
            RangeEnd="50"
            RangeStart="20"
            ShowRange="True"
            ThumbInterval="10"
            Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                ShowRange = true,
                RangeStart = 20,
                RangeEnd = 60,
                ThumbInterval = 10,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![ThumbInterval](Thumb-ToolTip_images/Thumb-ToolTip_img6.png)

