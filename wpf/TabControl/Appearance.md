---
layout: post
title: Appearance in WPF TabControl control | Syncfusion
description: Learn here all about Appearance support in Syncfusion WPF TabControl (TabControlExt) control and more.
platform: wpf
control: TabControlExt
 documentation: ug
---

# Appearance in WPF TabControl (TabControlExt)

This section explains different UI customization and theming options available in [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html).

## Change flow direction

You can change the flow direction of the `TabControl` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt FlowDirection="RightToLeft"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Content="This is the first tab item"
                           Header="tabItem1"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![TabControl with RightToLeft flow direction](Tab-Item-Header_images/FlowDirection.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Themes) in GitHub

## Theme

TabControl supports various built-in themes. Refer to the below links to apply themes for the TabControl,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme in WPF TabControl](Getting-Started_images/wpf-tabcontrol-theme.png)
