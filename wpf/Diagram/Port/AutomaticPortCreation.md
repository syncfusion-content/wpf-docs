---
layout: post
title: Automatic port creation | Syncfusion
description: How to create port at runtime ?
platform: wpf
control: SfDiagram
documentation: ug
---

# Automatic port creation

Diagram supports option to create a port dynamically at the mouse cursor position over any node or connector just by click and drag over it. This behavior is disabled by default and can be enabled by using `GraphConstraints.AutomaticPortCreation`.

{% tabs %}
{% highlight xaml %}

<!--Enables AutomaticPortCreation of SfDiagram to create port at runtime while making connections.-->
<Syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible" Constraints="Default,AutomaticPortCreation">           
</Syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Enables AutomaticPortCreation of SfDiagram to create port at runtime while making connections.
diagram.Constraints |= GraphConstraints.AutomaticPortCreation;

{% endhighlight %}
{% endtabs %}

![AutomaticPortCreation](Port_images/AutomaticPortCreation.gif)