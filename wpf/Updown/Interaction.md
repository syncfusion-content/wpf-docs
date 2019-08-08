---
layout: post
title: Interaction in WPF UpDown control | WPF | Syncfusion
description: This section explains about keyboard and mouse interaction with WPF UpDown control
platform: wpf
control: UpDown
documentation: ug
---

# Interaction

The WPF [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) controls allow you to change the value by keyboard or mouse interaction, and it also allows you to define increment or decrement when changing the value by MouseWheel or by clicking up and down buttons.

## Keyboard and Mouse support

The WPF `UpDown` control provides keyboard and mouse support to increment or decrement the value in the text box. The keyboard and mouse provide the following supports:

* Mouse wheel - It helps to increase or decrease the current value of the text box by scrolling over WPF UpDown control.

* Up Arrow key - It helps to increase the present value in the text box by the value indicated in the [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property.

* Down Arrow key - It helps to decrease the present value in the text box by the value indicated in the [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property.

## IsScrollingOnCircle

The [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~IsScrollingOnCircle.html) property allows change the value based on click and drag the control in upward or downward direction. 

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

The [Step](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Step.html) property is used to specify the interval to be increased or decreased when clicking the spin buttons in the WPF [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control. For example, the `Step` value is set to 5 so that the WPF `UpDown` control value increases or decreases by 5 when clicking the spin buttons.

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

When the WPF [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) value changes by using the up and down buttons, the textbox animates the transition from the current value to the new value. 

The animation speed value changed in the text portion by up and down buttons of WPF `UpDown` can be controlled by [AnimationSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~AnimationSpeed.html) property. 

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

