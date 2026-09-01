---
layout: post
title: Events in WPF Button | Syncfusion®
description: Events in WPF Button provide notifications for user interactions, command execution, and WPF Button state changes.
platform: wpf
control: ButtonAdv
documentation: ug
---

# Events in WPF Button (ButtonAdv)

The WPF Button comprises of the pre-defined events that are illustrated below.

## Click

The events occurs when the WPF Button control is clicked and any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:ButtonAdv Click="button_Click"/>

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();
button.Click += new RoutedEventHandler(button_Click);

private void button_Click(object sender, RoutedEventArgs e)
{

}

{% endhighlight %}
{% endtabs %}

## Checked

The event occurs when the WPF Button control is utilized as ToggleButton, that is, when [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property value is set to **true**. Any action can be handled in the respective event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:ButtonAdv IsCheckable="true" Checked="button_Checked"/>

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();
button.IsCheckable = true;
button.Checked += new RoutedEventHandler(button_Checked);

private void button_Checked(object sender, RoutedEventArgs e)
{
          
}
  
{% endhighlight  %}
{% endtabs %}
