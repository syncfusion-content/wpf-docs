---
layout: post
title: Changing Double Value in WPF DoubleTextBox | Syncfusion®
description: Update the double value of the Syncfusion WPF DoubleTextBox control programmatically, by spinner buttons, or via keyboard interactions.
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Changing Double Value in WPF Double TextBox

The [WPF Double TextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) allows the user to change the value using the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="150" Value="10"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays Value](Changing-Double-Value_images/wpf-double-textbox-value.jpeg)

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). By assigning a value to the `Value` property by binding, you can change the `WPF Double TextBox` value.

The following code snippets illustrate the value binding from one `WPF Double TextBox` to another.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox1" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Height="25" Width="100"/>
<syncfusion:DoubleTextBox x:Name="doubleTextBox2" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Width="100" Height="25"  />

{% endhighlight %}
{% endtabs %}

ViewModel.cs

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

class ViewModel : NotificationObject
{
    private double myValue;
    public double MyValue
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

![WPF DoubleTextBox displays Binding Value](Changing-Double-Value_images/wpf-double-textbox-binding-value.png)

## Change double value by pasting the clipboard's text

By default, `WPF Double TextBox` simply replaces the whole value with the copied value using the current number format. If you want to replace or insert the copied value at a specific place, set the [PasteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PasteMode) property to `Advanced`. The default value of `PasteMode` is `Default`.

The following table explains the pasting behavior in `Advanced` paste mode:

<table>
<tr>
<th> S.No </th>
<th> Action </th>
<th> Pasting behaviour in Advanced paste mode</th>
</tr>
<tr>
<td>1</td>
<td>When the whole value is selected</td>
<td>It simply replaces the whole value with the copied value using the current number format.</td>
</tr>
<tr>
<td>2</td>
<td>When the cursor is at some position and the copied value does not contain a number decimal separator</td>
<td>It inserts the copied value into the current cursor position.</td>
</tr>
<tr>
<td>3</td>
<td>When the cursor is at some position and the copied value contains a number decimal separator</td>
<td>The paste operation is not performed.</td>
</tr>
<tr>
<td>4</td>
<td>When the cursor is at some position and the control value is 0 or null</td>
<td>It simply replaces the whole value with the copied value using the current number format.</td>
</tr>
<tr>
<td>5</td>
<td>When a part of the number is selected</td>
<td>If the selected value contains a number decimal separator, then the copied value must contain a number decimal separator. Otherwise, the paste operation is not performed.

If the selected text does not contain a number decimal separator, then the copied value must not contain a number decimal separator. Otherwise, the paste operation is not performed.</td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox PasteMode="Advanced"
                           Value="12345.67"
                           Name="doubleTextBox"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.PasteMode = PasteMode.Advanced;
doubleTextBox.Value = 12345.67;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays Pasting Copied Value in Specific Place](Changing-Double-Value_images/wpf-double-textbox-paste-value.png)

## Show UpDown Button

You can increment or decrement the double value of `WPF Double TextBox` by setting the `ShowSpinButton` property to `true`. Click the Up button to increment or the Down button to decrement the double value. The default value of `ShowSpinButton` is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox Height="30" Width="150" ShowSpinButton="True" />

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ShowSpinButton = true;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays SpinButton](Changing-Double-Value_images/wpf-double-textbox-spin-button.gif)

## Value Changed Event

The `WPF Double TextBox` control notifies value changes through the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html) event. In the `ValueChanged` event, you can get the old value and new value from the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox ValueChanged="DoubleTextBox_ValueChanged"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValueChanged += new PropertyChangedCallbackHandler(DoubleTextBox_ValueChanged);

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

using System.Windows;

private void DoubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Setting the Null value

 By default, the `WPF Double TextBox` control will display a zero value when the `Value` is set to `null`. You can use the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show a null or any other value instead of zero.

 The default value of the `NullValue` property is `null`; you can reset it to any other double value. The `NullValue` is displayed only when the `UseNullOption` property is set to `true`. The default value of `UseNullOption` is `false`.
 
**NullValue = Null**

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="100" UseNullOption="True"  NullValue="{x:Null}"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.NullValue = null;
doubleTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays Empty Value](Changing-Double-Value_images/wpf-double-textbox-empty-value.png)

**NullValue = 10**

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25"
                          Width="100" UseNullOption="True" NullValue="10"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.NullValue = 10;
doubleTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox displays Null Value](Changing-Double-Value_images/wpf-double-textbox-null-value.jpeg)

## Setting Watermark Text

You can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkText) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextIsVisible) property is `true`, the value is `null` or empty, the control is not in focus, and the `UseNullOption` property is `true`.

### Setting the WatermarkText Foreground

The `WPF Double TextBox` allows you to set the desired brush as a foreground for `WaterMarkText` using the [WaterMarkTextForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextForeground) property. The default color of `WaterMarkTextForeground` is `Black`. The default value of `WatermarkTextIsVisible` is `true`.

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

![WPF DoubleTextBox displays Watermark Text](Changing-Double-Value_images/wpf-double-textbox-watermark.jpeg)

### Setting Watermark Template

You can customize the visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTemplate) property. Use the [WatermarkOpacity](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkOpacity) property to adjust the opacity of the watermark. The default value of `WatermarkOpacity` is `1`.

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25"
                          WatermarkText="Type Here" CornerRadius="3"
                          WatermarkTextIsVisible="True" WatermarkOpacity="0.5"
                          UseNullOption="True">
    <syncfusion:DoubleTextBox.WatermarkTemplate >
        <DataTemplate>
            <Border Background="Red">
                <TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>
            </Border>
        </DataTemplate>
    </syncfusion:DoubleTextBox.WatermarkTemplate>
</syncfusion:DoubleTextBox>

{% endhighlight %}

![Customizing Watermark Text in WPF DoubleTextBox](Changing-Double-Value_images/wpf-double-textbox-watermark-customization.png)

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `WPF Double TextBox` control. 

N> If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.
