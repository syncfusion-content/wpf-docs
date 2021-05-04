---
layout: post
title: Appearance in WPF Calendar control | Syncfusion
description: Learn here all about Appearance support in Syncfusion WPF Calendar (CalendarEdit) control and more.
platform: wpf
control: CalendarEdit
documentation: ug
---

# Appearance in WPF Calendar (CalendarEdit)

This section explains different styling, theming options available in [CalendarEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html) control.

## Setting the foreground

You can change the default foreground, mouse hover foreground and border brush of the `CalendarEdit` by using the `Foreground`, `MouseOverForeground` and `MouseOverBorderBrush` properties. The default value of `Foreground` is `Dark SlateGray` and `MouseOverForeground` is `Black`.

{% tabs %}
{% highlight xaml %}

<syncfusion:CalendarEdit Foreground="Blue"
                         MouseOverForeground="Red"
                         MouseOverBorderBrush="DarkGoldenrod"
                         Name="calendarEdit" />

{% endhighlight %}
{% highlight C# %}

calendarEdit.Foreground = Brushes.Blue;
calendarEdit.MouseOverForeground = Brushes.Red;
calendarEdit.MouseOverBorderBrush = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

![Changed the default and mouse hover background of CalendarEdit](Appearance_images/Foreground.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Appearance)

## Setting the background

You can change the default background and mouse hover background color of the `CalendarEdit` by using the `Background` and `MouseOverBackground` properties. The default value of `Background` is `White` and `MouseOverBackground` is `Lavender`.

{% tabs %}
{% highlight xaml %}

<syncfusion:CalendarEdit Background="Pink"
                         MouseOverBackground="Green"
                         Name="calendarEdit" />

{% endhighlight %}
{% highlight C# %}

calendarEdit.Background = Brushes.Pink;
calendarEdit.MouseOverBackground = Brushes.Green;

{% endhighlight %}
{% endtabs %}

![Changed the default and mouse hover background of CalendarEdit](Appearance_images/Background.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Appearance)

## Change flow direction

You can change the flow direction of the `CalendarEdit` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:CalendarEdit FlowDirection="RightToLeft"
                         Name="calendarEdit" />

{% endhighlight %}
{% highlight C# %}

calendarEdit.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![CalendarEdit with right to left flow direction](Appearance_images/rtl.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Appearance)

## Theme

CalendarEdit supports various built-in themes. Refer to the below links to apply themes for the CalendarEdit,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

 ![Setting theme to WPF CalendarEdit](Getting-Started_images/wpf-calendar-theme.png)
