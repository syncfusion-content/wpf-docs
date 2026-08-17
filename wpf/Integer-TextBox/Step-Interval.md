---
layout: post
title: Step Interval in WPF IntegerTextBox control | Syncfusion®
description: Learn about Step Interval support in Syncfusion® WPF IntegerTextBox control and more details about the control features.
platform: WPF
control: IntegerTextBox
documentation: ug
---

# Step Interval in WPF IntegerTextBox

The [IntegerTextBox](https://www.syncfusion.com/wpf-controls/integer-textbox) control allows you to increase or decrease the value by pressing the up and down arrow keys on the keyboard or by scrolling the mouse wheel over the control. The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_ScrollInterval) property specifies the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, if the `ScrollInterval` value is set to 4, the `IntegerTextBox` control [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) increases or decreases by 4 while pressing the Up arrow or Down arrow keys and mouse wheel scrolling up or down.

## Change Value on Up, Down Arrow Key

The `IntegerTextBox` control allows you to increase or decrease the `Value` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150"
                          Height="25" Value="10" ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 10;
integerTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Changing Value by Up and Down Arrow Key in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-value.png)

## Change Value on Mouse Wheel

The `IntegerTextBox` allows you to increase or decrease the `Value` based on the `ScrollInterval` when scrolling the mouse wheel over the control. This is enabled when the [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_IsScrollingOnCircle) property is `true`. The default value of `IsScrollingOnCircle` is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" Value="34"
                          IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 34;
integerTextBox.IsScrollingOnCircle = true;
integerTextBox.ScrollInterval = 3;

{% endhighlight %}
{% endtabs %}

![Changing Value by Mouse Wheel in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-change-value.png)

## Change Value on Click and Drag

The `IntegerTextBox` allows you to increase or decrease the value based on the `ScrollInterval` by clicking and dragging the mouse when the [EnableExtendedScrolling](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableExtendedScrolling) property is `true`. The `IntegerTextBox` value increases when you click and drag the mouse to the right or top of the screen, and decreases when you click and drag the mouse to the left or bottom of the screen. Before that, the control should be in an unfocused state. The default value of `EnableExtendedScrolling` is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="120" Height="25" Value="10"
                          ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 120;
integerTextBox.Height = 25;
integerTextBox.Value = 10;
integerTextBox.ScrollInterval = 5;
integerTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Changing Value by Clicking and Drag in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-drag-and-drop.gif)

## Allow or Restrict Selection on Focus

`IntegerTextBox` allows you to automatically select the text when the control receives focus, by setting the [TextSelectionOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_TextSelectionOnFocus) property to `true`. If you want to restrict selection when the control receives focus, set `TextSelectionOnFocus` to `false`. The default value of `TextSelectionOnFocus` is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.TextSelectionOnFocus = false;

{% endhighlight %}
{% endtabs %}

**TextSelectionOnFocus = "False"**

![Restrict Text Selection in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-restrict-selection.png)

**TextSelectionOnFocus = "True"**

![WPF IntegerTextBox displays Text Selection](Step-Interval_images/wpf-integer-textbox-text-selection.png)
