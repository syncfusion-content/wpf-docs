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

ValueChanged – The event occurs when the Value property of the IntegerTextBox is changed.

{%tabs%}
{% highlight xml %} <syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/>{% endhighlight %}

{% highlight C# %} IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.ValueChanged+=new PropertyChangedCallback(IntegerTextBox_ValueChanged);{% endhighlight %}

{%endtabs%}

You can handle the event as follows:



{% highlight C# %}



private void IntegerTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of IntegerTextBox changes.

        }
{% endhighlight %}

## TextChanged

TextChanged – The event occurs when the Value property of the IntegerTextBox is changed.

{%tabs%}
{% highlight html %}<syncfusion:IntegerTextBox  TextChanged="integerTextBox_TextChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.TextChanged+=new TextChangedEventHandler(IntegerTextBox_TextChanged);{% endhighlight %}

{%endtabs%}

You can handle the TextChanged event as follows:

{% highlight C# %}



private void IntegerTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of IntegerTextBox changes.

        }
{% endhighlight %}

## CultureChanged

CultureChanged – The event occurs when the Culture property of the IntegerTextBox is changed. When the Culture property is changed the value is formatted based on the new Culture.

{%tabs%}
{% highlight html %}<syncfusion:IntegerTextBox  CultureChanged="IntegerTextBox_CultureChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.CultureChanged+=new                                                PropertyChangedCallback(IntegerTextBox_CultureChanged);{% endhighlight %}

{%endtabs%}

You can handle the CultureChanged event as follows:

{% highlight C# %}



private void IntegerTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }
{% endhighlight %}

## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the IntegerTextBox is changed. When the MaxValue is changed the Value and the MinValue properties are formatted.

{%tabs%}
{% highlight html %}<syncfusion:IntegerTextBox  MaxValueChanged="IntegerTextBox_MaxValueChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MaxValueChanged+=new                           PropertyChangedCallback(IntegerTextBox_MaxValueChanged);{% endhighlight %}

{%endtabs%}

You can handle the MaxValueChanged event as follows:

{% highlight C# %}



private void IntegerTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }
{% endhighlight %}

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the IntegerTextBox is changed. When the MinValue is changed the Value and the MaxValue properties are formatted.

{%tabs%}
{% highlight html %}<syncfusion:IntegerTextBox  MinValueChanged="IntegerTextBox_MinValueChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MinValueChanged+=new                            PropertyChangedCallback(IntegerTextBox_MinValueChanged);{% endhighlight %}
{%endtabs%}


You can handle the MinValueChanged event as follows:

{% highlight C# %}



private void IntegerTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }

{% endhighlight %}

## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.

{%tabs%}
{% highlight html %}<syncfusion:IntegerTextBox  SelectionChanged="IntegerTextBox_SelectionChanged"/>{% endhighlight %}

{% highlight C# %}IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.SelectionChanged+=new RoutedEventHandler(IntegerTextBox_SelectionChanged);{% endhighlight %}

{%endtabs%}

You can handle the SelectionChanged event as follows:

{% highlight C# %}



private void IntegerTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }


{% endhighlight %}
