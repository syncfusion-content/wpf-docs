---
layout: post
title: Changing Integer Value in WPF IntegerTextBox | Syncfusion®
description: Update the integer value of the Syncfusion WPF IntegerTextBox control programmatically, by spinner buttons, or via keyboard interactions.
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Changing Integer Value in WPF IntegerTextBox

The [IntegerTextBox](https://www.syncfusion.com/wpf-controls/integer-textbox) allows the user to change the value using the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_Value) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25"
                          Width="150" Value="10"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 10;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Value](Changing-Integer-Value_images/wpf-integer-textbox-value.png)

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). By assigning a value to the `Value` property by binding, you can change the `IntegerTextBox` value.

The following code snippets illustrate the value binding from one `IntegerTextBox` to another.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox1" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Height="25" Width="100"/>
<syncfusion:IntegerTextBox x:Name="integerTextBox2" Value="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Width="100" Height="25"  />

{% endhighlight %}
{% endtabs %}

ViewModel.cs

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

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

![WPF IntegerTextBox with Binding Value](Changing-Integer-Value_images/wpf-integer-textbox-binding-value.png)

## Change integer value by pasting the clipboard's text

By default, `IntegerTextBox` simply replaces the whole value with the copied value using the current number format. If you want to replace or insert the copied value at a specific place, set the [PasteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PasteMode) property to `Advanced`. The default value of `PasteMode` is `Default`. In `Advanced` mode, the pasted value is treated as an integer and any decimal portion is rejected.

The following table explains the pasting behavior in `Advanced` paste mode for integer values:

<table>
<tr>
<th> S.No </th>
<th> Action </th>
<th> Pasting behaviour in Advanced paste mode</th>
</tr>
<tr>
<td>1</td>
<td>When the whole value is selected</td>
<td>The copied integer value replaces the whole value with the current number format.</td>
</tr>
<tr>
<td>2</td>
<td>When the cursor is at some position and the copied value is a valid integer</td>
<td>The copied integer is inserted at the current cursor position.</td>
</tr>
<tr>
<td>3</td>
<td>When the cursor is at some position and the copied value is not a valid integer (for example, contains a decimal separator, letters, or exceeds the <code>Int64</code> range)</td>
<td>The paste operation is not performed.</td>
</tr>
<tr>
<td>4</td>
<td>When the cursor is at some position and the control value is 0 or null</td>
<td>The copied value replaces the whole value with the current number format.</td>
</tr>
<tr>
<td>5</td>
<td>When a part of the number is selected and the copied value is not a valid integer</td>
<td>The paste operation is not performed.</td>
</tr>
<tr>
<td>6</td>
<td>When the copied value falls outside the configured <code>MinValue</code> or <code>MaxValue</code> range</td>
<td>The paste operation is not performed.</td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox PasteMode="Advanced"
                           Value="12345"
                           Name="integerTextBox"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.PasteMode = PasteMode.Advanced;
integerTextBox.Value = 12345;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Pasting Copied Value in Specific Place](Changing-Integer-Value_images/wpf-integer-textbox-paste-value.png)

## Show UpDown Button

You can increment or decrement the integer value of `IntegerTextBox` by setting the `ShowSpinButton` property to `true`. Click the Up button to increment or the Down button to decrement the integer value. The default value of `ShowSpinButton` is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox Height="30" Width="150" ShowSpinButton="True" />

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.ShowSpinButton = true;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays SpinButton](Changing-Integer-Value_images/wpf-integer-textbox-spinbutton.gif)

## Value Changed Eventnotifies value changes through the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html) event. In the `ValueChanged` event, you can get the old value and new value from the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.ValueChanged += new PropertyChangedCallbackHandler(IntegerTextBox_ValueChanged);

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

using System.Windows;

private void IntegerTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Setting the Null value

 By default, the `IntegerTextBox` control will display a zero value when the `Value` is set to `null`. You can use the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show a null or any other value instead of zero.

 The default value of the `NullValue` property is `null`; you can reset it to any other integer value. The `NullValue` is displayed only when the `UseNullOption` property is set to `true`. The default value of `UseNullOption` is `falsws.Shared.IntegerTextBox.html#Syncfusion_Windows_Shared_IntegerTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show the null or any other value instead of zero.
 
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

![WPF IntegerTextBox displays Empty Value](Changing-Integer-Value_images/wpf-integer-textbox-empty-value.png)

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

![WPF IntegerTextBox with Null Value](Changing-Integer-Value_images/wpf-integer-textbox-null-value.png)

## Setting Watermark Text

You can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkText) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextIsVisible) property is `true`, the value is `null` or empty, the control is not in focus, and the `UseNullOption` property is `true`.

### Setting the WatermarkText Foreground

The `IntegerTextBox` allows you to set the desired brush as a foreground for `WaterMarkText` using the [WaterMarkTextForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextForeground) property. The default color of `WaterMarkTextForeground` is `Black`. The default value of `WatermarkTextIsVisible` is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="100"
                          Height="25" UseNullOption="True" WatermarkText="Type here"
                          WatermarkTextIsVisible="True" WatermarkTextForeground="Red"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Windows.Media;

IntegerTextBox integerTextBox = new IntegerTextBox();
integerTextBox.Width = 100;
integerTextBox.Height = 25;
integerTextBox.UseNullOption = true;
integerTextBox.WatermarkText = "Type Here";
integerTextBox.WatermarkTextIsVisible = true;
integerTextBox.WatermarkTextForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![WPF IntegerTextBox displays Watermark Text in Red Color](Changing-Integer-Value_images/wpf-integer-textbox-watermark.png)

### Setting Watermark Template

You can customize the visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTemplate) property. Use the [WatermarkOpacity](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkOpacity) property to adjust the opacity of the watermark. The default value of `WatermarkOpacity` is `1`.

{% highlight XAML %}

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

![Customizing Watermark Text in WPF IntegerTextBox](Changing-Integer-Value_images/wpf-integer-textbox-watermark-customization.png)

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `IntegerTextBox`.

N> If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.
