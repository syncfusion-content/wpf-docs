---
layout: post
title: Changing Double Value| DoubleTextBox  | Wpf | Syncfusion
description: Changing Double Value represents value setting of the control and customization of the Watermark text and it's appearance
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Changing Double Value

## Value Changed

The `DoubleTextbox` control can notifies the value changes through the `ValueChanged` event. You can get old value and new Value from `OldValue` and `NewValue` properties in `ValueChanged` event.


{%tabs%}
{% highlight xaml %} <syncfusion:DoubleTextBox ValueChanged="DoubleTextBox_ValueChanged"/>{% endhighlight %}

{% highlight C# %} DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValueChanged += new PropertyChangedCallback(DoubleTextBox_ValueChanged);{% endhighlight %}

{%endtabs%}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void DoubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Null Value

The `DoubleTextBox` accepts `null` values. By default, the `DoubleTextBox` control will display zero value when the `Value` is set to `null`. You can change this to display some other  value using the  [NullValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~NullValue.html) property. The [UseNullOption](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~UseNullOption.html) property must be enabled to view the specified `NullValue`. By default `UseNullOption` value is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="150" UseNullOption="True" NullValue="10"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.NullValue = 10;
doubleTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![Double text box null value](Changing-Double-Value_images/NullValue.jpeg)


## Watermark

We can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) property is `true` and the text is empty, control not in focus and the `UseNullOption` is `true`.

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `DoubleTextBox` control. If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.

### WaterMark Foreground

The `DoubleTextBox` allows you to set the desired brush as a foreground for `WaterMarkText` using [WaterMarkTextForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WaterMarkTextForeground.html) property. The default color of `WaterMarkTextForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100"
                          Height="25" UseNullOption="True" WatermarkText="Type here"
                          WatermarkTextIsVisible="True" WatermarkTextForeground="Red"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.UseNullOption = true;
doubleTextBox.WatermarkText = "Type Here";
doubleTextBox.WatermarkTextIsVisible = true;
doubleTextBox.WatermarkTextForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![WaterMark text foreground](Changing-Double-Value_images/WaterMark-Foreground.jpeg)


[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the Value is null and the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) is true.

### Watermark Template

You can customize the Visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTemplate.html) property.



{% highlight xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"

WatermarkText="Type Here" CornerRadius="3" 

WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 

UseNullOption="True">

<syncfusion:DoubleTextBox.WatermarkTemplate>

<DataTemplate>

<Border Background="LightGray">

<TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>

</Border>

</DataTemplate>

</syncfusion:DoubleTextBox.WatermarkTemplate>

</syncfusion:DoubleTextBox>

{% endhighlight %}

![Watermark template](Changing-Double-Value_images/WaterMark-Template.png)



