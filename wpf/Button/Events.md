---
layout: post
title: Events in WPF Button | Syncfusion®
description: Events in WPF Button provide notifications for user interactions, command execution, and WPF Button state changes.
platform: wpf
control: ButtonAdv
documentation: ug
---

# Events in WPF Button (ButtonAdv)

The [WPF Button](https://www.syncfusion.com/wpf-controls/button) control includes the predefined events described below. The WPF Button is implemented through the `ButtonAdv` class.

## Click

The `Click` event occurs when the WPF Button control is clicked. You can handle any action in the respective event handler.

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

The `Checked` event occurs when the WPF Button control is used as a ToggleButton, that is, when the [IsCheckable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsCheckable) property is set to **true**. You can handle any action in the respective event handler.

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
