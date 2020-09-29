---
layout: post
title: Thumb ToolTip | SfRangeSlider | wpf | Syncfusion
description: This section explains how to set the ToolTip placement and ToolTip precision in the Syncfusion WPF SfRangeSlider..
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Thumb ToolTip in WPF RangeSlider(SfRangeSlider) 

The Thumb tooltip displays the current value where the Thumb stands. 

![ToolTip](Thumb-ToolTip_images/Thumb-ToolTip_img1.png)

## Thumb ToolTip Precision  

[ThumbToolTipPrecision](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbToolTipPrecision.html) property is used to define the precision of the value displayed in the tooltip.  


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

N> ThumbToolTipPrecision property is only applicable, if ToolTipFormat value is N.


## Thumb ToolTipFormat

The `ToolTipFormat` property, specifies the format specifier by which to format the ToolTip display value. 


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


N> Default value of `ToolTipFormat` is N.


## Thumb ToolTip Position 

The position of the Thumb tooltip in relation to the Thumb can be controlled by the [ThumbToolTipPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbToolTipPlacement.html) property. It has the following options.  

1. BottomRight 
2. TopLeft 
3. None 

### BottomRight  

Tooltip is placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation. 

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


N> This option displays the tooltip to right in vertical orientation.

### TopLeft 

Tooltip is placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation. 

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

N> This option displays the tooltip to left in vertical orientation.

### None 

No Tooltip appears. 

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

## ThumbInterval

[ThumbInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~ThumbInterval.html) is an interval between the two thumbs, the thumbs cannot be moved within this range.

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

