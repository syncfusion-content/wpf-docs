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

You can customize the appearance of the `TimeSpanEdit` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinmanager.SfSkinmanager.html#Syncfusion_SfSkinManager_SfSkinManager_SetVisualStyle_System_Windows_DependencyObject_Syncfusion_SfSkinManager_VisualStyles_) method and `SfSkinManager.VisualStyle` property . The following are the various built-in visual styles for `TimeSpanEdit` control.

* Blend
* Default
* Lime
* MaterialDark
* MaterialDarkBlue
* MaterialLight
* MaterialLightBlue
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office365
* Saffron
* SystemTheme
* VisualStudio2013
* VisualStudio2015

Here, the `Blend` style is applied to the `TimeSpanEdit`.

{% tabs %}
{% highlight xaml %}

<syncfusion:TimeSpanEdit syncfusionskin:SfSkinManager.VisualStyle="Blend" 
                         Name="timeSpanEdit"/>

{% endhighlight %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

TimeSpanEdit timeSpanEdit = new TimeSpanEdit();
SfSkinManager.SetVisualStyle(timeSpanEdit, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![TimeSpanEdit with Blend visual style](Apperance_images/BlendTheme.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-timespanedit-control-examples/tree/master/Samples/Themes) in GitHub