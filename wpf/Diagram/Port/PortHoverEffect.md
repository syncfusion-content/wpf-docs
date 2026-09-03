---
layout: post
title: Port Hover Effects in WPF SfDiagram | Syncfusion®
description: Learn about port hover effects in Syncfusion® WPF SfDiagram control, including ripple, shrink, filled ripple, and connection animation options.
platform: wpf
control: SfDiagram
documentation: ug
---

# Port Hover Effects in WPF SfDiagram

When establishing a new connection or modifying the start/end points of existing connector over a port, an animation will be shown while hovering on port. This animation is used to indicate that the user is hovering over the tiny port, which helps to start/end the connection to the ports. The [PortHoverEffect](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramViewModel.html#Syncfusion_UI_Xaml_Diagram_DiagramViewModel_PortHoverEffect) property of [SfDiagram](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramViewModel.html#Syncfusion_UI_Xaml_Diagram) class allows you to specify the any one of the following animation effects. The default effect is `Ripple`.

* **Ripple:** Specifies the water ripple circles type animation effect for connection.
* **Shrink:** Specifies the plus symbol type animation effect for connection.
* **None:** Specifies no connection animation effect.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram with port hover effect as ripple-->
<syncfusion:SfDiagram x:Name="diagram" PortHoverEffect="Ripple">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
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
| FilledRipple |![Filled Ripple](Port_images/FilledRippleAnimation.gif) |
| None | Connection animation effect does not appear. |

## See Also
[How to change the PortHover effect color in the WPF SfDiagram?](https://support.syncfusion.com/kb/article/17720/how-to-change-the-porthover-effect-color-in-the-wpf-diagram)