---
layout: post
title: Step Interval | DoubleTextBox  | Wpf | Syncfusion
description: Step Interval represents the customization of the DoubleTextBox value by keyboard buttons and mouse scrolling
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Step Interval

The `DoubletextBox` control allows to increase or decrease the value by pressing up-arrow and down-arrow keys in keyboard or mouse wheel over the control. The `ScrollInterval` property is used to specify the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, the `ScrollInterval` value is set to 4. So, that the `DoubleTextBox` control `Value` increases or decreases by 4 while pressing Up arrow or Down arrow keys and Mouse wheel scrolling up or down.

## Change Value on Up, Down arrow key

The `DoubletextBox` control allows you to increase or decrease the `Value` of `DoubletextBox` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.


{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="10"
                          ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Up-Down arrow key](Step-Interval_images/Step-Interval_Up-Down-arrow-key.png)

## Change Value on Mouse Wheel

The `DoubletextBox` allows you to increase or decrease the `Value` based on the `ScrollInterval` by the Mouse scrolling over the control When the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property is true.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="37" IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 37;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 3;

{% endhighlight %}
{% endtabs %}

![Mouse Wheel](Step-Interval_images/Step-Interval_Mouse-Wheel.png)

## Change Value on Click and Drag

The DoubletextBox allows you to increase or decrease the value based on the `ScrollInterval` by click and dragging the mouse move When the [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is `true`. The `Value` of `DoubleTextBox` will increase when the mouse moves to the right or top of the screen and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="120" Height="25" Value ="93" ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 120;
doubleTextBox.Height = 25;
doubleTextBox.Value = 93;
doubleTextBox.ScrollInterval = 5;
doubleTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Adding extended scrolling to an application](Step-Interval_images/Step-Interval_DragandDrop.jpeg)


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

### TextSelectionOnFocus="False"

![TextSelectionOnFocus](Step-Interval_images/Step-Interval_DragandDrop_SelectionFalse.png)

### TextSelectionOnFocus="True"

![TextSelectionOnFocus](Step-Interval_images/Step-Interval_DragandDrop_SelectionTrue.png)
