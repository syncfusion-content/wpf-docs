---
layout: post
title: Events | SplitButton | wpf | Syncfusion
description: events
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Events

The SplitButtonAdv control comprises the following events:

## Click 

This event occurs when the SplitButtonAdv control is clicked.

The following code adds the Click event handler to the SplitButtonAdv control:

{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv Click="SplitButtonAdv_Click"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Click +=new RoutedEventHandler(button_Click);

{% endhighlight %}

{% endtabs %}

## DropDownOpening 

This event occurs before opening the DropDown.

The following code adds the DropDownOpening event handler to the SplitButtonAdv control:

{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv DropDownOpening="SplitButtonAdv_DropDownOpening"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.DropDownOpening +=new CancelEventHandler(button_DropDownOpening);

{% endhighlight %}

{% endtabs %}

## DropDownOpened 

This event occurs after opened the DropDown. 

The following code adds the DropDownOpened event handler to the SplitButtonAdv control:


{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv DropDownOpened="SplitButtonAdv_DropDownOpened"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.DropDownOpened +=new RoutedEventHandler(button_DropDownOpened);

{% endhighlight %}

{% endtabs %}

## DropDownClosing 

This event occurs before closing the DropDown.

The following code adds the DropDownClosing event handler to the SplitButtonAdv control:

{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv DropDownClosing="SplitButtonAdv_DropDownClosing"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.DropDownClosing +=new CancelEventHandler(button_DropDownClosing);

{% endhighlight %}

{% endtabs %}

## DropDownClosed 

This event occurs after closed the DropDown.

The following code adds the DropDownClosed event handler to the SplitButtonAdv control:


{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv DropDownClosed="SplitButtonAdv_DropDownClosed"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.DropDownClosed +=new RoutedEventHandler(button_DropDownClosed);


{% endhighlight %}

{% endtabs %}
