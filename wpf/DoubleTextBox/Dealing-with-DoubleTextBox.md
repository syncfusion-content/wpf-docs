---
layout: post
title: Dealing with Syncfusion DoubleTextBox control for WPF
description: Dealing with Syncfusion DoubleTextBox control for WPF
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Dealing with DoubleTextBox

## Watermark

The Watermark text is the dummy content displayed in the DoubleTextBox when the value is null. It can be set using the [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) property. To enable Watermark text, the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) property need to set to true. By default its value is false.

N> [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) is visible only when the value of DoubleTextBox is null.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Height="25"
                          Width="100" Value="{x:Null}" UseNullOption="True"
                          WatermarkText="Type Here" WatermarkTextIsVisible="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox DoubletextBox1 = new DoubleTextBox();
DoubletextBox1.Width = 100;
DoubletextBox1.Height = 25;
DoubletextBox1.Value =null;
DoubletextBox1.UseNullOption = true;
DoubletextBox1.WatermarkText = "Type Here";
DoubletextBox1.WatermarkTextIsVisible = true;

{% endhighlight %}

{% highlight VB %}

Dim DoubletextBox1 As DoubleTextBox =  New DoubleTextBox() 
DoubletextBox1.Width = 100
DoubletextBox1.Height = 25
DoubletextBox1.Value =Nothing
DoubletextBox1.UseNullOption = True
DoubletextBox1.WatermarkText = "Type Here"
DoubletextBox1.WatermarkTextIsVisible = True

{% endhighlight %}

{% endtabs %}

![Watermark text](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img1.jpeg)

[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. When the control loses its focus the [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) comes to the visible state if the Value is null and the WatermarkTextIsVisible is true.

## Binding value

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source) or bidirectional (source <-> target). The data can bind to the DoubleTextBox through the Value property.

The following example shows a simple binding between the value of the DoubleTextBox and another DoubleTextBox value that reflects the typed value:

![Binding value](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img2.jpeg)

To bind values other than double values, the Value Converter need to use. The following example shows a simple binding between the value of the DoubleTextBox and the Textbox text that reflects the typed value:

{% tabs %}

{% highlight XAML %}

<StackPanel>
<StackPanel.Resources>
<c:StringToDoubleConverter x:Key="stringToDoubleConverter"/>
</StackPanel.Resources>
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Margin="10"/>
<TextBox x:Name="textBox" Width="150" Margin="10"
         Text="{Binding ElementName=doubleTextBox,Path=Value,Mode=TwoWay,
		 Converter={StaticResource stringToDoubleConverter}}"/>
</StackPanel>

{% endhighlight %}

{% endtabs %}

![Binding value](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img3.jpeg)

## Keyboard and Mouse support

Up or down key arrows allows to spin the values of DoubleTextBox one step up or down. Mouse Scroll in the DoubleTextBox spin the values one step up or down. This spin behavior in the DoubleTextBox, can be restricted by setting the [IsScrollingOnCircle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~IsScrollingOnCircle.html) property to `false`. By default, its value is `true`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="10" IsScrollingOnCircle="False"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.IsScrollingOnCircle = false;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.Value = 10
doubleTextBox.IsScrollingOnCircle = False

{% endhighlight %}

{% endtabs %}

## IsReadOnly

If the DoubleTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears. 

To enable this feature set [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) to `true`. By default its value is `false`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" IsReadOnly="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.IsReadOnly = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.IsReadOnly = True

{% endhighlight %}

{% endtabs %}

## EnterToMoveNext

On pressing the Enter key in the DoubleTextBox, then the Focus moves to the next element in the application. To restrict this feature the [EnterToMoveNext](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnterToMoveNext.html) property need to set to `false`. By default its value is `true`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" EnterToMoveNext="False"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.EnterToMoveNext = false;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.EnterToMoveNext = False

{% endhighlight %}

{% endtabs %}

## TextSelectionOnFocus

The [TextSelectionOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~TextSelectionOnFocus.html) property allows the DoubleTextBox to act like standard text boxes when the cursor hovers over. To restrict this behavior set its value as false. By default the value is true.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" TextSelectionOnFocus="False"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.TextSelectionOnFocus = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.TextSelectionOnFocus = True

{% endhighlight %}

{% endtabs %}

### False

![TextSelectionOnFocus](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img6.png)

### True

![TextSelectionOnFocus](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img7.png)

## Extended scrolling

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is used to change the values based on the click and drag direction of the mouse movements. The range will increase when the mouse moves to the right or top of the screen, and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state. The default value is false.

### Adding extended scrolling to an application

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property must be set either in XAML or the code file.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="120" Height="25" Value ="93" EnableExtendedScrolling="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 120;
doubleTextBox.Height = 25;
doubleTextBox.Value = 93;
doubleTextBox.EnableExtendedScrolling = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 120
doubleTextBox.Height = 25
doubleTextBox.Value = 93
doubleTextBox.EnableExtendedScrolling = True

{% endhighlight %}

{% endtabs %}

![Adding extended scrolling to an application](Dealing-with-DoubleTextBox-images/Dealing-with-DoubleTextBox-img4.jpeg)


