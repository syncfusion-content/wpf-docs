---
layout: post
title: Configuring Ticks in WPF Range Slider Control | Syncfusion®
description: Discover how to configure ticks in the Syncfusion® WPF Range Slider (SfRangeSlider) control, including frequency, placement, and customization options.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Configuring Ticks in WPF Range Slider (SfRangeSlider)

The SfRangeSlider enables the placement of tick marks along the track, allowing for uniform distribution and customization of tick positioning.
## Tick Frequency 

The [`TickFrequency`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~TickFrequency.html) property defines how many ticks appear along the track, based on defined minimum and maximum values.

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="200"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![TickFrequency](Ticks_images/Ticks_img1.png)

> **Note**: When `SnapsTo` is set to `Ticks`, `TickFrequency` determines the interval between snap points.

## Minor Tick Frequency

The `MinorTickFrequency` property sets the number of minor ticks between each major tick on the track.

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    MinorTickFrequency="3"
                    TickFrequency="10"
                    TickPlacement="BottomRight"
                    Value="40" />

{%endhighlight%}

{%highlight C#%}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 300,
                Maximum = 100,
                Minimum = 0,
                MinorTickFrequency=3,
                TickFrequency = 10,
                TickPlacement=TickPlacement.BottomRight,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{%endhighlight%}

{% endtabs %}

![MinorTickFrequency](Ticks_images/MinorTicks.png)

## Step Frequency  

When the [SnapsTo](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~SnapsTo.html) property is set to StepValues, the [StepFrequency](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~StepFrequency.html) property is used to specify the interval between snap points. 

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="200"
                    VerticalAlignment="Center"
                    Maximum="100"
                    Minimum="0"
                    StepFrequency="20"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                StepFrequency = 20,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

## Snaps To 

The [SnapsTo](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~SnapsTo.html) property determines whether the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) snaps to steps or ticks. Available options for this property are 

1. StepValues 
2. Ticks 


Default option is StepValues and StepFrequency property is used to specify the interval between snap points in this case. When the SnapsTo property is set to Ticks, the TickFrequency property is used to specify the interval between snap points.  

## Tick Placement 

The [TickPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~TickPlacement.html) property is used to determine where to draw tick marks in relation to the track. Available options for this property are 

1. BottomRight 
2. Inline 
3. None 
4. Outside 
5. TopLeft  

The default option is Inline.  

### BottomRight  

Tick marks are placed either below the track in horizontal orientation or right of the track in vertical orientation. 

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    TickPlacement="BottomRight"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.BottomRight,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![BottomRight](Ticks_images/Ticks_img2.png)

N> In Vertical Orientation, this option places the ticks to right side.

### TopLeft  

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation. 

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    TickPlacement="TopLeft"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.TopLeft,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![TopLeft](Ticks_images/Ticks_img3.png)

N> In Vertical Orientation, this option places the ticks to left side. 

### Outside 

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.  

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    TickPlacement="Outside"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.Outside,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![Outside](Ticks_images/Ticks_img4.png)


### Inline 

Ticks are placed inside the track.  

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    TickPlacement="Inline"
                    Value="40" />

{% endhighlight %}

{%highlight C#%}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.Inline,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![Inline](Ticks_images/Ticks_img5.png)

### None 

No Tick mark appears.  

{% tabs %}

{% highlight XAML %}

 <editors:SfRangeSlider
                    Width="300"
                    Maximum="100"
                    Minimum="0"
                    TickFrequency="20"
                    TickPlacement="None"
                    Value="40" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 200,
                Maximum = 100,
                Minimum = 0,
                TickFrequency = 20,
                TickPlacement = Syncfusion.Windows.Controls.Input.TickPlacement.None,
                Value = 40
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![None](Ticks_images/Ticks_img6.png)



