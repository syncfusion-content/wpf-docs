---
layout: post
title: Auto-Scroll Limit in WPF SfDiagram | Syncfusion®
description: Control the auto-scrolling region in Syncfusion® WPF SfDiagram by configuring auto-scroll limits and defining custom scrollable areas.
platform: wpf
control: SfDiagram
documentation: ug
---

# Auto-Scroll Limit in WPF SfDiagram

The auto-scroll limit allows you to define the scrollable region of the Diagram while the page is being auto-scrolled. The [AutoScrollLimit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ScrollSettings.html#Syncfusion_UI_Xaml_Diagram_ScrollSettings_AutoScrollLimit) property of ScrollSettings class helps to limit the auto scrolling area. It includes the following options:

* **Infinity**: Allows auto-scroll in all directions without any restriction.
* **Diagram**: Allows auto-scroll within the Diagram content.
* **Limited**: Allows auto-scroll within the specified area.

The default value is `Infinity`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the ScrollSetting class with auto scroll limit-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings AutoScrollLimit="Limited" ScrollableArea="0,0,1500,1500"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the ScrollSetting with auto scroll limit and scrolling area
diagram.ScrollSettings = new ScrollSettings()
{
    AutoScrollLimit = ScrollLimit.Limited,
    ScrollableArea = new Rect(0,0,1500,1500),
};
{% endhighlight %}
{% endtabs %}

| AutoScrollLimit | Output |
|---|---|
| Infinity |![AutoScroll infinity](Scroll-Settings_images/AutoScrollInfinity.gif) |
| Diagram |![AutoScroll diagram](Scroll-Settings_images/AutoScrollDiagram.gif) |
| Limited <br> ScrollableArea = (0,0,1500,1500) | ![AutoScroll limited](Scroll-Settings_images/AutoScrollLimited.gif) |
