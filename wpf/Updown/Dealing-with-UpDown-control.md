---
layout: post
title: Dealing with UpDown control | UpDown | WPF | Syncfusion
description: The UpDown controls allows to change the value by Keyboard or Mouse interaction.Allows users to increase or decrease the values using spin button interface.
platform: wpf
control: UpDown
documentation: ug
---
The WPF NumericUpDown control restricts input to double values. Allows users to increase or decrease the values using spin button interface.
# Dealing with UpDown Control

`UpDown` controls allows to change the value by Keyboard or Mouse interaction and it also allows to define increment or decrement when change the value by MouseWheel or clicking Up and Down buttons.

## Keyboard and Mouse support

The `UpDown` control provides keyboard and mouse support to increment or decrement the value in the text box. The keyboard and mouse provide the following supports:

* Mouse wheel - It increments or decrements the current value of the text box by the value specified in the `Step` property.
* Up Arrow key - It increments the current value in the text box by the value specified in the `Step` property.
* Down Arrow key - It decrements the current value in the text box by the value specified in the `Step` property.

## IsScrollingOnCircle


The `IsScrollingOnCircle` property allows to scroll the up and down using the mouse. This property also allows to restrict the value changing using the mouse, by setting its values to `False`. By default, its value is `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Width="100" Height="23" IsScrollingOnCircle="True" />

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10;
updown.IsScrollingOnCircle = true;

{% endhighlight %}

{% endtabs %}

## Step value

The `Step` property is used to specify the interval to be incremented or decremented in the `UpDown` control when the repeat buttons are clicked. The `Step` value can be set for the `UpDown` control as shown in the following code example. Here the `Step` value is set to 3 so that the value in the `UpDown` control increases or decreases by 3 on clicking the repeat buttons.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Value="10" Width="100" Height="23" Step="5"/>

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10;
updown.Width = 100;
updown.Height = 23;
updown.Step = 5;
Grid1.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

## Restrict change of value

To restrict the change of the values in the `UpDown` control by canceling the `ValueChanging` event as shown in the following code example. 

{% tabs %}

{% highlight C# %}

void upDown_ValueChanging(object sender, ValueChangingEventArgs e) 
{
    e.Cancel = true; 
}

{% endhighlight %}

{% highlight VB %}

Private Sub upDown_ValueChanging(ByVal sender As Object, ByVal e As ValueChangingEventArgs) 
e.Cancel = True
End Sub

{% endhighlight %}

{% endtabs %}

## AllowEdit

The `AllowEdit` feature allows to restrict the editing in the `UpDown` control by setting its value to `False`. By default its value is `True`.


{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Value="10" Width="100" Height="23" AllowEdit="False"/>

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10;
updown.Width = 100;
updown.Height = 23;
updown.AllowEdit = false;
Grid1.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

## Animation speed

When a value change in the `UpDown` by using the repeat buttons, the transition from the current value to the new value is animated in the TextBox.

Animation speed of Value changed in Text part by Up and Down buttons of `UpDown` can be controlled by `AnimationSpeed` property. 

The `AnimationSpeed` can be set for the `UpDown` control as shown in the following code example.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" AnimationSpeed="30" Width="100" Height="23"/>

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10;
updown.Width = 100;
updown.Height = 23;
updown.AnimationSpeed = 30;
Grid1.Children.Add(updown);

{% endhighlight %}

{% endtabs %}