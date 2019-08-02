---
layout: post
title: Interaction | UpDown | WPF | Syncfusion
description: This section explains about keyboard and mouse interaction with UpDown control
platform: wpf
control: UpDown
documentation: ug
---

# Interaction

The [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) controls allow you to change the value by keyboard or mouse interaction, and it also allows you to define increment or decrement when changing the value by MouseWheel or by clicking up and down buttons.

## Keyboard and Mouse support

The `UpDown` control provides keyboard and mouse support to increment or decrement the value in the text box. The keyboard and mouse provide the following supports:

* Mouse wheel - It helps to increase or decrease the current value of the text box by the value indicated in the [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property.

* Up Arrow key - It helps to increase the present value in the text box by the value indicated in the [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property.

* Down Arrow key - It helps to decrease the present value in the text box by the value indicated in the [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property.

## IsScrollingOnCircle

The [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~IsScrollingOnCircle.html) property allows the mouse to scroll up and down. This property also allows the mouse to restrict the value that changes by setting its values to `False`. By default, its value is `True`.

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

## Step

The [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property is used to specify the interval to be increased or decreased when clicking the spin buttons in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control. For example, the `Step` value is set to 5 so that the `UpDown` control value increases or decreases by 5 when clicking the spin buttons.

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

## Animation speed

When the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) value changes by using the up and down buttons, the textbox animates the transition from the current value to the new value. 

The animation speed value changed by up and down buttons in the text portion of `UpDown` can be controlled by [AnimationSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~AnimationSpeed.html) property. 

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

* Animation speed = 0.5

![Modified animation speed of WPF UpDown](Interaction_images/Updown_speed1.gif)

* Animation speed = 0.1

![Default animation speed of WPF UpDown](Interaction_images/Updown_speed2.gif)
