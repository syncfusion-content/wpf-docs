---
layout: post
title: Changing Double Value| DoubleTextBox  | Wpf | Syncfusion
description: Changing Double Value represents value setting of the control and customization of the Watermark text and it's appearance
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Changing Double Value

## ValueChanged

[ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~ValueChanged_EV.html) – The event occurs when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property of the IntegerTextBox is changed.

{%tabs%}
{% highlight xaml %} <syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/>{% endhighlight %}

{% highlight C# %} IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.ValueChanged += new PropertyChangedCallback(IntegerTextBox_ValueChanged);{% endhighlight %}

{%endtabs%}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when value of IntegerTextBox changes.
}

{% endhighlight %}
{% endtabs %}




## NullValue

### UseNullOption

DoubleTextBox accepts null values. To enable the null option, the [UseNullOption](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~UseNullOption.html) property need to set to `true`. By default its value is `false`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="170" UseNullOption="True" />

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 170;
doubleTextBox.Height = 25;
doubleTextBox.UseNullOption = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 170
doubleTextBox.Height = 25
doubleTextBox.UseNullOption = True

{% endhighlight %}

{% endtabs %}

![Double text box null option](Changing-Double-Value_images/UseNullOption.jpeg)

### Set NullValue

To set the value, when the value of the DoubleTextBox is null the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NullValue.html) property is used. On setting the value to the [NullValue]([NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~NullValue.html)) property, it will assigned to the Value property.

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

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.NullValue = 10

{% endhighlight %}

{% endtabs %}

![Double text box null value](Changing-Double-Value_images/NullValue.jpeg)


## Watermark

## WaterMarkForeground

The DoubleTextBox allows to set the desired brush as the foreground for the WaterMarkText using [WaterMarkTextForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextForeground.html).

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

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.UseNullOption = True
doubleTextBox.WatermarkText = "Type Here"
doubleTextBox.WatermarkTextIsVisible = True
doubleTextBox.WatermarkTextForeground = Brushes.Red

{% endhighlight %}

{% endtabs %}

![WaterMark text foreground](Changing-Double-Value_images/WaterMark-Foreground.jpeg)


[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the Value is null and the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) is true.

### WatermarkTemplate

You can customize the Visual appearance of the WatermarkText by using the [WatermarkTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTemplate.html) property.



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



