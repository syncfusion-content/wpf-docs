---
layout: post
title: Step Interval | DoubleTextBox  | Wpf | Syncfusion
description: Step Interval represents the customization of the DoubleTextBox value by keyboard buttons and mouse scrolling
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Step Interval


## Change Value on Up, Down arrow key

Up or down key arrows allows to spin the values of DoubleTextBox one step up or down. Up or down key arrows allows the DoubleTextBox spin the values one step up or down. This spin behavior in the DoubleTextBox, can be restricted by setting the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property to `false`. By default, its value is `true`.

The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ScrollInterval.html) property is used to set spin value of DoubleTextBox. Based on the [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ScrollInterval.html) value, DoubleTextBox spins up or down.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="10" IsScrollingOnCircle="True" ScrollInterval="2"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 2;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.Value = 10
doubleTextBox.IsScrollingOnCircle = False
doubleTextBox.ScrollInterval = 2

{% endhighlight %}

{% endtabs %}

![Up-Down arrow key](Step-Interval_images/Step-Interval_Up-Down-arrow-key.png)

## Change Value on Mouse Wheel

Mouse Wheel allows to spin the values of DoubleTextBox one step up or down. Mouse Wheel in the DoubleTextBox spin the values one step up or down. This spin behavior in the DoubleTextBox, can be restricted by setting the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property to `false`. By default, its value is `true`.

The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ScrollInterval.html) property is used to set spin value of DoubleTextBox. Based on the [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ScrollInterval.html) value, DoubleTextBox spins up or down.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="35" IsScrollingOnCircle="True" ScrollInterval="2"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 35;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 2;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.Value = 35
doubleTextBox.IsScrollingOnCircle = False
doubleTextBox.ScrollInterval = 2

{% endhighlight %}

{% endtabs %}

![Mouse Wheel](Step-Interval_images/Step-Interval_Mouse-Wheel.png)

## Change Value on Click and Drag

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is used to change the values based on the click and drag direction of the mouse movements. The range will increase when the mouse moves to the right or top of the screen, and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state. The default value is false.

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property must be set either in XAML or the code file.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="120" Height="25" Value ="93" EnableExtendedScrolling="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 120;
doubleTextBox.Height = 25;
doubleTextBox.Value = 93;
doubleTextBox.EnableExtendedScrolling = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 120
doubleTextBox.Height = 25
doubleTextBox.Value = 93
doubleTextBox.EnableExtendedScrolling = True

{% endhighlight %}

{% endtabs %}

![Adding extended scrolling to an application](Step-Interval_images/Step-Interval_DragandDrop.jpeg)


## Select All on focus

The [TextSelectionOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~TextSelectionOnFocus.html) property allows the DoubleTextBox to act like standard text boxes when the cursor hovers over. To restrict this behavior set its value as false. By default the value is true.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.TextSelectionOnFocus = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.TextSelectionOnFocus = True

{% endhighlight %}

{% endtabs %}

### False

![TextSelectionOnFocus](Step-Interval_images/Step-Interval_DragandDrop_SelectionFalse.png)

### True

![TextSelectionOnFocus](Step-Interval_images/Step-Interval_DragandDrop_SelectionTrue.png)
