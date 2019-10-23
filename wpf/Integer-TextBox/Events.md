---
layout: post
title: Events | IntegerTextBox | wpf | Syncfusion
description: events
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Events

The IntegerTextBox exposes the following events:

## ValueChanged

[ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~ValueChanged_EV.html) – The event occurs when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property of the IntegerTextBox is changed.

{%tabs%}
{% highlight xaml %} <syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/>{% endhighlight %}

{% highlight C# %} IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.ValueChanged+=new PropertyChangedCallback(IntegerTextBox_ValueChanged);{% endhighlight %}

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

## TextChanged

[TextChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.textchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the [Value]([Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html)) property of the IntegerTextBox is changed.

{%tabs%}
{% highlight xaml %}<syncfusion:IntegerTextBox  TextChanged="integerTextBox_TextChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.TextChanged+=new TextChangedEventHandler(IntegerTextBox_TextChanged);{% endhighlight %}

{%endtabs%}

You can handle the TextChanged event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_TextChanged(object sender, TextChangedEventArgs e)
{
//Insert code to do some operations when Text of IntegerTextBox changes.
}

{% endhighlight %}
{% endtabs %}

## CultureChanged

[CultureChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CultureChanged_EV.html) – The event occurs when the [Culture]([Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~Culture.html)) property of the IntegerTextBox is changed. When the [Culture]([Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~Culture.html)) property is changed the value is formatted based on the new Culture.

{%tabs%}
{% highlight xaml %}<syncfusion:IntegerTextBox  CultureChanged="IntegerTextBox_CultureChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.CultureChanged+=new                                                PropertyChangedCallback(IntegerTextBox_CultureChanged);{% endhighlight %}

{%endtabs%}

You can handle the CultureChanged event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the Culture property changes.
}

{% endhighlight %}
{% endtabs %}

## MaxValueChanged

[MaxValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValueChanged_EV.html) – The event occurs when the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) property of the IntegerTextBox is changed. When the [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MaxValue.html) is changed the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) and the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) properties are formatted.

{%tabs%}
{% highlight xaml %}<syncfusion:IntegerTextBox  MaxValueChanged="IntegerTextBox_MaxValueChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MaxValueChanged+=new                           PropertyChangedCallback(IntegerTextBox_MaxValueChanged);{% endhighlight %}

{%endtabs%}

You can handle the MaxValueChanged event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the MaxValue changed
}

{% endhighlight %}
{% endtabs %}

## MinValueChanged

[MinValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValueChanged_EV.html) – The event occurs when the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) property of the IntegerTextBox is changed. When the [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~MinValue.html) is changed the Value and the MaxValue properties are formatted.

{%tabs%}
{% highlight xaml %}<syncfusion:IntegerTextBox  MinValueChanged="IntegerTextBox_MinValueChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MinValueChanged+=new                            PropertyChangedCallback(IntegerTextBox_MinValueChanged);{% endhighlight %}
{%endtabs%}


You can handle the MinValueChanged event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the MinValue changed
}

{% endhighlight %}
{% endtabs %}

## SelectionChanged

[SelectionChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the selection in the textbox is changed.

{%tabs%}
{% highlight xaml %}<syncfusion:IntegerTextBox  SelectionChanged="IntegerTextBox_SelectionChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.SelectionChanged+=new RoutedEventHandler(IntegerTextBox_SelectionChanged);{% endhighlight %}

{%endtabs%}

You can handle the SelectionChanged event as follows:

{% tabs %}
{% highlight C# %}

private void IntegerTextBox_SelectionChanged(object sender, RoutedEventArgs e)
{
//Insert code to do some operations when the Selected Text changed.
}

{% endhighlight %}
{% endtabs %}
