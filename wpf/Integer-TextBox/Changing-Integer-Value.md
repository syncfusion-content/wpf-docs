---
layout: post
title: Changing Integer Value in WPF IntegerTextBox control | Syncfusion
description: Learn here about Changing Integer Value with Syncfusion WPF IntegerTextBox control and more details about the control features.
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Changing Integer Value in WPF IntegerTextBox

The [IntegerTextBox](https://www.syncfusion.com/wpf-ui-controls/integer-textbox) allows the user to change the value using the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) property.

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25"
                          Width="150" Value="10"/>

{% endhighlight %}                       
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 10;

{% endhighlight %}
{%endtabs%}

![IntegerTextBox displaying a value](Changing-Integer-Value_images/SettingValue.png)

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). By assigning a value to the `Value` property by binding, you can change the `IntegerTextBox` value.

The following code snippets illustrate the value binding from one `IntegerTextBox` to another.

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox x:Name="integerTextBox1" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Height="25" Width="100"/>
<syncfusion:IntegerTextBox x:Name="integerTextBox2" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Width="100" Height="25"  />

{% endhighlight %}
{%endtabs%}

ViewModel.cs

{% tabs %}
{% highlight C# %}

class ViewModel : NotificationObject
{
    private int myValue;
    public int MyValue
    {
        get
        {
            return myValue;
        }
        set
        {
            myValue = value;
            RaisePropertyChanged("MyValue");
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Binding a value to IntegerTextBox](Changing-Integer-Value_images/Binding.png)

## Change integer value by pasting the clipboard's text

By default, `IntegerTextBox` simply replaces the whole value by copied value with the current number format. If you want to replace or insert the copied value on specific place, use the [PasteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PasteMode) property value as `Advanced`. The default value of `PasteMode` property is `Default`. 

The following table explains the pasting behaviour in `Advanced` paste mode,

<table>
<tr>
<th> S.No </th>
<th> Action </th>
<th> Pasting behaviour in Advanced paste mode</th>
</tr>
<tr>
<td>1</td>
<td>When the whole value is selected</td>
<td>It simply replaces the whole value by copied value with the current number format.</td>
</tr>
<tr>
<td>2</td>
<td>When the cursor is at some position and the copied value does not contain a number decimal separator</td>
<td>It inserts the copied value into the current cursor position.</td>
</tr>
<tr>
<td>3</td>
<td>When the cursor is at some position and the copied value contains a number decimal separator</td>
<td>It won’t perform pasting operation.</td>
</tr>
<tr>
<td>4</td>
<td>When the cursor is at some position and the control value is 0 or null</td>
<td>It simply replaces the whole value by copied value with the current number format.</td>
</tr>
<tr>
<td>5</td>
<td>When a part of the number is selected and copied value contains number decimal separator</td>
<td> it won’t perform pasting operation.</td>
</tr>
</table>

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox PasteMode="Advanced" 
                           Value="12345"
                           Name="integerTextBox"/>

{% endhighlight %}                       
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.PasteMode = PasteMode.Advanced;
integerTextBox.Value = 12345;

{% endhighlight %}
{%endtabs%}

![IntegerTextBox pasting the copied value in specific place](Changing-Integer-Value_images/Pasting.png)

## Changing integer value by SpinButton

You can increment or decrement the integer value of `IntegerTextBox` by setting the `ShowSpinButton` property value as `true`. Click UpButton to increment or DownButton to decrement the integer value. The default value of `ShowSpinButton` property is `false`.

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox Height="30" Width="150" ShowSpinButton="True" />

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.ShowSpinButton = true;

{% endhighlight %}
{%endtabs%}

![Changing percent value by SpinButton in IntegerTextBox](Changing-Integer-Value_images/SpinButton.gif)

## Value Changed Event

The `IntegerTextBox` control can notify changes in value through the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html) event. In `ValueChanged` event, you can get old value and new value from the `OldValue` and  `NewValue` properties.

{%tabs%}
{% highlight xaml %}

<syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/>

{% endhighlight %}
{% highlight C# %} 

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.ValueChanged += new PropertyChangedCallback(IntegerTextBox_ValueChanged);

{% endhighlight %}
{%endtabs%}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Setting the Null value

 By default, the `IntegerTextBox` control will display zero value when the `Value` is set to `null`. You can use the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show the null or any other value instead of zero.
 
 The default value of the `NullValue` property is `null`, you can reset this to any other integer value. It will display only on setting the `UseNullOption` property is set to `true`.
 
**NullValue = Null**

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25"
                          Width="100" UseNullOption="True"  NullValue="{x:Null}"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 100;
integerTextBox.Height = 25;
integerTextBox.NullValue = null;
integerTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![Setting null as NullValue in IntegerTextBox](Changing-Integer-Value_images/NullValue_null.png)

**NullValue = 10**

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25"
                          Width="100" UseNullOption="True" NullValue="10"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 100;
integerTextBox.Height = 25;
integerTextBox.NullValue = 10;
integerTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![Setting Null value in IntegerTextBox](Changing-Integer-Value_images/NullValue.png)

## Setting Watermark Text

We can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkText) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextIsVisible) property is `true` and the value is `null` or empty, the control is not in focus and the `UseNullOption` property is `true`.

### Setting the WatermarkText Foreground

The `IntegerTextBox` allows you to set the desired brush as a foreground for `WaterMarkText` using [WaterMarkTextForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextForeground) property. The default color of `WaterMarkTextForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="100"
                          Height="25" UseNullOption="True" WatermarkText="Type here"
                          WatermarkTextIsVisible="True" WatermarkTextForeground="Red"/>

{% endhighlight %}
{% highlight C# %}

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 100;
integerTextBox.Height = 25;
integerTextBox.UseNullOption = true;
integerTextBox.WatermarkText = "Type Here";
integerTextBox.WatermarkTextIsVisible = true;
integerTextBox.WatermarkTextForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![IntegerTextBox displaying a watermark text in red color](Changing-Integer-Value_images/WaterMark-Foreground.png)

### Setting Watermark Template

You can customize the Visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTemplate) property.

{% highlight xaml %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="100" Height="25"
                          WatermarkText="Type Here" CornerRadius="3" 
                          WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 
                          UseNullOption="True">
    <syncfusion:IntegerTextBox.WatermarkTemplate >
        <DataTemplate>
            <Border Background="Red">
                <TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>
            </Border>
        </DataTemplate>
    </syncfusion:IntegerTextBox.WatermarkTemplate>
</syncfusion:IntegerTextBox>

{% endhighlight %}

![IntegerTextBox displaying watermark text using a data-template](Changing-Integer-Value_images/WaterMark-Template.png)

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `IntegerTextBox` control.

N> If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.
