---
layout: post
title: Ruler is used to measure the distance of nodes and connectors from origin of the page. 
description: how to measure the distance of Nodes and Connectors? 
platform: wpf
control: SfDiagram
documentation: ug
---

# Rulers

The Ruler provides a Horizontal and Vertical guide for measuring in the Diagram control. The Ruler can be used to measure the Diagram objects, indicate positions, and align Diagram elements. This is especially useful in creating scale models. You can set the unit of measure, such as centimeters or inches. The default [Unit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.LengthUnit_members.html) of measure is pixels.

Please refer to the sample from Dashboard->Desktop->WPF->Diagram->GettingStarted->Rulers and Units.

## Define Rulers

{% tabs %}
{% highlight C# %}

diagramcontrol.HorizontalRuler = new Ruler();
diagramcontrol.VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };

{% endhighlight %}

{% highlight XAML %}

 xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Diagram;assembly=Syncfusion.SfDiagram.WPF"
 xmlns:SyncControls="clr-namespace:Syncfusion.UI.Xaml.Diagram.Controls;assembly=Syncfusion.SfDiagram.WPF"

<Syncfusion:SfDiagram x:Name="diagramcontrol">
            <Syncfusion:SfDiagram.HorizontalRuler>
                <SyncControls:Ruler/>
            </Syncfusion:SfDiagram.HorizontalRuler>
            <Syncfusion:SfDiagram.VerticalRuler>
                <SyncControls:Ruler Orientation="Vertical"/>
            </Syncfusion:SfDiagram.VerticalRuler>
</Syncfusion:SfDiagram>
		
{% endhighlight %}
{% endtabs %}

![DefaultRuler](Rulers_images/Rulers_img1.jpeg)

## Customizing the Ruler

By default, ruler segments are arranged based on the `MeasurementUnit`. See the available [LengthUnits](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.LengthUnit_fields.html) for Ruler.

Segment width, the textual description of the ruler segment, and the appearance of the ruler ticks can be customized. 

![CustomRuler](Rulers_images/Rulers_img2.jpeg)

Please refer to the sample to [Customize the Ruler](http://www.syncfusion.com/downloads/support/directtrac/199579/ze/RulerCustomization324121572)