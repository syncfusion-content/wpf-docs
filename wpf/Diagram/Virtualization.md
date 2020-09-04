---
layout: post
title: Quick rendering by loading object lies in viewport alone | Syncfusion.
description: How to enable faster rendering when diagram is too large and how to customize the rendering visibility of the diagram objects?
platform: wpf
control: SfDiagram
documentation: ug
---

# Virtualization and customization

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded and remaining objects will be loaded only when they come into view. 

This feature gives optimized performance and low memory consumption while loading and dragging items to the SfDiagram that consists of large diagram objects.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram and enable the virtualize constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Virtualize"/>
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the Virtualize constraint
diagram.Constraints = diagram.Constraints | GraphConstraints.Virtualize;

{% endhighlight %}
{% endtabs %}

![Virtualization](Virtualization_images/Virtualize.gif)

## Deferred Scrolling

To improve scrolling performance, the outline of a diagram element will be displayed until the UI element is loaded, regardless of the weight of the element. 

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram and enable the virtualize and outline constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Virtualize,Outline"/>
{% endhighlight %}
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the Virtualize and outline constraints
diagram.Constraints |= GraphConstraints.Virtualize | GraphConstraints.Outline;

{% endhighlight %}
{% endtabs %}

N> In SfDiagram, Deferred Scrolling support is named as `Outline`. Outline is only applicable when virtualization is enabled.

![DeferredScrolling](Virtualization_images/VirtualizeOutline.gif)

## Outline customization

Options are provided to override the appearance, style, and interval time of outline by using the [OutlineSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.OutlineSettings.html) class of diagram.

* `OutlineStyle`: Specifies the style for the outline of the diagram elements.
* `RenderInterval`: Specifies the time interval to render the diagram elements into view. Default time interval is 200ms.

{% tabs %}
{% highlight xaml %}

<!--Custom style for outline of overview-->
<Style TargetType="Path" x:Key="outlineStyle">
    <Setter Property="Stroke" Value="Red"/>
    <Setter Property="StrokeThickness" Value="2"/>
</Style>

<!--Initialize outline setting with outline style and outline interval-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Virtualize,Outline" >
    <syncfusion:SfDiagram.OutlineSettings>
        <syncfusion:OutlineSettings OutlineStyle="{StaticResource outlineStyle}">
            <syncfusion:OutlineSettings.RenderInterval>
                <sys:TimeSpan>0:0:0:20</sys:TimeSpan>
            </syncfusion:OutlineSettings.RenderInterval>
        </syncfusion:OutlineSettings>
    </syncfusion:SfDiagram.OutlineSettings>
</syncfusion:SfDiagram>
	
{% endhighlight %}	
{% highlight C# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the outline and virtualize constraints
diagram.Constraints |= GraphConstraints.Virtualize | GraphConstraints.Outline;
//Style for custom outline of overview
Style style = new Style(typeof(Path));
style.Setters.Add(new Setter(Shape.StrokeProperty, new SolidColorBrush(Colors.Red)));
style.Setters.Add(new Setter(Shape.StrokeThicknessProperty,2d));
//Initiaize the outline setting
diagram.OutlineSettings = new OutlineSettings()
{
    //Specifies the outline style
    OutlineStyle = style,
    //Specifies the outline rendering interval
    RenderInterval = new TimeSpan(0,0,0,20),
};
{% endhighlight %}
{% endtabs %}

![Custom Outline](Virtualization_images/CustomOutline.gif)

Find the [Virtualization sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Virtualization) to depict the Virtualization.

{% seealso %}

[How to serialize the diagram control](/wpf/sfdiagram/serialization)

[How to localize the diagram control](/wpf/sfdiagram/localization)

[How to have overview for diagram control](/wpf/sfdiagram/overview-control)

{% endseealso %}