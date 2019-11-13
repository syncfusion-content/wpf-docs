---
layout: post
title: Syncfusion | Explore the Spacing commands.
description:  Spacing commands are used to place selected objects on the page at equal intervals from each other in both vertically and horizontally.
platform: wpf
control: SfDiagram
documentation: ug
---

# Spacing commands

Spacing commands are used to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

## SpaceAcross command

SpaceAcross command is used to place selected objects on the page at equal intervals from each other horizontally.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes horizontally
graphinfo.Commands.SpaceAcross.Execute(null);

{% endhighlight %}
{% endtabs %}

![SPace Across](Commands_images/Commands_img3.gif)

## SpaceDown command

SpaceDown command is used to place selected objects on the page at equal intervals from each other vertically.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes vertically
graphinfo.Commands.SpaceDown.Execute(null);

{% endhighlight %}
{% endtabs %}

![SPace Down](Commands_images/Commands_img4.gif)

Please find the [Spacing commands sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Spacing_Commands1910544000) to depict these commands.