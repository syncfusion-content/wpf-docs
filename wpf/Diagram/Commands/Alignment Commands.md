---
layout: post
title: Syncfusion | Explore the alignment functionalities with Alignment commands.
description: Alignment Commands are used to align the selected objects on a page with respect to a reference object(first item in selection list).
platform: wpf
control: SfDiagram
documentation: ug
---

# Alignment commands

Alignment commands are used to align the selected objects such as Nodes and Connectors on a page with respect to a reference object(first item in selection list).

## AlignLeft command 

AlignLeft command is used to align all the selected objects along the left corner of the reference object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Left
graphinfo.Commands.AlignLeft.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignRight command

AlignRight command is used to align all the selected objects along the Right corner of the reference object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Right
graphinfo.Commands.AlignRight.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignCenter command

AlignCenter command is used to center all selected objects vertically. It aligns selected objects to the center with respect to the horizontal axis by changing the x-coordinate of the object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Center vertically
graphinfo.Commands.AlignCenter.Execute(null);

{% endhighlight %}
{% endtabs %}

![Gif for Align commands](Commands_Images/Commands_img1.gif)

## AlignTop command 

AlignTop command is used to align all the selected objects along the top corner of the reference object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Top
graphinfo.Commands.AlignTop.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignBottom command

AlignBottom command is used to align all the selected objects along the Bottom corner of the reference object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Bottom
graphinfo.Commands.AlignBottom.Execute(null);

{% endhighlight %}
{% endtabs %}

## AlignMiddle command

AlignMiddle command is used to center all selected objects horizontally. It aligns selected objects to the center with respect to the vertical axis by changing the y-coordinate of the object.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// sets direction as Center horizontally
graphinfo.Commands.AlignCenter.Execute(null);

{% endhighlight %}
{% endtabs %}

![Gif for Align commands](Commands_Images/Commands_img2.gif)

Please find the [Alignment Commands sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Alignment_Commands124897265) to depict these commands. 