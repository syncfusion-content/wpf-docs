---
layout: post
title: Events | CurrencyTextBox | wpf | Syncfusion
description: events
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Events

The CurrencyTextBox exposes the following events:

## ValueChanged

ValueChanged – The event occurs when the Value property of the CurrencyTextBox is changed.



{% highlight xml %}


<syncfusion:CurrencyTextBox ValueChanged="CurrencyTextBox_ValueChanged"/>

{% endhighlight %}

{% highlight xml %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.ValueChanged+=new PropertyChangedCallback(CurrencyTextBox_ValueChanged);

{% endhighlight %}


You can handle the event as follows:


{% highlight C# %}



private void CurrencyTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of CurrencyTextBox changes.

        }
{% endhighlight %}

## TextChanged

TextChanged – The event occurs when the Value property of the CurrencyTextBox is changed.



{% highlight xml %}


<syncfusion:CurrencyTextBox TextChanged="CurrencyTextBox_TextChanged"/>
{% endhighlight %}

{% highlight C# %}


CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.TextChanged += new TextChangedEventHandler(CurrencyTextBox_TextChanged);
{% endhighlight %}

You can handle the event as follows:


{% highlight C# %}





private void CurrencyTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of CurrencyTextBox changes.

        }

{% endhighlight %}

## CultureChanged

CultureChanged – The event occurs when the Culture property of the CurrencyTextBox is changed.




{% highlight xml %}


<syncfusion:CurrencyTextBox CultureChanged="CurrencyTextBox_CultureChanged"/>
{% endhighlight %}

{% highlight C# %}


CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.CultureChanged+=new    PropertyChangedCallback(CurrencyTextBox_CultureChanged);
{% endhighlight %}


### You can handle the event as follows:


{% highlight C# %}





private void CurrencyTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }
{% endhighlight %}

## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the CurrencyTextBox is changed.



{% highlight xml %}


<syncfusion:CurrencyTextBox MaxValueChanged="CurrencyTextBox_MaxValueChanged"/>
{% endhighlight %}

{% highlight C# %}


CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.MaxValueChanged+=new  PropertyChangedCallback(CurrencyTextBox_MaxValueChanged);
{% endhighlight %}


You can handle the event as follows:


{% highlight C# %}





private void CurrencyTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }
{% endhighlight %}

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the CurrencyTextBox is changed.




{% highlight xml %}


<syncfusion:CurrencyTextBox MinValueChanged="CurrencyTextBox_MinValueChanged"/>
{% endhighlight %}

{% highlight C# %}


CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.MinValueChanged+=new  PropertyChangedCallback(CurrencyTextBox_MinValueChanged);

{% endhighlight %}

### You can handle the event as follows:


{% highlight C# %}





private void CurrencyTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }
{% endhighlight %}
	

## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.



{% highlight xml %}


<syncfusion:CurrencyTextBox SelectionChanged="CurrencyTextBox_SelectionChanged"/>
{% endhighlight %}

{% highlight C# %}



CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.SelectionChanged+=new RoutedEventHandler(CurrencyTextBox_SelectionChanged);

{% endhighlight %}

You can handle the event as follows:


{% highlight C# %}






private void CurrencyTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }
{% endhighlight %}


