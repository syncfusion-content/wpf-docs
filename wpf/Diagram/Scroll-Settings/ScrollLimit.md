---
layout: post
title: Scroll Limit in WPF Diagram control | Syncfusion
description: Learn here all about Scroll Limit support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Scroll Limit in WPF Diagram (SfDiagram)

The scroll limit allows you to define the scrollable region of the Diagram while mouse scrolling on the page. The [ScrollLimit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ScrollSettings.html#Syncfusion_UI_Xaml_Diagram_ScrollSettings_ScrollLimit) property of scroll settings helps to limit the scrolling area. It includes the following options:

* **Infinity**: Allows you to scroll in all directions without any restriction.
* **Diagram**: Allows you to scroll within the Diagram content.
* **Limited**: Allows you to scroll within the specified area.

The default operation is `Diagram`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the scroll setting class with scroll limit-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings ScrollLimit="Diagram"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the scroll settings with scroll limit
diagram.ScrollSettings = new ScrollSettings()
{
    ScrollLimit = ScrollLimit.Diagram,
};
{% endhighlight %}
{% endtabs %}
## Scrolling Diagrams with Arrow Keys

The arrow keys (Left, Right, Up, Down) and navigation keys (Home, End, Page Up, Page Down) on the keyboard provide a convenient way to navigate through the diagram. Depending on the configuration of the `ScrollLimit` property, these keys can be used to scroll the diagram in various ways.

| Shortcut Keys | Description |
|---|---|
| Left Arrow Key | The diagram page scrolls to the left by 120 pixels. | 
| Right Arrow Key | The diagram page scrolls to the right by 120 pixels. | 
| Up Arrow Key | The diagram page scrolls to the top by 120 pixels. | 
| Down Arrow Key | The diagram page scrolls to the bottom by 120 pixels. | 
| Home Key | The diagram page jump to the leftmost position. | 
| End Key | The diagram page jump to the rightmost position. | 
| Page Up Key | The diagram page jump to the topmost position. | 
| Page Down Key | The diagram page jump to the bottommost position. |

N> When the `ScrollLimit` is set to Infinity, pressing the Page Up, Page Down, Home, or End keys does not result in any navigation on the diagram page.

## Scrollable area

You can restrict scrolling beyond any particular rectangle area by using the `ScrollableArea` property of ScrollSettings. To restrict scrolling beyond any custom region,you have to set the `ScrollLimit` to Limited. The default value is Rect.Empty.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the scroll setting class with scroll limit and scrollable area values-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings ScrollLimit="Limited" ScrollableArea="0,0,1500,1500"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the scroll settings with scroll limit and scrollabl area value
diagram.ScrollSettings = new ScrollSettings()
{
    ScrollLimit = ScrollLimit.Limited,
    ScrollableArea = new Rect(0,0,1500,1500),
};
{% endhighlight %}
{% endtabs %}

| ScrollLimit | Output |
|---|---|
| Infinity |![ScrollLimit infinity](Scroll-Settings_images/ScrollLimitInfinity.gif) |
| Diagram |![ScrollLimit Diagram](Scroll-Settings_images/ScrollLimitDiagram.gif) |
| Limited <br> ScrollableArea = (0,0,1500,1500) | ![ScrollLimit Limited](Scroll-Settings_images/ScrollLimitLimited.gif) |

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Interaction/DiagramScrollUsingArrowKeys)
## See Also

[How to stop infinite scrolling?](https://support.syncfusion.com/kb/article/9869/how-to-stop-infinite-scrolling-in-wpf-diagram-sfdiagram)

[How to restrict diagram objects dragging in the positive side?](https://support.syncfusion.com/kb/article/9917/how-to-restrict-diagram-objects-dragging-in-the-positive-side-in-wpf-diagram)