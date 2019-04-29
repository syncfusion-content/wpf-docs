---
layout: post
title: Appearance | DateTimeEdit | WPF | Syncfusion 
description: DateTimeEdit control provides an option to customize the appearance to different visual style such as Blend, Office2003, etc.,
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

![DateTimeEdit blend visual style](appearance-images/blend.jpeg)