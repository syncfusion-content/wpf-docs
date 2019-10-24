---
layout: post
title: Events| PercentTextBox  | Wpf | Syncfusion
description: events
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Events

The PercentTextBox exposes the following events:

## PercentValueChanged

PercentValueChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox ValueChanged="PercentTextBox_PercentValueChanged"/>

{% endhighlight %}

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.PercentValueChanged+=new PropertyChangedCallback(PercentTextBox_PercentValueChanged);
{% endhighlight %}
{% endtabs %}


You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_PercentValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when value of PercentTextBox PercentValue change.
}

{% endhighlight %}
{% endtabs %}




## TextChanged

TextChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox TextChanged="PercentTextBox_TextChanged"/>
{% endhighlight %}

{% highlight c# %}
 PercentTextBox percentTextBox = new PercentTextBox();
 percentTextBox.TextChanged += new TextChangedEventHandler(PercentTextBox_TextChanged);
{% endhighlight %}
{% endtabs %}


You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_TextChanged(object sender, TextChangedEventArgs e)
{
//Insert code to do some operations when Text of PercentTextBox change.
}

{% endhighlight %}
{% endtabs %}


      

## CultureChanged

CultureChanged – The event occurs when the Culture property of the PercentTextBox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox CultureChanged="PercentTextBox_CultureChanged"/>
{% endhighlight %}

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.CultureChanged+=new                  
{% endhighlight %}
{% endtabs %}


You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the Culture property changes.
}

{% endhighlight %}
{% endtabs %}




## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the PercentTextBox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox MaxValueChanged="PercentTextBox_MaxValueChanged"/>
{% endhighlight %}

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.MaxValueChanged+=new                  
PropertyChangedCallback(PercentTextBox_MaxValueChanged);
{% endhighlight %}
{% endtabs %}



You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the MaxValue changed
}

{% endhighlight %}
{% endtabs %}




## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the PercentTextBox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox MinValueChanged="PercentTextBox_MinValueChanged"/>
{% endhighlight %}

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.MinValueChanged+=new                 
PropertyChangedCallback(PercentTextBox_MinValueChanged);
{% endhighlight %}
{% endtabs %}


You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
//Insert code to do some operations when the MinValue changed
}

{% endhighlight %}
{% endtabs %}






## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox SelectionChanged="PercentTextBox_SelectionChanged"/>
{% endhighlight %}</td></tr>

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.SelectionChanged+=new                      
RoutedEventHandler(PercentTextBox_SelectionChanged);
{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight c# %}
 
void PercentTextBox_SelectionChanged(object sender, RoutedEventArgs e)
{
//Insert code to do some operations when the Selected Text changed.
}

{% endhighlight %}
{% endtabs %}






