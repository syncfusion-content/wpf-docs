---
layout: post
title: Rulers in WPF Diagram control | Syncfusion
description: Learn here all about Rulers support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Rulers in WPF Diagram (SfDiagram)

The Ruler provides a Horizontal and Vertical guide for measuring in the Diagram control. The Ruler can be used to measure the Diagram objects, indicate positions, and align Diagram elements. This is especially useful in creating scale models. You can set the unit of measure, such as centimeters or inches. The default [Unit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.LengthUnit.html) of measure is pixels.

Please refer to the sample from Dashboard->Desktop->WPF->Diagram->GettingStarted->Rulers and Units.

## Define Rulers

{% tabs %}
{% highlight XAML %}

xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Diagram;assembly=Syncfusion.SfDiagram.WPF"
xmlns:SyncControls="clr-namespace:Syncfusion.UI.Xaml.Diagram.Controls;assembly=Syncfusion.SfDiagram.WPF"

<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.HorizontalRuler>
        <syncfusion:Ruler/>
    </syncfusion:SfDiagram.HorizontalRuler>
    <syncfusion:SfDiagram.VerticalRuler>
        <syncfusion:Ruler Orientation="Vertical"/>
    </syncfusion:SfDiagram.VerticalRuler>
</syncfusion:SfDiagram>
		
{% endhighlight %}
{% highlight C# %}

diagram.HorizontalRuler = new Ruler();
diagram.VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };

{% endhighlight %}
{% endtabs %}

![DefaultRuler](Rulers_images/Rulers_img1.jpeg)

## Customizing the Ruler

By default, ruler segments are arranged based on the `MeasurementUnit`. See the available [LengthUnits](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.LengthUnit.html) for Ruler.

Segment width, the textual description of the ruler segment, and the appearance of the ruler ticks can be customized. 

![CustomRuler](Rulers_images/Rulers_img2.jpeg)

Please refer to the sample to [Customize the Ruler](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Rulers).
