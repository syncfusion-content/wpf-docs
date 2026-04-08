---
layout: post
title: Getting Started with WPF Tree Navigator control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Tree Navigator (SfTreeNavigator) control, its elements and more.
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Getting Started with WPF Tree Navigator (SfTreeNavigator)

Namespace: `Syncfusion.Windows.Controls.Navigation`

Assembly: `Syncfusion.SfTreeNavigator.WPF` (in `Syncfusion.SfTreeNavigator.WPF.dll`)

This guide gives a concise, practical path to add `SfTreeNavigator` to a WPF application.

### Prerequisites

- A WPF app project targeting a supported .NET framework/runtime.
- The `Syncfusion.SfTreeNavigator.WPF` assembly/package added to your project (install via NuGet or add a project reference).

### Quick setup (minimal steps)
1. Create a new WPF application (or open your existing WPF project).
2. Install or reference the `Syncfusion.SfTreeNavigator.WPF` package/assembly in your project (use NuGet or your reference workflow).
3. Add the Syncfusion WPF XML namespace to your XAML (common prefix shown below):

```xaml
xmlns:navigation="http://schemas.syncfusion.com/wpf"
```

4. Place the `SfTreeNavigator` control in your XAML and code-behind (simple example):

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

For XAML-driven scenarios and data binding examples, see [Populating Items](https://help.syncfusion.com/wpf/tree-navigator/populating-items).

### Themes
Tree Navigator supports the standard Syncfusion WPF themes. To apply themes, follow the general theming guidance (SfSkinManager / ThemeStudio). For theme setup and best practices, see:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Tree Navigator](Populating-Items_images/Theme.png)

### Samples and further reading
- Live sample/demos: Syncfusion WPF SampleBrowser (navigation demos): https://github.com/syncfusion/wpf-demos/tree/master/navigation
- Package & installation: refer to the Syncfusion NuGet packages and product documentation.

