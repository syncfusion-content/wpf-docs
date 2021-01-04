---
layout: post
title: Appearance of the WPF TimeSpanEdit control | Syncfusion
description: Learn about UI customization, theme support in Syncfusion WPF TimeSpanEdit control and more details about the control features.
platform: wpf
control: TimeSpanEdit
documentation: ug
---

# Appearance in WPF TimeSpanEdit

This section explains different UI customization and theming options available in [TimeSpanEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TimeSpanEdit.html).

## Setting the background

You can change the background color and selection color of `TimeSpanEdit` by using the `Background` and `SelectionBrush` property. The default value of `Background` property is `White` and `SelectionBrush` property is `Royal Blue`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TimeSpanEdit Background="Yellow"
                         SelectionBrush="Red"
                         Value="35.12:45:52"
                         Name="timeSpanEdit"/>

{% endhighlight %}
{% highlight C# %}

TimeSpanEdit timeSpanEdit = new TimeSpanEdit();
timeSpanEdit.Background = Brushes.Yellow;
timeSpanEdit.SelectionBrush = Brushes.Red;
timeSpanEdit.Value = new TimeSpan(35, 12, 45, 52);

{% endhighlight %}
{% endtabs %}

![TimeSpanEdit with yellow background](Apperance_images/Background.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-timespanedit-control-examples/tree/master/Samples/Appearance) in GitHub

## Setting the foreground

You can change the foreground color by using the `Foreground` property. The default value of `Foreground` property is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TimeSpanEdit Foreground="Red"
                         Value="35.12:45:52"
                         Name="timeSpanEdit"/>

{% endhighlight %}
{% highlight C# %}

TimeSpanEdit timeSpanEdit = new TimeSpanEdit();
timeSpanEdit.Foreground = Brushes.Red;
timeSpanEdit.Value = new TimeSpan(35, 12, 45, 52);

{% endhighlight %}
{% endtabs %}

![TimeSpanEdit with red foreground](Apperance_images/Foreground.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-timespanedit-control-examples/tree/master/Samples/Appearance) in GitHub

## Change flow direction

You can change the flow direction of the `TimeSpanEdit` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TimeSpanEdit FlowDirection="RightToLeft"
                         Value="35.12:45:52"
                         Name="timeSpanEdit"/>

{% endhighlight %}
{% highlight C# %}

TimeSpanEdit timeSpanEdit = new TimeSpanEdit();
timeSpanEdit.FlowDirection = FlowDirection.RightToLeft;
timeSpanEdit.Value = new TimeSpan(35, 12, 45, 52);

{% endhighlight %}
{% endtabs %}

![TimeSpanEdit with RightToLeft flow direction](Apperance_images/FlowDirection.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-timespanedit-control-examples/tree/master/Samples/Appearance) in GitHub

## Theme

TimeSpanEdit supports various built-in themes. Refer to the below links to apply themes for the TimeSpanEdit,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

 ![Setting theme to WPF TimeSpanEdit](Getting-Started_images/Theme.png)