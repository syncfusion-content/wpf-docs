---
layout: post
title: Commands | SfDiagram | wpf | Syncfusion
description: commands
platform: wpf
control: SfDiagram
documentation: ug
---

## Commands

There are several commands available in the Diagram as follows.

* Alignment commands

* Spacing commands

* Sizing commands

* Clipboard commands

* Duplicate Command

* Grouping commands

* Flip Commands

* Z-order commands

* Zoom commands

* Reset Command

* Draw Commands

* Nudge commands

* FitToPage commands

* Undo/Redo commands



**Alignment Commands**

Alignment commands enable you to align the selected objects such as Nodes and Connectors on a page with respect to a reference object.

The Alignment commands as follows

<table>
<tr>
<td>
Commands</td><td>
Description</td></tr>
<tr>
<td>
AlignLeft</td><td>
The AlignLeft command enables you to align all selected objects along the left corner of the reference object.</td></tr>
<tr>
<td>
AlignRight</td><td>
The AlignRight command enables you to align all selected objects along the right corner of the reference object.</td></tr>
<tr>
<td>
AlignCenter</td><td>
The AlignCenter command enables you to center all selected objects vertically. It aligns selected objects to the center with respect to the horizontal axis by changing the x-coordinate of the object.</td></tr>
<tr>
<td>
AlignTop</td><td>
The AlignTop command enables you to align all selected objects along the top surface of the reference object.</td></tr>
<tr>
<td>
AlignBottom</td><td>
The AlignBottom command enables you to align all selected objects along the bottom surface of the reference object. </td></tr>
<tr>
<td>
AlignMiddle</td><td>
The AlignMiddle command enables you to center all selected objects horizontally. It aligns selected objects to the center with respect to the vertical axis by changing the y-coordinate of the object.</td></tr>
</table>

The following code example illustrates how to align all the selected objects at the left side of selection boundary.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// sets diration as left

graphinfo.Commands.AlignTop.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img1.png)![](Commands_images\Commands_img2.png)![](Commands_images\Commands_img3.png)

![](Commands_images\Commands_img4.png)

![](Commands_images\Commands_img5.png)

![](Commands_images\Commands_img6.png)

**Spacing Commands**

Spacing commands enable you to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

The following code example illustrates how to execute the space commands.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Equally spaces the selected nodes horizontally

graphinfo.Commands.SpaceAcross.Execute(null);

// Equally spaces the selected nodes vertically

graphinfo.Commands.SpaceDown.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img7.png)![](Commands_images\Commands_img8.png)

**Sizing Commands**

Object size commands enable selected Diagram objects on the page to be resized. The selected objects are resized in proportion to the first object in the selection list.

The following code example illustrates how to execute the size commands.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Scales the selected items to the size of first selected object

graphinfo.Commands.SameSize.Execute(null);

//Vertically scales the selected items to the height of first selected object

graphinfo.Commands.SameHeight.Execute(null);

//Horizontally scales the selected items to the width of first selected object

graphinfo.Commands.SameWidth.Execute(null);

{% endhighlight %}



<table>
<tr>
<td>
          Before<img src="Commands_images\Commands_img9.png" alt="" width="177pt" height="332pt"</td><td>
                                    After <img src="Commands_images\Commands_img10.png" alt="" width="125pt" height="312pt"<img src="Commands_images\Commands_img11.png" alt="" width="164pt" height="317pt"<img src="Commands_images\Commands_img12.png" alt="" width="120pt" height="306pt"</td></tr>
</table>


**Clipboard Commands**

Clipboard commands are used to perform cut, copy, and paste operations. 

Clipboard commands allow you to cut or copy selected Diagram objects to the Clipboard and paste the valid Clipboard content into the Diagram.

The following code illustrates how to execute the clipboard commands.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Cuts the selected elements from the Diagram to the Diagram’s clipboard

graphinfo.Commands.Cut.Execute(null);

//Copies the selected elements from the Diagram to the Diagram’s clipboard.

graphinfo.Commands.Copy.Execute(null);

//Pastes the Diagram’s clipboard data (nodes/connectors) into the Diagram.

graphinfo.Commands.Paste.Execute(null);

{% endhighlight %}

****

****![D:\Diagram\Diagram2015Vol4\2015 November 1st Sprint\UG\Diagram Images\Diagram\Commands_images\Commands_img6.png](Commands_images\Commands_img13.png)

**Duplicate Command**

This command copies the selected objects from the diagram and pastes the copied content into the diagram.                           

![](Commands_images\Commands_img14.png)

**Grouping Command**

Grouping commands are used to group/ungroup the selected elements on the diagram.

The following code illustrates how to execute the group commands

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Groups the selected elements.

graphinfo.Commands.Group.Execute(null);

//UnGroups the selected elements.

graphinfo.Commands.UnGroup.Execute(null);

{% endhighlight %}

**Flip Commands**

Flip commands are used to mirror a diagram object’s content.

**Parameter**

To customize flipping, a parameter of type IFlipParameter has to be passed.

**IFlipParameter Properties**

<table>
<tr>
<td>
<b>Property</b></td><td>
<b>Description</b></td><td>
<b>Value</b></td></tr>
<tr>
<td>
Flip</td><td>
Gets or sets whether the object is to be mirrored horizontally, vertically, or both</td><td>
EnumFlipFlip.HorizontalFlipFlip.VerticalFlipFlip.Flip</td></tr>
</table>


**Execute Flip Command**

{% highlight C# %}

// Flip Command

(diagramcontrol.Info as IGraphInfo).Commands.Flip.Execute(null);

{% endhighlight %}

If the parameter is null, the object will be flipped both horizontally and vertically.

{% highlight C# %}


IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

FlipParameter flipParam = new FlipParameter();

// Horizontal Flip

flipParam.Flip = Flip.HorizontalFlip;

graphinfo.Commands.Flip.Execute(flipParam);

// Vertical Flip

flipParam.Flip = Flip.VerticalFlip;

graphinfo.Commands.Flip.Execute(flipParam);

{% endhighlight %}

Without Flip

![](Commands_images\Commands_img15.png)

With Flip

![](Commands_images\Commands_img16.png)![](Commands_images\Commands_img17.png)![](Commands_images\Commands_img18.png)


**Z – Order Command**

Z – Order commands enable you to visually arrange the selected objects such as Nodes and Connectors on the page.

**BringToFront command**

The BringToFront command visually brings the selected element to the front over all other overlapped elements. 

The following code illustrates how to execute BringToFront command.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Brings to front

graphinfo.Commands.BringToFront.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img19.png)

**SendToBack command**

The SendToBack command visually moves the selected elements behind all the other overlapped elements. 

The following code illustrates how to execute the SendToBack command.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Send To Back

graphinfo.Commands.SendToBack.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img20.png)

**SendBackward command**

The SendBackward command visually moves the selected elements behind the underlying element.

The following code illustrates how to execute the SendBackward command.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Send To Backward

graphinfo.Commands.SendBackward.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img21.png)

**BringForward command**

The BringForward command visually moves the selected element over the nearest overlapping element.

The following code illustrates how to execute the BringForward command.

{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Brings To Forward

graphinfo.Commands.BringForward.Execute(null);

{% endhighlight %}

![](Commands_images\Commands_img22.png)

**Zoom Commands**

Zoom commands are used to  zoom-in and zoom-out the Diagram view.

To execute zoom commands, parameters of type IZoomParameter (IZoomManipulationParameter, IZoomPositionParameter, or IZoomPointerParameter) have to be passed.

**IZoomManipulationParameter Properties**

<table>
<tr>
<td>
<b>Property</b></td><td>
<b>Description</b></td><td>
<b>Value</b></td></tr>
<tr>
<td>
ManipulationArgs</td><td>
Gets or sets the ManipulationDeltaRoutedEventArgs associated with the desired zoom function.</td><td>
ManipulationDeltaRoutedEventArgs</td></tr>
</table>


**IZoomPositionParameter Property**

<table>
<tr>
<td>
<b>Property</b></td><td>
<b>Description</b></td><td>
<b>Value</b></td></tr>
<tr>
<td>
ZoomTo</td><td>
Gets or sets the zoom level to which the diagram is to be zoomed.</td><td>
double</td></tr>
<tr>
<td>
ZoomFactor</td><td>
Gets or sets the percentage of scale value for each ZoomIn or ZoomOut function.</td><td>
double</td></tr>
<tr>
<td>
FocusPoint</td><td>
Gets or sets the point of focus while zooming.</td><td>
Point</td></tr>
<tr>
<td>
ZoomCommand</td><td>
Gets or sets whether zoom in or zoom out has to be performed.</td><td>
Enum ZoomCommandZoomCommand.ZoomInZoomCommand.ZoomOut</td></tr>
</table>


**IZoomPointerParameter Property**

<table>
<tr>
<td>
<b>Property</b></td><td>
<b>Description</b></td><td>
<b>Value</b></td></tr>
<tr>
<td>
PointerArgs</td><td>
Gets or sets the PointerRoutedEventArgs associated with the desired zoom function.</td><td>
PointerRoutedEventArgs</td></tr>
<tr>
<td>
ZoomCommand</td><td>
Gets or sets whether zoom in or zoom out has to be performed</td><td>
EnumZoomCommandZoomCommand.ZoomInZoomCommand.ZoomOut### <br><br></td></tr>
</table>
