---
layout: post
title: Events in WPF Split Button control | Syncfusion
description: Learn about Events support in Syncfusion WPF Split Button control and more.
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Events in WPF Split Button

The Split Button comprises of various pre-defined events to perform any required action that are illustrated below.

## DropDownOpening

The event occurs before opening the dropdown menu popup and any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:SplitButtonAdv x:Name="splitbutton" DropDownOpening="splitbutton_DropDownOpening"/>

{% endhighlight %}
{% highlight C# %} 

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbutton.DropDownOpening +=new CancelEventHandler(splitbutton_DropDownOpening);

private void splitbutton_DropDownOpening(object sender, System.ComponentModel.CancelEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}


## DropDownOpened

The event occurs after opening the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv x:Name="splitbutton" DropDownOpened="splitbutton_DropDownOpened"/> 

{% endhighlight %}
{% highlight C# %}

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbutton.DropDownOpened +=new RoutedEventHandler(splitbutton_DropDownOpened); 

private void splitbutton_DropDownOpened(object sender, RoutedEventArgs e)
{

}

{% endhighlight %} 
{% endtabs %}

## DropDownClosing

The event occurs before closing the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:SplitButtonAdv x:Name="splitbutton" DropDownClosing="splitbutton_DropDownClosing"/>

{% endhighlight %}
{% highlight C# %} 

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbutton.DropDownClosing +=new CancelEventHandler(splitbutton_DropDownClosing);

private void splitbutton_DropDownClosing(object sender, System.ComponentModel.CancelEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}

## DropDownClosed 

The event occurs before closing the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:SplitButtonAdv x:Name="splitbutton" DropDownClosed="splitbutton_DropDownClosed"/> 

{% endhighlight %} 
{% highlight C# %} 

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbutton.DropDownClosed +=new RoutedEventHandler(splitbutton_DropDownClosed); 

private void splitbutton_DropDownClosed(object sender, RoutedEventArgs e)
{

}

{% endhighlight %} 
{% endtabs %}

## Click

The events occurs when the Split Button control is clicked and any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv x:Name="splitbutton" Click="splitbutton_Click"/>

{% endhighlight %}
{% highlight c# %}

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbuttonbutton.Click += new RoutedEventHandler(splitbuttonbutton_Click);

private void splitbuttonbutton_Click(object sender, RoutedEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}

## Events for dropdown menu items

### Click

The events occurs when the dropdown menu item is clicked and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:DropDownMenuItem x:Name="dropDownMenuItem" Click="dropDownMenuItem_Click/> 

{% endhighlight %} 
{% highlight C# %} 

DropDownMenuItem dropDownMenuItem = new DropDownMenuItem();
dropDownMenuItem.Click +=new RoutedEventHandler(dropDownMenuItem_Click);

private void dropDownMenuItem_Click(object sender, RoutedEventArgs e)
{

} 

{% endhighlight %} 
{% endtabs %}

### IsCheckedChanged

The events occur when the dropdown menu item is checked or unchecked, that is, only when [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DropDownMenuItem.html#Syncfusion_Windows_Tools_Controls_DropDownMenuItem_IsCheckable) property is set to **true**. Any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:DropDownMenuItem x:Name="dropDownMenuItem" IsCheckable="True" IsCheckedChanged="DropDownMenuItem_IsCheckedChanged"/>

{% endhighlight %} 
{% highlight C# %} 

DropDownMenuItem dropDownMenuItem  = new DropDownMenuItem();
dropDownMenuItem.IsCheckable=true;
dropDownMenuItem.IsCheckedChanged +=new RoutedEventHandler(dropDownMenuItem_IsCheckedChanged);

private void dropDownMenuItem_IsCheckedChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{

}

{% endhighlight %} 
{% endtabs %}
