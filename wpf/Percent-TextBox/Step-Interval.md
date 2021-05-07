---
layout: post
title: Step Interval in WPF Percent TextBox control | Syncfusion
description: Learn about Step Interval support in Syncfusion Essential Studio WPF Percent TextBox control, its elements and more details.
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Step Interval in WPF Percent TextBox

The [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) control allows you to increase or decrease the percent value by pressing up-arrow and down-arrow keys in keyboard or mouse wheel over the control. The [ScrollInterval](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_ScrollInterval) property is used to specify the increment or decrement interval. The default value of `ScrollInterval` is 1.

 For example, the `ScrollInterval` value is set to 4. So, that the `PercentTextBox` control [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) increases or decreases by 4 while pressing Up arrow or Down arrow keys and Mouse wheel scrolling up or down.

## Change Value on Up, Down arrow key

The `PercentTextBox` control allows you to increase or decrease the `PercentValue` of `PercentTextBox` based on the `ScrollInterval` by pressing the up arrow and down arrow keys on the keyboard.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150"
                          Height="25" PercentValue ="10" ScrollInterval="2"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 10;
percentTextBox.ScrollInterval = 2;

{% endhighlight %}
{% endtabs %}

![Changing the PercentTextBox percent value by the Up-Down arrow key](Step-Interval_images/Step-Interval_Up-Down-arrow-key.png)

## Change Value on Mouse Wheel

The `PercentTextBox` allows you to increase or decrease the `PercentValue` based on the `ScrollInterval` by the Mouse scrolling over the control When the [IsScrollingOnCircle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Editorbase.html#Syncfusion_Windows_Shared_EditorBase_IsScrollingOnCircle) property is `true`. The default value of `IsScrollingOnCircle` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150" Height="25" PercentValue ="34" 
                          IsScrollingOnCircle="True" ScrollInterval="3"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 34;
percentTextBox.IsScrollingOnCircle = true;
percentTextBox.ScrollInterval = 3;

{% endhighlight %}
{% endtabs %}

![Changing the PercentTextBox percent value by Mouse Wheel](Step-Interval_images/Step-Interval_Mouse-Wheel.png)

## Change Value on Click and Drag

The `PercentTextBox` allows you to increase or decrease the percent value based on the `ScrollInterval` by clicking and dragging the mouse when the [EnableExtendedScrolling](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_EnableExtendedScrolling) property is `true`. `PercentTextBox` percent value increases when the cursor moves to the right or the top of the screen and decreases when you click and drag the mouse to the left or the bottom of the screen. Before that, the control should be in an unfocused state.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="120" Height="25" PercentValue ="10" 
                          ScrollInterval="5" EnableExtendedScrolling="True"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 120;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 10;
percentTextBox.ScrollInterval = 5;
percentTextBox.EnableExtendedScrolling = true;

{% endhighlight %}
{% endtabs %}

![Changing the PercentTextBox percent value by clicking and Drag](Step-Interval_images/Step-Interval_DragandDrop.gif)

## Allow or restrict selection on focus

`PercentTextBox` allows you to automatically select text by setting [TextSelectionOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_TextSelectionOnFocus) property to `true` and when the control got focus.  If you want to restrict the selection on when control got focus, use the `TextSelectionOnFocus` property value as `false`. The default value of the `TextSelectionOnFocus` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.TextSelectionOnFocus = true;

{% endhighlight %}
{% endtabs %}

**TextSelectionOnFocus = "False"**

![PercentTextBox showing TextSelection On Focus disabled](Step-Interval_images/Step-Interval_TextSelectionFalse.png)

**TextSelectionOnFocus = "True"**

![PercentTextBox showing TextSelection On Focus enabled](Step-Interval_images/Step-Interval_TextSelectionTrue.png)
