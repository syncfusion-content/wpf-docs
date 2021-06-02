---
layout: post
title: Syncfusion | Explore the frequently used inbuilt commands.
description:  How to explore and use the inbuilt commands to align, position, sizing, grouping, ordering, scaling, serialize the diagram objects in easy way?
platform: wpf
control: SfDiagram
documentation: ug
---

# Commands in WPF Diagram (SfDiagram) control

Diagram provides set of commands to perform the functionalities in application.

* Alignment commands
* Spacing commands
* Sizing commands
* Clipboard commands
* Duplicate Command
* Grouping commands
* Flip commands
* Z-order commands
* Zoom commands
* Reset command
* Nudge commands
* FitToPage command
* Undo/Redo command

## Alignment

Alignment commands enable you to align the selected objects such as Nodes and Connectors on a page with respect to a reference object.

The Alignment commands as follows.

| Commands | Description |
|---|---|---|
| AlignLeft | The AlignLeft command enables you to align all selected objects along the left corner of the reference object. |
| AlignRight | The AlignRight command enables you to align all selected objects along the right corner of the reference object. |
| AlignCenter | The AlignCenter command enables you to center all selected objects vertically. It aligns selected objects to the center with respect to the horizontal axis by changing the x-coordinate of the object. |
| AlignTop | The AlignTop command enables you to align all selected objects along the top surface of the reference object. |
| AlignBottom | The AlignBottom command enables you to align all selected objects along the bottom surface of the reference object. |
| AlignMiddle | The AlignMiddle command enables you to center all selected objects horizontally. It aligns selected objects to the center with respect to the vertical axis by changing the y-coordinate of the object. |

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
//sets direction as Top
graphinfo.Commands.AlignTop.Execute(null);

{% endhighlight %}
{% endtabs %}

## Spacing

Spacing commands enable you to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Equally spaces the selected nodes horizontally
graphinfo.Commands.SpaceAcross.Execute(null);

//Equally spaces the selected nodes vertically
graphinfo.Commands.SpaceDown.Execute(null);

{% endhighlight %}
{% endtabs %}

## Sizing

Object size commands will be resized all selected object based on width, height and size of the first object in the selection list.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Scales the selected items to the size of first selected object
graphinfo.Commands.SameSize.Execute(null);

//Vertically scales the selected items to the height of first selected object
graphinfo.Commands.SameHeight.Execute(null);

//Horizontally scales the selected items to the width of first selected object
graphinfo.Commands.SameWidth.Execute(null);

{% endhighlight %}
{% endtabs %}

## Clipboard

Clipboard commands are used to perform Cut, Copy and Paste operations. 

Clipboard commands allow you to cut or copy selected Diagram objects to the Clipboard and paste the valid Clipboard content into the Diagram.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
//Cuts the selected elements from the Diagram to the Diagram’s clipboard
graphinfo.Commands.Cut.Execute(null);

//Copies the selected elements from the Diagram to the Diagram’s clipboard.
graphinfo.Commands.Copy.Execute(null);

//Pastes the Diagram’s clipboard data (nodes/connectors) into the Diagram.
graphinfo.Commands.Paste.Execute(null);

{% endhighlight %}
{% endtabs %}

## Duplicate

This command copies the selected objects from the diagram and pastes the copied content into the diagram.                           

![Commands SelectByType Image](Commands/Commands_images/Commands_SelectByType.gif)

## Grouping

Grouping commands are used to group/ungroup the selected elements on the diagram.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Groups the selected elements.
graphinfo.Commands.Group.Execute(null);

//UnGroups the selected elements.
graphinfo.Commands.UnGroup.Execute(null);

{% endhighlight %}
{% endtabs %}

## Flip

Flip commands are used to mirror a diagram object’s content. [IFlip parameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FlipParameter.html) is provided to customize the flip. 
If the parameter is null, the object will be flipped both horizontally and vertically.

{% tabs %}
{% highlight C# %}

//Apply flip to selected objects.
(diagramcontrol.Info as IGraphInfo).Commands.Flip.Execute(null);

{% endhighlight %}
{% endtabs %}

![Represents the flip](Commands/Commands_images/Commands_img7.gif)

## Z – Order

Z – Order commands enable you to visually arrange the selected objects such as Nodes and Connectors on the page.

### BringToFront

The BringToFront command visually brings the selected element to the front over all other overlapped elements. 

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Brings to front
graphinfo.Commands.BringToFront.Execute(null);

{% endhighlight %}
{% endtabs %}

### SendToBack

The SendToBack command visually moves the selected elements behind all the other overlapped elements. 

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Send To Back
graphinfo.Commands.SendToBack.Execute(null);

{% endhighlight %}
{% endtabs %}

![Represents the send to back](Commands/Commands_images/Commands_img8.gif)

### SendBackward

The SendBackward command visually moves the selected elements behind the underlying element.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Send To Backward
graphinfo.Commands.SendBackward.Execute(null);

{% endhighlight %}
{% endtabs %}

### BringForward

The BringForward command visually moves the selected element over the nearest overlapping element.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Brings To Forward
graphinfo.Commands.BringForward.Execute(null);

{% endhighlight %}
{% endtabs %}

![Represents the bring forward](Commands/Commands_images/Commands_img9.gif)

## Zoom

Zoom commands are used to zoom-in and zoom-out the Diagram view.

To execute zoom commands, parameters of type IZoomParameter ([IZoomManipulationParameter](https://help.syncfusion.com/cr//wpf/Syncfusion.UI.Xaml.Diagram.ZoomManipulationParamenter.html#Syncfusion_UI_Xaml_Diagram_ZoomManipulationParamenter_members), [IZoomPositionParameter](https://help.syncfusion.com/cr//wpf/Syncfusion.UI.Xaml.Diagram.ZoomPositionParameter.html#Syncfusion_UI_Xaml_Diagram_ZoomPositionParameter_members), or [IZoomPointerParameter](https://help.syncfusion.com/cr//wpf/Syncfusion.UI.Xaml.Diagram.IZoomPointerParameter.html#Syncfusion_UI_Xaml_Diagram_IZoomPointerParameter_members)) have to be passed.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Zoom to a particular scale.
graphinfo.Commands.Zoom.Execute(new ZoomPositionParameter() 
{ 
	ZoomTo = 2, ZoomCommand = ZoomCommand.ZoomOut 
});

{% endhighlight %}
{% endtabs %}

## Reset

Reset commands are used to reset horizontal Offset, vertical Offset, and zoom level of the Diagram. To execute a reset command, a parameter of type [IReset](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ResetParameter.html) has to be passed.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

// Reset the Zoom level of the Diagram
graphinfo.Commands.Reset.Execute(new ResetParameter() { Reset = Reset.Zoom });

{% endhighlight %}
{% endtabs %}

## Undo and Redo

The Undo command reverses the last editing action performed. For example, some of the basic operations performed on diagram objects such as translation, rotation, resizing, grouping, ungrouping, changing z-order, addition, deletion, and so on, can be reversed. The Redo command restores the last editing action if no other actions have occurred since the last undo.

Undo and Redo actions are disabled by default, to enable this you can use `Constraints` property of the SfDiagram.  Please refer to the [GraphConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GraphConstraints.html)

{% tabs %}
{% highlight C# %}

// To enable the Undo and Redo action
diagram.Constraints |= GraphConstraints.Undoable;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//To perform the Undo action in Diagram
graphinfo.Commands.Undo.Execute(null);

//To Perform the Redo action in Diagram
graphinfo.Commands.Redo.Execute(null);

{% endhighlight %}
{% endtabs %}

## Nudge

Nudge commands move the selected elements towards up, down, left or right by 1 pixel. [IMoveParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.MoveParameter.html) is provided to customize the movement of the selected objects. The Nudge Commands as follows.

| Commands | Description |
|---|---|
| NudgeUp | The NudgeUp command moves the selected object towards the top by 1 pixel. |
| NudgeDown | The NudgeDown command moves the selected object towards the bottom by 1 pixel. |
| NudgeLeft | The NudgeLeft command moves the selected object towards the left by 1 pixel. |
| NudgeRight | The NudgeRight command moves the selected object towards the right by 1 pixel. |

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

//Nudge up the selected objects
graphinfo.Commands.MoveUp.Execute(null);

{% endhighlight %}
{% endtabs %}

## FitToPage

FitToPage commands are used to bring the entire Diagram into the view. [IFitToPage parameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html) is provided to customize the FitToPage.
If the parameter is null, entire Diagram is fit into the view.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
//To fit the Diagram into the view
graphinfo.Commands.FitToPage.Execute(null);

{% endhighlight %}
{% endtabs %}

## Command Manager
Command manager is used to map between user gestures (keyboard, mouse) with commands. Refer to the following table for built-in commands with Key Gesture and Mouse Gesture.

List of Commands and Key Gesture:

| Command | Key | Key Modifiers |
|---|---|---|
| Copy | C | Control |
| Cut | X| Control |
| Paste | V | Control |
| Duplicate | D | Control |
| Undo | Z | Control |
| Redo | Y | Control |
| MoveLeft | | Left |	
| MoveRight | |	Right |	
| MoveUp | | Up |	
| MoveDown | | Down |	
| Delete | | Delete |	
| SelectAll | A	| Control |
| Group| G|	Control |
| UnGroup | G | Control |
| SendToBack | [ | Control+Shift |
| SendBackward | [ | Control |
| BringToFront | ] | Control+Shift |
| BringForward | ] | Control |

#### List of Commands and Key Gestures with Parameter

| Command | Key | KeyModifier | Parameter |
|---|---|---|---|
| Zoom | - | Control | new ZoomPositionParameter { ZoomCommand=ZoomCommand.ZoomOut} |
| Zoom | + | Control | new ZoomPositionParameter { ZoomCommand = ZoomCommand.ZoomIn } |
| Reset | 0 | Control | new ResetParameter { Reset = Diagram.Reset.ZoomPan } |
| FitToPage | 0 | Control+ Menu | new FitToPageParameter { FitToPage = Diagram.FitToPage.FitToPage, Margin = new Thickness(20) } |

#### List of Commands and Mouse Gesture with Parameter

| Command | Scroll State | Parameter |
|---|---|---|
| Vertical Scroll using ‘Zoom’ command | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.VerticalScroll} |

#### List of Commands and Key and Mouse Gesture with Parameter

| Command | KeyModifier | Scroll State | Parameter |
|---|---|---|---|
| Horizontal Scroll using ‘Zoom’ command | Shift | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.HorizontalScroll} |
| Zoom | Control | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.ZoomIn `|` ZoomCommand.ZoomOut} |

N> When different commands are registered for the same key / mouse gestures, you need to handle the command while execution.

### Custom command

CommandManager provides support to define custom commands. The custom commands are executed, when the specified key gesture is recognized.
The [GestureCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GestureCommand.html) and [Gesture](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Gesture.html) helps to define a custom command.

The following code example represents how to define custom command to Save Command (Control + S).

{% tabs %}
{% highlight C# %}

//To define the mouse and keyboard gesture for the commands
GestureCommand saveGesture = new GestureCommand()
{
    //Define the command with custom command
    Command = Save,
    //Define gesture for custom Command
    Gesture = new Gesture
    {
        KeyModifiers = ModifierKeys.Control,
        KeyState = KeyStates.Down,
        Key = Key.S
    },
    //Parameter for command - file name for save command
    Parameter = "diagram"
};

//Add the custom command to the existsing command collection.
diagram.CommandManager.Commands.Add(saveGesture);
{% endhighlight %}
{% endtabs %}

Find the sample for [Custom Command](http://www.syncfusion.com/downloads/support/directtrac/219839/ze/CustomCommand1467218487).