---
layout: post
title: Snap objects with respect to grid lines in the Design environment.
description: How to snap Nodes and Connectors over gridlines?
platform: wpf
control: SfDiagram
documentation: ug
---

# Snapping

Defines the gridlines and defines how and when the objects have to be snapped.

Please refer to the [SnapSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SnapSettings_members.html) properties.

## Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram. A Node can be snapped with its neighboring objects based on certain alignments(same size,same position). Such alignments are visually represented as smart guides.

Snapping to objects can be enabled by assigning values other than `SnapToObject.None` to `SfDiagram.SnapSettings.SnapToObject`.

{% tabs %}
{% highlight C# %}

//Enables or disables the default behaviors of the Snapping with objects in SfDiagram.
diagram.SnapSettings.SnapToObject = SnapToObject.All;

{% endhighlight %}
{% endtabs %}

![](Gridlines_images/SnapToObject.gif)

Please refer to the members of [SnapToObject](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SnapToObject.html).

## Gridlines

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

### Customize the gridlines visibility

The `SnapConstraints` property of SnapSettings enables you to show/hide the gridlines.

{% tabs %}
{% highlight xaml %}

<!--Initialize SfDiagram-->
<diagram:SfDiagram x:Name="diagram"> 
  <!--Initialize SnapSettings-->		
  <diagram:SfDiagram.SnapSettings>
    <diagram:SnapSettings SnapConstraints="ShowLines"/>
  </diagram:SfDiagram.SnapSettings>
</diagram:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Shows both Horizontal and Vertical Gridlines
diagram.SnapSettings.SnapConstraints = SnapConstraints.ShowLines;

{% endhighlight %}
{% endtabs %}

![](Gridlines_images/Gridlines_img1.jpeg)

### Appearance

Options are provided to customize the Style and LineIntervals of Gridlines.

Please refer to the [Gridlines](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.Gridlines_members.html) properties.

Please refer to the KB link for [Gridlines customization](https://www.syncfusion.com/kb/8466/how-to-customize-the-appearance-for-gridlines)

## Snap To Lines

This feature allows the Diagram objects to snap to the nearest interaction of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the [SnapConstraints](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SnapConstraints.html) property of SnapSettings. 
{% tabs %}
{% highlight C# %}

//Enables snapping to both the horizontal and vertical lines.
diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToLines;

{% endhighlight %}
{% endtabs %}