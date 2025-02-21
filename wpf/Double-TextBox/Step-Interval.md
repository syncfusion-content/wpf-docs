---
layout: post
title: Step Interval in WPF Double TextBox control | Syncfusion®
description: Learn about Step Interval support in Syncfusion® WPF Double TextBox control, its elements and more details.
platform: WPF
control: DoubleTextBox 
documentation: ug
---

# Step Interval in WPF Double TextBox

The [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) control allows you to increase or decrease the value by pressing up-arrow and down-arrow keys in keyboard or mouse wheel over the control. The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_ScrollInterval) property is used to specify the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, the `ScrollInterval` value is set to 4. So, that the `DoubleTextBox` control [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) increases or decreases by 4 while pressing Up arrow or Down arrow keys and Mouse wheel scrolling up or down.

## Change Value on Up, Down arrow key

The `DoubleTextBox` control allows you to increase or decrease the `Value` of `DoubleTextBox` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="10" ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Changing Value by Up and Down Arrow Key in WPF DoubleTextBox](Step-Interval_images/wpf-double-textbox-value.png)

## Change Value on Mouse Wheel

The `DoubleTextBox` allows you to increase or decrease the `Value` based on the `ScrollInterval` by the Mouse scrolling over the control When the [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Editorbase.html#Syncfusion_Windows_Shared_EditorBase_IsScrollingOnCircle) property is `true`. The default value of `IsScrollingOnCircle` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25" Value ="34" 
                          IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 34;
doubleTextBox.IsScrollingOnCircle = true;
doubleTextBox.ScrollInterval = 3;

{% endhighlight %}
{% endtabs %}

![Changing Value by Mouse Wheel in WPF DoubleTextBox](Step-Interval_images/wpf-double-textbox-changing-value.png)

## Change Value on Click and Drag

The `DoubleTextBox` allows you to increase or decrease the value based on the `ScrollInterval` by clicking and dragging the mouse when the [EnableExtendedScrolling](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableExtendedScrolling) property is `true`. `DoubleTextBox` value increases when you click and drag the mouse to the right or the top of the screen and decreases when the mouse moves to the left or the bottom of the screen. Before that, the control should be in an unfocused state.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="120" Height="25" Value ="10" 
                          ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 120;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.ScrollInterval = 5;
doubleTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Changing Value by Clicking and Drag in WPF DoubleTextBox](Step-Interval_images/wpf-double-textbox-drag-and-drop.gif)

## Allow or restrict selection on focus

`DoubleTextBox` allows you to automatically select text by setting [TextSelectionOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_TextSelectionOnFocus) property to `true` and when the control got focus. If you want to restrict the selection on when control got focus, use the `TextSelectionOnFocus` property value as `false`. The default value of the `TextSelectionOnFocus` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.TextSelectionOnFocus = true;

{% endhighlight %}
{% endtabs %}

**TextSelectionOnFocus = "False"**

![Restrict Text Selection in WPF DoubleTextBox](Step-Interval_images/wpf-double-textbox-restrict-selection.png)

**TextSelectionOnFocus = "True"**

![WPF DoubleTextBox displays Text Selection](Step-Interval_images/wpf-double-textbox-text-selection.png)
