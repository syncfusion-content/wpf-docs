---
layout: post
title: Events | ButtonAdv | wpf | Syncfusion
description: events
platform: wpf
control: ButtonAdv
documentation: ug
---

# Events

The ButtonAdv control comprises the following events:

* Click—The event occurs when the ButtonAdv Control is clicked.

The following code adds the Click event handler to the ButtonAdv control:

{% tabs %}
{% highlight xaml %}

<sync:ButtonAdv Click="button_Click"/></td></tr>

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();

button.Click += new RoutedEventHandler(button_Click);

{% endhighlight %}
{% endtabs %}

* Checked—The event occurs when the element is checked.

The following code adds the Checked event handler to the ButtonAdv control:

{% tabs %}
{% highlight xaml %}

<sync:ButtonAdv Checked="button_Checked"/>

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();

button.Checked += new RoutedEventHandler(button_Checked);

{% endhighlight  %}
{% endtabs %}
