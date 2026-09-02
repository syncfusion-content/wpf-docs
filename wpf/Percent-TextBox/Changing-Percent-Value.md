---
layout: post
title: Changing Percent Value in WPF PercentTextBox | Syncfusion®
description: Update the percent value of the Syncfusion WPF PercentTextBox control programmatically, by spinner buttons, or via keyboard interactions.
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Changing Percent Value in WPF Percent TextBox

The [WPF Percent TextBox](https://www.syncfusion.com/wpf-controls/percent-textbox) allows the user to change the percent value using the [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) property.

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

![WPF PercentTextBox displays Value](Changing-Percent-Value_images/wpf-percent-textbox-value.jpeg)

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). By assigning a percent value to the `PercentValue` property by binding, you can change the `WPF Percent TextBox` percent value.

The following code snippets illustrate the percent value binding from one `WPF Percent TextBox` to another. To make the binding work, set the `DataContext` of the Window to an instance of `ViewModel` (for example, `DataContext = new ViewModel()` in the code-behind).

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox1" PercentValue="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Height="25" Width="100"/>
<syncfusion:PercentTextBox x:Name="percentTextBox2" PercentValue="{Binding MyValue,UpdateSourceTrigger=PropertyChanged}" Width="100" Height="25"  />

{% endhighlight %}
{% endtabs %}

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

![WPF PercentTextBox with Binding Value](Changing-Percent-Value_images/wpf-percent-textbox-binding-value.png)

## Change percent value by pasting the clipboard's text

By default, `WPF Percent TextBox` simply replaces the whole value with the copied value using the current number format. If you want to replace or insert the copied value at a specific place, use the [PasteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PasteMode) property value as `Advanced`. The default value of the `PasteMode` property is `Default`. 

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

{% tabs %}
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
{% endtabs %}

![WPF PercentTextBox displays Pasting Copied Value in Specific Place](Changing-Percent-Value_images/wpf-percent-textbox-paste-value.png)

## Showing the UpDown Button

You can increment or decrement the percent value of `WPF Percent TextBox` by setting the `ShowSpinButton` property value to `true`. Click the Up button to increment or the Down button to decrement the percent value. The default value of the `ShowSpinButton` property is `false`. When using the spin buttons, you may also need to set the `MinValue` and `MaxValue` properties to control the valid range.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox Height="30" Width="150" MinValue="0" MaxValue="100" ShowSpinButton="True" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.MinValue = 0;
percentTextBox.MaxValue = 100;
percentTextBox.ShowSpinButton = true;

{% endhighlight %}
{% endtabs %}

![WPF PercentTextBox displays SpinButton](Changing-Percent-Value_images/wpf-percent-textbox-spinbutton.gif)

## Value Changed Event

The `WPF Percent TextBox` control can notify changes in percent value through the [PercentValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValueChanged) event. In the `PercentValueChanged` event, you can get the old percent value and new percent value from the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox PercentValueChanged="PercentTextBox_PercentValueChanged"/>

{% endhighlight %}
{% highlight C# %} 

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.PercentValueChanged += new PropertyChangedCallback(PercentTextBox_PercentValueChanged);

{% endhighlight %}
{% endtabs %}

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

 By default, the `WPF Percent TextBox` control will display zero when the `PercentValue` is set to `null`. You can use the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_NullValue) and [UseNullOption](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_UseNullOption) properties to show the null value or any other percent value instead of zero.
 
 The default value of the `NullValue` property is `null`; you can reset this to any other percent value. The `NullValue` is displayed only when the `UseNullOption` property is set to `true`. The default value of `UseNullOption` is `false`.
 
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

![WPF PercentTextBox displays Empty Value](Changing-Percent-Value_images/wpf-percent-textbox-empty-value.png)

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

![WPF PercentTextBox displays Null Value](Changing-Percent-Value_images/wpf-percent-textbox-null-value.jpeg)

## Setting Watermark Text

You can display certain information within the control by using the [WatermarkText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkText) property. `WatermarkText` is shown when the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextIsVisible) property is `true`, the `PercentValue` is `null` or empty, the control is not in focus, and the `UseNullOption` property is `true`. The default value of `WatermarkTextIsVisible` is `false`.

### Setting the WatermarkText Foreground

`WPF Percent TextBox` allows you to set the desired brush as a foreground for `WatermarkText` using the [WatermarkTextForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTextForeground) property. The default color of `WatermarkTextForeground` is `Black`.

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

![WPF PercentTextBox displays Watermark Text](Changing-Percent-Value_images/wpf-percent-textbox-watermark.jpeg)

### Setting Watermark Template

You can customize the visual appearance of the `WatermarkText` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_WatermarkTemplate) property. The `WatermarkOpacity` property (used in the sample below) controls the opacity of the watermark content; its default value is `1`.

{% tabs %}
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
{% endtabs %}

![Customizing Watermark Text in WPF PercentTextBox](Changing-Percent-Value_images/wpf-percent-textbox-watermark-customization.png)

N> The `UseNullOption` property must be enabled if you want to see `NullValue` or `WatermarkText` in the `WPF Percent TextBox` control.

N> If both `NullValue` and `WatermarkText` are specified, you will only see `NullValue` but not `WatermarkText`.
