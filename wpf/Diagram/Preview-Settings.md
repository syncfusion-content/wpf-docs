---
layout: post
title: Syncfusion Diagram supports to edit nodes and connectors at runtime.
description: How to select and edit nodes and connectors during runtime and how to arrange the node and connectors while dragging?
platform: wpf
control: SfDiagram
documentation: ug
---
## Preview Settings

SfDiagram provides support to drag objects as an outline without affecting original object. When multiple elements are selected, outline of every selected element will be moved.

Preview Dragging can be enabled by assigning values other than `PreviewMode.Preview` to `SfDiagram.PreviewSettings.PreviewMode`.

![QuickCommand](Interaction/Interaction_images/QuickCommand_img.png)

By default, Outline of the connectors connected to the dragging objects will be in disabled state. But, you can able to view the outline of the connectors, by holding dragging objects for certain time span. `ConnectorRefreshingSpan` property of `PreviewSettings` allows you to specify the time span and the value should be greater than 300ms.

{% tabs %}
{% highlight C# %}

this.diagram.PreviewSettings = new PreviewSettings() { PreviewMode = PreviewMode.Preview, ConnectorRefreshingSpan = 300 };

{% endhighlight %}
{% endtabs %}

![QuickCommand](Interaction/Interaction_images/QuickCommand_img2.png)

### Appearance

Appearance of the preview can be modified using `PreviewStyle` property of `PreviewSettings`.

{% tabs %}
{% highlight C# %}

var previewStyle = new Style();
previewStyle.TargetType = typeof(Shape);
previewStyle.Setters.Add(new Setter() 
{ 
    Property = Shape.StrokeProperty, 
    Value = new SolidColorBrush(Colors.CornflowerBlue) 
});
previewStyle.Setters.Add(new Setter()
{
    Property = Shape.StrokeThicknessProperty, 
    Value = 1.5
});
previewStyle.Setters.Add(new Setter()
{ 
    Property = Shape.StrokeDashArrayProperty, 
    Value = new DoubleCollection { 3, 3 }
});
this.diagram.PreviewSettings = new PreviewSettings() 
{ 
    PreviewMode = PreviewMode.Preview, 
    ConnectorRefreshingSpan = 300, 
    PreviewStyle = previewStyle
};

{% endhighlight %}
{% endtabs %}

![QuickCommand](Interaction/Interaction_images/QuickCommand_img3.png)
