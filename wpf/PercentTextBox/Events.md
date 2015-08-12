---
layout: post
title: Events
description: events
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Events

The PercentTextBox exposes the following events:

## PercentValueChanged

PercentValueChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

{% highlight xml %}
XAML
<syncfusion:PercentTextBox ValueChanged="PercentTextBox_PercentValueChanged"/>
{% endhighlight %}
{% highlight c# %}
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.PercentValueChanged+=new PropertyChangedCallback(PercentTextBox_PercentValueChanged);
 {% endhighlight %}


You can handle the event as follows:

 {% highlight c# %}
 
    [C#]

    void PercentTextBox_PercentValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of PercentTextBox PercentValue change.

        }

 {% endhighlight %}





## TextChanged

TextChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

{% highlight xml %}
 XAML
<syncfusion:PercentTextBox TextChanged="PercentTextBox_TextChanged"/>
 {% endhighlight %}
{% highlight c# %}
C# 
PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.TextChanged += new TextChangedEventHandler(PercentTextBox_TextChanged);
 {% endhighlight %}


You can handle the event as follows:

 {% highlight c# %}
 
    [C#]
  void PercentTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of PercentTextBox change.

        }

 {% endhighlight %}



      

## CultureChanged

CultureChanged – The event occurs when the Culture property of the PercentTextBox is changed.

{% highlight xml %}
XAML
<syncfusion:PercentTextBox CultureChanged="PercentTextBox_CultureChanged"/>
{% endhighlight %}
{% highlight c# %}
C# 
PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.CultureChanged+=new PropertyChangedCallback(PercentTextBox_CultureChanged);</td></tr>
{% endhighlight %}


You can handle the event as follows:

 {% highlight c# %}
 
    [C#]

    void PercentTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }

 {% endhighlight %}





## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the PercentTextBox is changed.

{% highlight xml %}
XAML
<syncfusion:PercentTextBox MaxValueChanged="PercentTextBox_MaxValueChanged"/>
{% endhighlight %}
{% highlight c# %}
C# 
PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.MaxValueChanged+=new  PropertyChangedCallback(PercentTextBox_MaxValueChanged);
{% endhighlight %}


You can handle the event as follows:

 {% highlight c# %}
 
    [C#]

void PercentTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

	//Insert code to do some operations when the MaxValue changed

}

 {% endhighlight %}





## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the PercentTextBox is changed.

{% highlight xml %}
XAML
<syncfusion:PercentTextBox MinValueChanged="PercentTextBox_MinValueChanged"/>
{% endhighlight %}
{% highlight c# %}
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.MinValueChanged+=new PropertyChangedCallback(PercentTextBox_MinValueChanged);</td></tr>
{% endhighlight %}


You can handle the event as follows:

{% highlight xml %}
 
[C#]

void PercentTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

	//Insert code to do some operations when the MinValue changed

}

 {% endhighlight %}


## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.

{% highlight xml %}
XAML
<syncfusion:PercentTextBox SelectionChanged="PercentTextBox_SelectionChanged"/>
{% endhighlight %}
{% highlight c# %}
C# 
PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.SelectionChanged+=new RoutedEventHandler(PercentTextBox_SelectionChanged);
{% endhighlight %}


You can handle the event as follows:

 {% highlight c# %}
 
    [C#]

   void PercentTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }

 {% endhighlight %}







