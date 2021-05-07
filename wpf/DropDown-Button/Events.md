---
layout: post
title: Events in WPF Dropdown Button control | Syncfusion
description: Learn here all about Events support in Syncfusion WPF Dropdown Button (DropDownButtonAdv) control and more.
platform: WPF
control: DropDownButtonAdv
documentation: ug
---

# Events in WPF Dropdown Button (DropDownButtonAdv)

The Dropdown Button control comprises of various pre-defined events to perform any required action that are illustrated below.

## DropDownOpening

The event occurs before opening the dropdown menu popup and any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:DropDownButtonAdv x:Name="dropdownbutton" DropDownOpening="dropdownbutton_DropDownOpening"/>

{% endhighlight %}
{% highlight c# %} 

DropDownButtonAdv dropdownbutton = new DropDownButtonAdv();
dropdownbutton.DropDownOpening +=new CancelEventHandler(dropdownbutton_DropDownOpening);

private void dropdownbutton_DropDownOpening(object sender, System.ComponentModel.CancelEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}

## DropDownOpened

The event occurs after opening the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:DropDownButtonAdv x:Name="dropdownbutton" DropDownOpened="dropdownbutton_DropDownOpened"/> 

{% endhighlight %}
{% highlight C# %}

DropDownButtonAdv dropdownbutton = new DropDownButtonAdv();
dropdownbutton.DropDownOpened +=new RoutedEventHandler(dropdownbutton_DropDownOpened); 

private void dropdownbutton_DropDownOpened(object sender, RoutedEventArgs e)
{

}

{% endhighlight %} 
{% endtabs %}

## DropDownClosing

The event occurs before closing the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:DropDownButtonAdv x:Name="dropdownbutton" DropDownClosing="dropdownbutton_DropDownClosing"/>

{% endhighlight %}
{% highlight C# %} 

DropDownButtonAdv dropdownbutton = new DropDownButtonAdv();
dropdownbutton.DropDownClosing +=new CancelEventHandler(dropdownbutton_DropDownClosing);

private void dropdownbutton_DropDownClosing(object sender, System.ComponentModel.CancelEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}

## DropDownClosed 

The event occurs after closing the dropdown menu popup and any action can be handled in respective event handler.

{% tabs %}
{% highlight xaml %} 

<syncfusion:DropDownButtonAdv x:Name="dropdownbutton" DropDownClosed="dropdownbutton_DropDownClosed"/> 

{% endhighlight %} 
{% highlight C# %} 

DropDownButtonAdv dropdownbutton = new DropDownButtonAdv();
dropdownbutton.DropDownClosed +=new RoutedEventHandler(dropdownbutton_DropDownClosed); 

private void dropdownbutton_DropDownClosed(object sender, RoutedEventArgs e)
{

}

{% endhighlight %} 
{% endtabs %}

## Events for dropdown menu items

### Click

The event occurs when the dropdown menu item is clicked and any action can be handled in respective event handler.

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

The event occurs when the dropdown menu item is checked or unchecked, that is, only when [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DropDownMenuItem.html#Syncfusion_Windows_Tools_Controls_DropDownMenuItem_IsCheckable) property is set to **true**. Any action can be handled in the respective event handler.

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
