---
layout: post
title: Changing Percent Value in WPF PercentTextBox control | Syncfusion
description: Learn here about Changing Percent Value with Syncfusion WPF PercentTextBox control and more details about the control features.
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Changing Percent Value in WPF PercentTextBox

The [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) allows the user to change the percent value using the [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) property.

{%tabs%}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25"
                          Width="150" PercentValue="10"/>

{% endhighlight %}                       
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 10;

{% endhighlight %}
{%endtabs%}

![PercentTextBox displaying a value](Changing-Percent-Value_images/SettingValue.jpeg)

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). By assigning a percent value to the `PercentValue` property by binding, you can change the `PercentTextBox` percent value.

The following code snippets illustrate the percent value binding from one `PercentTextBox` to another.

{%tabs%}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox1" PercentValue="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Height="25" Width="100"/>
<syncfusion:PercentTextBox x:Name="percentTextBox2" PercentValue="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Width="100" Height="25"  />

{% endhighlight %}
{%endtabs%}

ViewModel.cs

{% tabs %}
{% highlight C# %}

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

![Binding a value to PercentTextBox](Changing-Percent-Value_images/ValueBinding.png)

## Change percent value by pasting the clipboard's text

By default, `PercentTextBox` simply replaces the whole value by copied value with the current number format. If you want to replace or insert the copied value on specific place, use the [PasteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PasteMode) property value as `Advanced`. The default value of `PasteMode` property is `Default`. 

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
<td>When a part of the number is selected</td>
<td>If the selected value contains a number decimal separator, then copied value must contain number decimal separator. Otherwise, it won’t perform pasting operation. 

If the selected text does not contain a number decimal separator, then copied value must not contain number decimal separator. Otherwise, it won’t perform pasting operation.</td>
</tr>
</table>

{%tabs%}
{% highlight xaml %}

<syncfusion:PercentTextBox PasteMode="Advanced" 
                           PercentValue="12345.67"
                           Name="percentTextBox"/>

{% endhighlight %}                       
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.PasteMode = PasteMode.Advanced;
percentTextBox.PercentValue = 12345.67;

{% endhighlight %}
{%endtabs%}

![PercentTextBox pasting the copied value in specific place](Changing-Percent-Value_images/Pasting.png)

## Changing percent value by SpinButton

You can increment or decrement the percent value of `PercentTextBox` by setting the `ShowSpinButton` property value as `true`. Click UpButton to increment or DownButton to decrement the percent value. The default value of `ShowSpinButton` property is `false`.

{%tabs%}
{% highlight xaml %}

<syncfusion:PercentTextBox Height="30" Width="150" ShowSpinButton="True" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.ShowSpinButton = true;

{% endhighlight %}
{%endtabs%}

![Changing percent value by SpinButton in PercentTextBox](Changing-Percent-Value_images/SpinButton.gif)

## Value Changed Event

The `PercentTextBox` control can notify changes in percent value through the [PercentValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html) event. In `PercentValueChanged` event, you can get old percent value and new percent value from the `OldValue` and  `NewValue` properties.

{%tabs%}
{% highlight xaml %}

<syncfusion:PercentTextBox PercentValueChanged="PercentTextBox_PercentValueChanged"/>

{% endhighlight %}
{% highlight C# %} 

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.PercentValueChanged += new PropertyChangedCallback(PercentTextBox_PercentValueChanged);

{% endhighlight %}
{%endtabs%}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void PercentTextBox_PercentValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Get old and new percent value
    var newValue = e.NewValue;
    var oldValue = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Setting the Null value

 By default, the `PercentTextBox` control will display zero value when the `PercentValue` is set to `null`. You can use the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show the null or any other percent value instead of zero.
 
 The default value of the `NullValue` property is `null`, you can reset this to any other percent value. It will display only on setting the `UseNullOption` property is set to `true`.
 
**NullValue = Null**

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25"
                          Width="100" UseNullOption="True"  NullValue="{x:Null}"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.NullValue = null;
percentTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![Setting null as NullValue in PercentTextBox](Changing-Percent-Value_images/NullValue_null.png)

**NullValue = 10**

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25"
                          Width="100" UseNullOption="True" NullValue="10"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.NullValue = 10;
percentTextBox.UseNullOption = true;

{% endhighlight %}
{% endtabs %}

![Setting Null value in PercentTextBox](Changing-Percent-Value_images/NullValue.jpeg)

## Setting Watermark Text

We can display certain information within the control by using the [WaterMarkText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkText) property. `WaterMarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextIsVisible) property is `true` and the Percent value is `null` or empty, the control is not in focus and the `UseNullOption` property is `true`.

### Setting the WatermarkText Foreground

The `PercentTextBox` allows you to set the desired brush as a foreground for `WaterMarkText` using [WaterMarkTextForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextForeground) property. The default color of `WaterMarkTextForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100"
                          Height="25" UseNullOption="True" WatermarkText="Type here"
                          WatermarkTextIsVisible="True" WatermarkTextForeground="Red"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.UseNullOption = true;
percentTextBox.WatermarkText = "Type Here";
percentTextBox.WatermarkTextIsVisible = true;
percentTextBox.WatermarkTextForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![PercentTextBox displaying a watermark text in red color](Changing-Percent-Value_images/WaterMark-Foreground.jpeg)

### Setting Watermark Template

You can customize the Visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTemplate) property.

{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25"
                          WatermarkText="Type Here" CornerRadius="3" 
                          WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 
                          UseNullOption="True">
    <syncfusion:PercentTextBox.WatermarkTemplate >
        <DataTemplate>
            <Border Background="Red">
                <TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>
            </Border>
        </DataTemplate>
    </syncfusion:PercentTextBox.WatermarkTemplate>
</syncfusion:PercentTextBox>

{% endhighlight %}

![PercentTextBox displaying watermark text using a data-template](Changing-Percent-Value_images/WaterMark-Template.png)

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WaterMarkText` in `PercentTextBox` control.

N> If both `NullValue` and `WaterMarkText` are specified, you will only see `NullValue` but not `WaterMarkText`.
