---
layout: post
title: Getting Started | SfTreeNavigator | wpf | Syncfusion
description: This section explain about how to integrate WPF Tree Navigator(SfTreeNavigator) into an applicationl and enable its basic features with example.
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Getting Started with WPF Tree Navigator (SfTreeNavigator)

Namespace : Syncfusion.Windows.Controls.Navigation 

Assembly : Syncfusion.SfTreeNavigator.WPF (in Syncfusion.SfTreeNavigator.WPF.dll) 

The following code sample shows how to create the Tree Navigator from code-behind and XAML, 

{%tabs%}
{% highlight xaml %}

<navigation:SfTreeNavigator Header="Enterprise Toolkit" >
<navigation:SfTreeNavigatorItem Header="WinRT (XAML)">
<navigation:SfTreeNavigatorItem Header="Chart"/>
<navigation:SfTreeNavigatorItem Header="Tools"/>
</navigation:SfTreeNavigatorItem>
<navigation:SfTreeNavigatorItem Header="Metro Studio"/>
</navigation:SfTreeNavigator>
{% endhighlight %}

{% highlight c# %}

SfTreeNavigator sfToolkit = new SfTreeNavigator();
SfTreeNavigatorItem winrt = new SfTreeNavigatorItem() {Header = "WinRT (XAML)"};
SfTreeNavigatorItem metroStudio = new SfTreeNavigatorItem() {Header = "Metro Studio"};
SfTreeNavigatorItem winrt_chart = new SfTreeNavigatorItem() {Header = "Chart"};
SfTreeNavigatorItem winrt_tools = new SfTreeNavigatorItem() {Header = "Tools"};

winrt.Items.Add(winrt_chart);
winrt.Items.Add(winrt_tools);

sfToolkit.Items.Add(winrt);
sfToolkit.Items.Add(metroStudio);
{% endhighlight %}
{%endtabs%}

## Theme

Tree Navigator supports various built-in themes. Refer to the below links to apply themes for the Tree Navigator,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Tree Navigator](Populating-Items_images/Theme.png)