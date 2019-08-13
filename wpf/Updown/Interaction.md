---
layout: post
title: Interaction with WPF UpDown control | Syncfusion
description: This section explains about keyboard and mouse interact with WPF UpDown control
platform: wpf
control: UpDown
documentation: ug
---

# Interaction

This section explains about how to change the value by using mouse and keyboard in WPF [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control.

## Keyboard and Mouse support

The `UpDown` control provides to change the value by keyboard or mouse interaction, and it also allows you to define increment or decrement when changing the value by MouseWheel or by clicking up and down buttons.

## Mouse scrolling

When the `IsScrollingOnCircle` property is enabled, the user can increase or decrease the current value of the text box by scrolling over UpDown control.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Width="100" Height="23" IsScrollingOnCircle="True" />

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10;
updown.IsScrollingOnCircle = true;
grid.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

![Change the WPF UpDown value by scrolling the mouse](Interaction_images/wpf-updown-scrolling.gif)

## Step

The [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property is used to specify the interval to be increase or decrease the value when clicking the spin buttons in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control. For example, the `Step` value is set to 5 so that the `UpDown` control value increases or decreases by 5 when clicking the spin buttons.

Another way,

You can also increase or decrease the present value in the text box by using up or down arrow key in keyboard.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Value="10" Width="100" Height="23" Step="5"/>

{% endhighlight %}

{% highlight C# %}

updown.Value = 10;
updown.Width = 100;
updown.Height = 23;
updown.Step = 5;

{% endhighlight %}

{% endtabs %}

![Set the step value to WPF UpDown](Interaction_images/wpf-updown-step.gif)

## Animation speed

When the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) value changes by using the up and down buttons, the textbox animates the transition from the current value to the new value. 

The animation speed value changed in the text portion by up and down buttons of `UpDown` can be controlled by [AnimationSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~AnimationSpeed.html) property. 

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Value="10" AnimationSpeed="0.5" Width="100" Height="23"/>

{% endhighlight %}

{% highlight C# %}

updown.Value = 10;
updown.Width = 100;
updown.Height = 23;
updown.AnimationSpeed = 0.5;

{% endhighlight %}

{% endtabs %}

![Animation speed of WPF UpDown](Interaction_images/wpf-updown-speed1.gif)

## Range Adorner

The UpDown control will indicate value like a progress bar, based on minimum and maximum value specified. You can show the color applied based on the range values by allowing the [EnableRangeAdorner](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~EnableRangeAdorner.html) property and the color of the range can be specified using  [RangeAdornerBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~RangeAdornerBackground.html) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="25" Width="90" Value="40" RangeAdornerBackground="Red" EnableRangeAdorner="True" MinValue="0" MaxValue="100" />

{% endhighlight %}

{% highlight C# %}

updown.RangeAdornerBackground = Brushes.Blue;
updown.EnableRangeAdorner = true;

{% endhighlight %}

{% endtabs %}
