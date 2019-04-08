---
layout: post
title: Appearance | DateTimeEdit | WPF | Syncfusion 
description: This section explains how to customize the appearance and styling of DateTimeEdit control.   
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Appearance     

The appearance of the DateTimeEdit control can be customized by using the VisualStyle property. The following are the various built-in visual styles for DateTimeEdit control:

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Transparent

For example, `Blend` style applied for the `DateTimeEdit` control by setting `VisualStyle` property of `SkinStorage` as Blend.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit syncfusion:SkinStorage.VisualStyle="Blend" x:Name="datetimeedit" Width="100" Height="23" />

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetVisualStyle(datetimeedit, "Blend");

{% endhighlight %}

{% endtabs %}

![](appearance-images/blend.jpeg)