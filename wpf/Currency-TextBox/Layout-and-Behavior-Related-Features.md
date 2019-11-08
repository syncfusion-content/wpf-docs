---
layout: post
title: Layout related features | CurrencyTextBox | wpf | Syncfusion
description: Layout and behavior related features represents the customization of the various Foreground, ReadOnly mode and CornerRadius properties
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Layout and Behavior Related Features

## IsReadOnly

If the CurrencyTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears.

N> The Cursor in the CurrencyTextBox can be displayed by setting the `IsReadOnlyCaretVisible` property to true.

{% tabs %}
{% highlight XAML %}
<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="150" Height="25" Value="123" IsReadOnly="True" IsReadOnlyCaretVisible="True"/>
{% endhighlight %}

{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 123;
currencyTextBox.IsReadOnly = true;
currencyTextBox.IsReadOnlyCaretVisible = true;
{% endhighlight %}

{% endtabs %}

![IsReadOnly](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img6.png)



## CornerRadius

The [CornerRadius](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CornerRadius.html) describes the degree to which corners are rounded. This property has no default value.

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="123" Height="25" Width="150" CornerRadius="4"/>

{% endhighlight %}
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.Value = 123;
integerTextBox.CornerRadius = new CornerRadius(4);
{% endhighlight %}

{% endtabs %}

![Corner radius](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img1.png)

## Negative foreground

The Foreground of the CurrencyTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~Value.html) property. When Negative value is assigned to the Value property, then automatically the NegativeForeground value gets assigned to the Foreground property.

N> The [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) in the CurrencyTextBox can be enabled by setting the [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property to true.

### Default NegativeForeground

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 
                            CornerRadius="2" Value="-123" ApplyNegativeForeground="True"/>

{% endhighlight %}
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = -123;
currencyTextBox.CornerRadius = new CornerRadius(2);
currencyTextBox.ApplyNegativeForeground =true; 
{% endhighlight %}

{% endtabs %}

![Default NegativeForeground](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img2.png)

### Customized NegativeForeground

% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 
                            CornerRadius="2" Value="-123" NegativeForeground="BlueViolet" 
                            ApplyNegativeForeground="True"/>

{% endhighlight %}
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = -123;
currencyTextBox.CornerRadius = new CornerRadius(2);
currencyTextBox.ApplyNegativeForeground =true; 
currencyTextBox.NegativeForeground = Brushes.BlueViolet; 
{% endhighlight %}
{% endtabs %}

![Customized NegativeForeground](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img7.png)

## Zero color

The Foreground of the CurrencyTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~Value.html) property. When zero is assigned as a value to the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~Value.html) property, then automatically the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) is set to the Foreground property.

N> The [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) in the CurrencyTextBox can be enabled by setting the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property to true.

### Default ZeroColor

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 
                            CornerRadius="2" Value="0" ApplyZeroColor="True"/>

{% endhighlight %}
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 0;
currencyTextBox.CornerRadius = new CornerRadius(2);
currencyTextBox.ApplyZeroColor =true; 
{% endhighlight %}

{% endtabs %}

![Default ZeroColor](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img8.png)

### Customized ZeroColor

% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 
                            CornerRadius="2" Value="0" ZeroColor ="Magenta" 
                            ApplyZeroColor="True"/>

{% endhighlight %}
{% highlight C# %}
CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 0;
currencyTextBox.CornerRadius = new CornerRadius(2);
currencyTextBox.ApplyZeroColor =true; 
currencyTextBox.ZeroColor = Brushes.Magenta; 
{% endhighlight %}
{% endtabs %}

![Customized ZeroColor](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img9.png)

## EnterToMoveNext

If you press the Enter key in the CurrencyTextBox then the Focus moves to the next element in the application. To enable this feature you have to set the [EnterToMoveNext](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnterToMoveNext.html) property to true.

{% tabs %}

{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" EnterToMoveNext="True"/>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.EnterToMoveNext = true;

{% endhighlight %}

{% endtabs %}


## TextSelectionOnFocus

The [TextSelectionOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~TextSelectionOnFocus.html) property allows the CurrencyTextBox to act like standard text boxes when the cursor hovers over. 

{% tabs %}

{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="1234" TextSelectionOnFocus="True"/>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Value = 1234;
currencyTextBox.TextSelectionOnFocus = true;

{% endhighlight %}

{% endtabs %}

![Text selection on focus](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img10.png)


{% tabs %}

{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="1234" TextSelectionOnFocus="False"/>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Value = 1234;
currencyTextBox.TextSelectionOnFocus = false;

{% endhighlight %}

{% endtabs %}

![Text selection on focus](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img11.png)
