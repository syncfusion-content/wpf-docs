---
layout: post
title: Touch Support | SfRangeSlider | wpf | Syncfusion
description: This section explains how to move the thumb by tapping or clicking in the Syncfusion WPF SfRangeSlider.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Touch Support in WPF RangeSlider(SfRangeSlider)

[MoveToPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~MoveToPoint.html) API allows the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) to move the thumb by tapping or clicking the track of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html). This property provides the following options:

* MoveToTapPosition
* IncrementBySmallChange
* IncrementByLargeChange
* None

### MoveToTapPosition

To move the thumb of [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) to the tapped position, set the [MoveToPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~MoveToPoint.html) property to MoveToTapPosition, and then tap or click the track of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html). This moves the thumb to the tapped position.

The following code example and screenshot illustrates the above.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="400"
                    LargeChange="10"
                    Maximum="100"
                    Minimum="0"
                    MoveToPoint="MoveToTapPosition"
                    SmallChange="5"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 400,
                Maximum = 100,
                Minimum = 0,
                SmallChange = 5,
                LargeChange = 10,
                MoveToPoint = MovePoint.MoveToTapPosition,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![MoveToTapPosition](Touch-Support_images/Touch-Support_img1.png)

### IncrementBySmallChange

To move the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) thumb based on the SmallChange value, set the [MoveToPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~MoveToPoint.html) property to IncrementBySmallChange, and then tap or click the track of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html). This increments the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) value by the SmallChange value.

The following code example and screenshot illustrates the above.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="400"
                    LargeChange="10"
                    Maximum="100"
                    Minimum="0"
                    MoveToPoint="IncrementBySmallChange"
                    SmallChange="5"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 400,
                Maximum = 100,
                Minimum = 0,
                SmallChange = 5,
                LargeChange = 10,
                MoveToPoint = MovePoint.IncrementBySmallChange,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![IncrementBySmallChange](Touch-Support_images/Touch-Support_img2.png)

### IncrementByLargeChange

To move the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) thumb based on the LargeChange value, set the [MoveToPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider~MoveToPoint.html) property to IncrementByLargeChange, and then tap the track of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html). This increments the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) value by the LargeChange value.

The following code example and screenshot illustrates the above.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="400"
                    LargeChange="10"
                    Maximum="100"
                    Minimum="0"
                    MoveToPoint="IncrementByLargeChange"
                    SmallChange="5"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 400,
                Maximum = 100,
                Minimum = 0,
                SmallChange = 5,
                LargeChange = 10,
                MoveToPoint = MovePoint.IncrementByLargeChange,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![IncrementByLargeChange](Touch-Support_images/Touch-Support_img3.png)


### None

To fix the thumb movement of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html), set the MoveToPoint property to _None_. This does not allow thumb movement of the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html).

The following code example and screenshot illustrates the above.

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="400"
                    LargeChange="10"
                    Maximum="100"
                    Minimum="0"
                    MoveToPoint="None"
                    SmallChange="5"
                    Value="50" />

{% endhighlight %}

{% highlight C# %}

            Grid parentGrid = new Grid();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {   
                Width = 400,
                Maximum = 100,
                Minimum = 0,
                SmallChange = 5,
                LargeChange = 10,
                MoveToPoint = MovePoint.None,
                Value = 50
            };

            parentGrid.Children.Add(rangeSlider);
            this.Content = parentGrid;

{% endhighlight %}

{% endtabs %}

![None](Touch-Support_images/Touch-Support_img4.png)







