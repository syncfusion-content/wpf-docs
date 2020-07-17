---
layout: post
title: Set and Override Visual Style at Application Level| SkinStorage (Classic) | Wpf | Syncfusion
description: set and override visual style at application level
platform: wpf
control: SkinStorage (Classic)
documentation: ug
---

# Set and Override Visual Style at Application Level

The Visual Styles can also be defined at application level. The VisualStyle property cannot be set at the application level. You have to merge the appropriate Resource Dictionary on Application resources which will cause all the controls to pick up the particular style.

The following code snippet explains how to override the Syncfusion Blend Style for the Ribbon Control at the application level.

{% tabs %}
{% highlight xaml %}

<Application x:Class="WpfApplication2.App"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
StartupUri="MainWindow.xaml">
<Application.Resources>
<ResourceDictionary>
<ResourceDictionary.MergedDictionaries>
<ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/BlendStyle.xaml"/>
</ResourceDictionary.MergedDictionaries>
<Style TargetType="syncfusion:Ribbon" BasedOn="{StaticResource BlendRibbonStyle}">
<Setter Property="FontSize" Value="19"/>
</Style>
</ResourceDictionary>
</Application.Resources>
</Application>

{% endhighlight %}
{% endtabs %}

The output is displayed as shown below.

![](Set-and-Override-Visual-Style-at-Application-Level_images/Set-and-Override-Visual-Style-at-Application-Level_img1.png)
