---
layout: post
title: Events| DoubleTextBox  | Wpf | Syncfusion
description: events
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Events

The DoubleTextBox exposes the following events:

## ValueChanged

[ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~ValueChanged_EV.html) – The event occurs when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property of the DoubleTextBox is changed.



{% tabs %}
{% highlight xaml %}
 <syncfusion:DoubleTextBox ValueChanged="DoubleTextBox_ValueChanged"/>
 {% endhighlight %} 

{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.ValueChanged += new PropertyChangedCallback(DoubleTextBox_ValueChanged); 
{% endhighlight %} 
{% endtabs %}


You can handle the ValueChanged event as follows:


{% highlight C# %} 



private void DoubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

//Insert code to do some operations when value of DoubleTextBox changes.

}

{% endhighlight %}

## TextChanged

[TextChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.textchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property of the DoubleTextBox is changed.



{% tabs %}
{% highlight xaml %} 
<syncfusion:DoubleTextBox TextChanged="DoubleTextBox_TextChanged"/> 
{% endhighlight %} 

{% highlight C# %}
 DoubleTextBox doubleTextBox = new DoubleTextBox();
 doubleTextBox.TextChanged+=new TextChangedEventHandler(DoubleTextBox_TextChanged); 
 {% endhighlight %} 
{% endtabs %}


You can handle the TextChanged event as follows:



{% highlight C# %}



private void DoubleTextBox_TextChanged(object sender, TextChangedEventArgs e)

{

//Insert code to do some operations when Text of DoubleTextBox changes.

}
{% endhighlight %}

## CultureChanged

[CultureChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CultureChanged_EV.html) – The event occurs when the [Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~Culture.html) property of the DoubleTextBox is changed.


{% tabs %}
{% highlight xaml %}
 <syncfusion:DoubleTextBox CultureChanged="DoubleTextBox_CultureChanged"/> 
 {% endhighlight %} 

{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.CultureChanged+=new PropertyChangedCallback(DoubleTextBox_CultureChanged); 
{% endhighlight %} 
{% endtabs %}


You can handle the CultureChanged event as follows:



{% highlight C# %}



private void DoubleTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

//Insert code to do some operations when the Culture property changes.

}

{% endhighlight %}

## MaxValueChanged

[MaxValueChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValueChanged_EV.html) – The event occurs when the [MaxValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MaxValue.html) property of the DoubleTextBox is changed.


{% tabs %}
{% highlight xaml %}
 <syncfusion:DoubleTextBox MaxValueChanged="DoubleTextBox_MaxValueChanged"/>
 {% endhighlight %} 

{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MaxValueChanged+=new              
 PropertyChangedCallback(DoubleTextBox_MaxValueChanged); 
 {% endhighlight %} 
{% endtabs %}


You can handle the MaxValueChanged event as follows:



{% highlight C# %}



private void DoubleTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

//Insert code to do some operations when the MaxValue changed

}
{% endhighlight %}

## MinValueChanged

[MinValueChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValueChanged_EV.html) – The event occurs when the [MinValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~MinValue.html) property of the DoubleTextBox is changed.



{% tabs %}
{% highlight xaml %} 
<syncfusion:DoubleTextBox MinValueChanged="DoubleTextBox_MinValueChanged"/> 
{% endhighlight %} 
{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.MinValueChanged+=new              PropertyChangedCallback(DoubleTextBox_MinValueChanged); 
{% endhighlight %} 
{% endtabs %}


You can handle the MinValueChanged event as follows:



{% highlight C# %}

private void DoubleTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

//Insert code to do some operations when the MinValue changed

}
{% endhighlight %}

## SelectionChanged

[SelectionChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionchanged?redirectedfrom=MSDN&view=netframework-4.7.2) – The event occurs when the selection in the textbox is changed.



{% tabs %}
{% highlight xaml %} 
<syncfusion:DoubleTextBox SelectionChanged="DoubleTextBox_SelectionChanged"/> 
{% endhighlight %} 

{% highlight C# %} 
DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.SelectionChanged+=new RoutedEventHandler(DoubleTextBox_SelectionChanged); 
{% endhighlight %} 
{% endtabs %}


You can handle the SelectionChanged event as follows:



{% highlight C# %}



private void DoubleTextBox_SelectionChanged(object sender, RoutedEventArgs e)

{

//Insert code to do some operations when the Selected Text changed.

}


{% endhighlight %}
