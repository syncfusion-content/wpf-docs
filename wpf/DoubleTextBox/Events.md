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

ValueChanged – The event occurs when the Value property of the DoubleTextBox is changed.



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

TextChanged – The event occurs when the Value property of the DoubleTextBox is changed.



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

CultureChanged – The event occurs when the Culture property of the DoubleTextBox is changed.


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

MaxValueChanged – The event occurs when the MaxValue property of the DoubleTextBox is changed.


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

MinValueChanged – The event occurs when the MinValue property of the DoubleTextBox is changed.



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

SelectionChanged – The event occurs when the selection in the textbox is changed.



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
