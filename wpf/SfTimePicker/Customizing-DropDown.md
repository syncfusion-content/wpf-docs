---
layout: post
title: Deals with the DropDown Customization of the SfTimePicker control for WPF
description: Explains about DropDown Customization of the SfTimePicker control for WPF
platform: wpf
control:  SfTimePicker
documentation: ug
---
# Customizing DropDown

## DropDown height

The height of drop down can be changed using DropDownHeight property.

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfTimePicker x:Name="timePicker" HorizontalAlignment="Center" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

{% endhighlight %}

{% highlight c# %}

	timePicker.DropDownHeight = 200;

{% endhighlight %}

{% endtabs %}

![](Features_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

## ShowDropDownButton

DropDownButton visibility can be changed by using the ShowDropDownButton property

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfTimePicker x:Name="timePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="True"/>

{% endhighlight %}

{% highlight c# %}

	timePicker.ShowDropDownButton = true;

{% endhighlight %}
{% endtabs %}
![](Features_images/Customizing-DropDown_img3.png)