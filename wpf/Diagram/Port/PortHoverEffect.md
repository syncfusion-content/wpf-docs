---
layout: post
title: Port hovering effect in WPF Diagram control | Syncfusion
description: Learn here all about Port hovering animation effect support in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Port hovering animation effect in WPF Diagram (SfDiagram)

When establishing a new connection or modifying the endpoint of existing connection, animation will be shown over the connecting objects. And `PortHoverEffect` property of `SfDiagram` class allows you to change the animation effect. The default effect is Ripple.

* Ripple: Specifies the water ripple circles type animation effect for connection.
* Shrink: Specifies the plus symbol type animation effect for connection.
* None: Specifies no connection animation effect.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram with port hover effect as ripple-->
<syncfusion:SfDiagram x:Name="diagram" PortHoverEffect="Ripple">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//defines the port hover connection effect as ripple.
diagram.PortHoverEffect = PortHoverEffect.Ripple;
{% endhighlight %}
{% endtabs %}

| PortHoverEffect | Output |
|---|---|
| Ripple |![Ripple aimation](Port_images/RippleAnimation.gif) |
| Shrink |![shrink diagram](Port_images/ShrinkAnimation.gif) |
| Node |Connection animation effect does not appeared. |
