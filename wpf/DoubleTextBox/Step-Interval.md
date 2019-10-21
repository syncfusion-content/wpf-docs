---
layout: post
title: Step Interval in WPF DoubleTextBox control | Syncfusion
description: Learn about Step Interval support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Step Interval in WPF DoubleTextBox

The `DoubleTextBox` control allows you to increase or decrease the value within the minumum and maximum value limits by pressing up-arrow and down-arrow keys in keyboard or mouse wheel over the control. The `ScrollInterval` property is used to specify the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, the `ScrollInterval` value is set to 4. So, that the `DoubleTextBox` control `Value` increases or decreases by 4 while pressing Up arrow or Down arrow keys and Mouse wheel scrolling up or down.

## Change Value on Up, Down arrow key

The `DoubleTextBox` control allows you to increase or decrease the `Value` of `DoubleTextBox` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.


{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="10"
                          MinValue="0" MaxValue="100" ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 10;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Changing the DoubleTextBox value by the Up-Down arrow key](Step-Interval_images/Step-Interval_Up-Down-arrow-key.png)

## Change Value on Mouse Wheel

The `DoubleTextBox` allows you to increase or decrease the `Value` based on the `ScrollInterval` by the Mouse scrolling over the control When the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property is true.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="34"
                          MinValue="0" MaxValue="100" Value ="37" IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 34;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 3;

{% endhighlight %}
{% endtabs %}

![Changing the DoubleTextBox value by Mouse Wheel](Step-Interval_images/Step-Interval_Mouse-Wheel.png)

## Change Value on Click and Drag

The `DoubleTextBox` allows you to increase or decrease the value based on the `ScrollInterval` by click and dragging the mouse move When the [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is `true`. The `Value` of `DoubleTextBox` will increase when the mouse moves to the right or top of the screen and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="120" Height="25" Value ="88" 
                          MinValue="0" MaxValue="100" ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 120;
doubleTextBox.Height = 25;
doubleTextBox.MinValue = 0;
doubleTextBox.MaxValue = 100;
doubleTextBox.Value = 88;
doubleTextBox.ScrollInterval = 5;
doubleTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Changing the DoubleTextBox value by Click and Drag](Step-Interval_images/Step-Interval_DragandDrop.jpeg)


## Select All on focus

`DoubleTextBox` allows you to automatically select text by setting [TextSelectionOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~TextSelectionOnFocus.html) property to true and when the control got focus.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.TextSelectionOnFocus = true;

{% endhighlight %}
{% endtabs %}

### TextSelectionOnFocus = "False"

![DoubleTextBox TextSelection On Focus disabled](Step-Interval_images/Step-Interval_TextSelectionFalse.png)

### TextSelectionOnFocus = "True"

![WPF DoubleTextBox TextSelection On Focus enabled](Step-Interval_images/Step-Interval_TextSelectionTrue.png)
