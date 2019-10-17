---
layout: post
title: Changing Double Value in WPF DoubleTextBox control | Syncfusion
description: Learn about Changing Double Value support in Syncfusion WPF DoubleTextBox control and more details.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Changing Double Value in WPF DoubleTextBox

The `DoubleTextBox` allows the user to change the value using the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextbox~Value.html) property.

%tabs%}
{% highlight xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="150" Value="10"/>

{% endhighlight %}                       
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;

{% endhighlight %}
{%endtabs%}

![WPF DoubleTextBox setting value](Changing-Double-Value_images/SettingValue.jpeg)


Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target).By assigning a value to the `Value` property by binding, you can change the `DoubleTextBox` value.

%tabs%}
{% highlight xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox1" Grid.Row="1" Height="25" Width="100"/>
<syncfusion:DoubleTextBox x:Name="doubleTextBox2" Grid.Row="3" Width="100" Height="25" Value="{Binding ElementName=doubleTextBox1,Path=Value,Mode=TwoWay}" />

{% endhighlight %}
{%endtabs%}


## Value Changed Event

The `DoubleTextbox` control can notify changes in value through the `ValueChanged` event. In `ValueChanged` event, you can get old value and new value from the `OldValue` and  `NewValue` properties.


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

## Setting Null Value

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

![WPF DoubleTextBox null value](Changing-Double-Value_images/NullValue.jpeg)


## Setting Watermark

We can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) property is `true` and the text is empty, control not in focus and the `UseNullOption` is `true`.

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `DoubleTextBox` control. If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.

### Setting WaterMark Foreground

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

![WPF DoubleTextBox WatermarkText foreground](Changing-Double-Value_images/WaterMark-Foreground.jpeg)


[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the Value is null and the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) is true.

### Setting Watermark Template

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

![WPF DoubleTextBox Watermark template](Changing-Double-Value_images/WaterMark-Template.png)



