---
layout: post
title: Syncfusion | Explore the sizing functionalities Sizing commands.
description: Sizing commands are used to resize all selected object based on width, height and size of the reference object (FirstSelectedItem). 
platform: wpf
control: SfDiagram
documentation: ug
---

# Sizing commands

Sizing commands are used to resize all selected object based on width, height and size of the reference object (FirstSelectedItem).

## SameSize command

SameSize command is used to resize all the selected object based on the size of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Scales the selected items to the size of first selected object
graphinfo.Commands.SameSize.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameHeight command

SameHeight command is used to resize all the selected object based on the height of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Vertically scales the selected items to the height of first selected object
graphinfo.Commands.SameHeight.Execute(null);

{% endhighlight %}
{% endtabs %}

## SameWidth command

SameWidth command is used to resize all the selected object based on the width of the first item in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Horizontally scales the selected items to the width of first selected object
graphinfo.Commands.SameWidth.Execute(null);

{% endhighlight %}
{% endtabs %}

![Sizing commands](Commands_Images/Commands_img5.gif)

Please find the [Sizing commands sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Sizing_Commands1595367346) to depict these commands.