---
layout: post
title: Step Interval in  control | Syncfusion®
description: Learn about Step Interval support in Syncfusion® WPF IntegerTextBox control and more details about the control features.WPF IntegerTextBox
platform: WPF
control: IntegerTextBox 
documentation: ug
---

# Step Interval in WPF IntegerTextBox

The [IntegerTextBox](https://www.syncfusion.com/wpf-ui-controls/integer-textbox) control allows you to increase or decrease the value by pressing up-arrow and down-arrow keys in keyboard or mouse wheel over the control. The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_ScrollInterval) property is used to specify the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, the `ScrollInterval` value is set to 4. So, that the `IntegerTextBox` control [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) increases or decreases by 4 while pressing Up arrow or Down arrow keys and Mouse wheel scrolling up or down.

## Change Value on Up, Down arrow key

The `IntegerTextBox` control allows you to increase or decrease the `Value` of `IntegerTextBox` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150"
                          Height="25" Value ="10" ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 10;
integerTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Changing Value by Up and Down Arrow Key in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-value.png)

## Change Value on Mouse Wheel

The `IntegerTextBox` allows you to increase or decrease the `Value` based on the `ScrollInterval` by the Mouse scrolling over the control When the [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Editorbase.html#Syncfusion_Windows_Shared_EditorBase_IsScrollingOnCircle) property is `true`. The default value of `IsScrollingOnCircle` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" Value ="34" 
                          IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

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

The `IntegerTextBox` allows you to increase or decrease the value based on the `ScrollInterval` by clicking and dragging the mouse when the [EnableExtendedScrolling](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableExtendedScrolling) property is `true`. `IntegerTextBox` value increases when the cursor moves to the right or the top of the screen and decreases when you click and drag the mouse to the left or the bottom of the screen. Before that, the control should be in an unfocused state.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="120" Height="25" Value ="10" 
                          ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 120;
integerTextBox.Height = 25;
integerTextBox.Value = 10;
integerTextBox.ScrollInterval = 5;
integerTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Changing Value by Clicking and Drag in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-drag-and-drop.gif)

## Allow or restrict selection on focus

`IntegerTextBox` allows you to automatically select text by setting [TextSelectionOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_TextSelectionOnFocus) property to `true` and when the control got focus. If you want to restrict the selection on when control got focus, use the `TextSelectionOnFocus` property value as `false`. The default value of the `TextSelectionOnFocus` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.TextSelectionOnFocus = true;

{% endhighlight %}
{% endtabs %}

### TextSelectionOnFocus = "False"

![Restrict Text Selection in WPF IntegerTextBox](Step-Interval_images/wpf-integer-textbox-restrict-selection.png)

### TextSelectionOnFocus = "True"

![WPF IntegerTextBox displays Text Selection](Step-Interval_images/wpf-integer-textbox-text-selection.png)
