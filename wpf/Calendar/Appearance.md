---
layout: post
title: Appearance | CalendarEdit | WPF | Syncfusion
description: How to apply theme for CalendarEdit control for WPF? 
platform: wpf
control: CalendarEdit
documentation: ug
---

# Appearance 

CalenderEdit provides built-in themes which can be applied using [SfSkinManager](https://help.syncfusion.com/wpf/themes/getting-started). 

## Built-in Themes

The appearance of CalenderEdit control can be customized by [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.VisualStyles.html) attached property of the [SfSkinManager](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager.html).

Below example explains how to apply Metro theme for CalenderEdit using `SfSkinManager` in an existing application.
<ul>
<li>Add reference to <b>Syncfusion.SfSkinManager.Wpf.dll</b> and <b>Syncfusion.Themes.Metro.Wpf.dll</b> assembly.</li>
<li>Now add reference to `SfSkinManager` namespace and set `SfSkinManager.VisualStyle` attached property to window or CalenderEdit. Setting `VisualStyle` property to window will apply metro theme for all controls in Windows.

{% tabs %}
{% highlight xaml %}
xmlns:skinManager="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"

<Grid>
<syncfusion:CalendarEdit x:Name="calendar" skinManager:SfSkinManager.VisualStyle="Metro"/>    
</Grid>   
{% endhighlight %}
{% highlight c# %}
using Syncfusion.SfSkinManager;

SfSkinManager.SetVisualStyle(calendar, VisualStyles.Metro);

{% endhighlight %}
{% endtabs %}

</li> 

<li>Now run the application, you can see Metro theme applied for CalenderEdit.</li>
</ul>

![Display Metro theme applied for CalenderEdit](Themes_images/themes_img1.png)


