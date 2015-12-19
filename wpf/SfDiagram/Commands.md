# Commands

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

**Alignment** **Commands******

Alignment commands enable you to align the selected objects such as Nodes and Connectors on a page with respect to a reference object.

The Alignment commands as follows

<table>
<tr>
<td>
Commands<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
AlignLeft<br/><br/></td><td>
The AlignLeft command enables you to align all selected objects along the left corner of the reference object.<br/><br/></td></tr>
<tr>
<td>
AlignRight<br/><br/></td><td>
The AlignRight command enables you to align all selected objects along the right corner of the reference object.<br/><br/></td></tr>
<tr>
<td>
AlignCenter<br/><br/></td><td>
The AlignCenter command enables you to center all selected objects vertically. It aligns selected objects to the center with respect to the horizontal axis by changing the x-coordinate of the object<br/><br/></td></tr>
<tr>
<td>
AlignTop<br/><br/></td><td>
The AlignTop command enables you to align all selected objects along the top surface of the reference object.<br/><br/></td></tr>
<tr>
<td>
AlignBottom<br/><br/></td><td>
The AlignBottom command enables you to align all selected objects along the bottom surface of the reference object. <br/><br/></td></tr>
<tr>
<td>
AlignMiddle<br/><br/></td><td>
The AlignMiddle command enables you to center all selected objects horizontally. It aligns selected objects to the center with respect to the vertical axis by changing the y-coordinate of the object.<br/><br/></td></tr>
</table>

The following code example illustrates how to align all the selected objects at the left side of selection boundary.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// sets diration as left<br/><br/>graphinfo.Commands.AlignTop.Execute(null);<br/><br/><br/><br/></td></tr>
</table>


![](Commands_images/Commands_img1.jpeg)
![](Commands_images/Commands_img2.jpeg)
![](Commands_images/Commands_img3.jpeg)


![](Commands_images/Commands_img4.jpeg)


![](Commands_images/Commands_img5.jpeg)


![](Commands_images/Commands_img6.jpeg)


**Spacing** **Commands******

Spacing commands enable you to place selected objects on the page at equal intervals from each other. The objects are spaced within the bounds of the first and last objects in the selection.

The following code example illustrates how to execute the space commands.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// Equally spaces the selected nodes horizontally<br/><br/>graphinfo.Commands.SpaceAcross.Execute(null);<br/><br/>// Equally spaces the selected nodes vertically<br/><br/>graphinfo.Commands.SpaceDown.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
![](Commands_images/Commands_img7.jpeg)
![](Commands_images/Commands_img8.jpeg)


**Sizing** **Commands******

Object size commands enable selected Diagram objects on the page to be resized. The selected objects are resized in proportion to the first object in the selection list.

The following code example illustrates how to execute the size commands

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Scales the selected items to the size of first selected object<br/><br/>graphinfo.Commands.SameSize.Execute(null);<br/><br/>//Vertically scales the selected items to the height of first selected object<br/><br/>graphinfo.Commands.SameHeight.Execute(null);<br/><br/>//Horizontally scales the selected items to the width of first selected object<br/><br/>graphinfo.Commands.SameWidth.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
Before<br/><br/>{{'![](Commands_images/Commands_img9.jpeg)'| markdownify }}
<br/><br/></td><td>
After <br/><br/>{{'![](Commands_images/Commands_img10.jpeg)'| markdownify }}
{{'![](Commands_images/Commands_img11.jpeg)'| markdownify }}
{{'![](Commands_images/Commands_img12.jpeg)'| markdownify }}
<br/><br/></td></tr>
</table>
******Clipboard** **Commands******

Clipboard commands are used to perform cut, copy, and paste operations. 

Clipboard commands allow you to cut or copy selected Diagram objects to the Clipboard and paste the valid Clipboard content into the Diagram.

The following code illustrates how to execute the clipboard commands.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Cuts the selected elements from the Diagram to the Diagram’s clipboard<br/><br/>graphinfo.Commands.Cut.Execute(null);<br/><br/>//Copies the selected elements from the Diagram to the Diagram’s clipboard.<br/><br/>graphinfo.Commands.Copy.Execute(null);<br/><br/>//Pastes the Diagram’s clipboard data (nodes/connectors) into the Diagram.<br/><br/>graphinfo.Commands.Paste.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
********

****![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Commands_images/Commands_img6.png](Commands_images/Commands_img13.jpeg)
****

**Duplicate** **Command******

This command copies the selected objects from the diagram and pastes the copied content into the diagram.                           

![](Commands_images/Commands_img14.jpeg)


**Grouping** **Command******

Grouping commands are used to group/ungroup the selected elements on the diagram.

The following code illustrates how to execute the group commands

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Groups the selected elements.<br/><br/>graphinfo.Commands.Group.Execute(null);<br/><br/>//UnGroups the selected elements.<br/><br/>graphinfo.Commands.UnGroup.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
******Flip** **Commands******

Flip commands are used to mirror a diagram object’s content.

**Parameter******

To customize flipping, a parameter of type IFlipParameter has to be passed.

**IFlipParameter** **Properties******

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
Flip<br/><br/></td><td>
Gets or sets whether the object is to be mirrored horizontally, vertically, or both<br/><br/></td><td>
Enum<br/><br/>FlipFlip.HorizontalFlip<br/><br/>Flip.VerticalFlipFlip.Flip<br/><br/></td></tr>
</table>
******Execute** **Flip** **Command******

<table>
<tr>
<td>
// Flip Command<br/><br/>(diagramcontrol.Info as IGraphInfo).Commands.Flip.Execute(null);<br/><br/></td></tr>
</table>
****If the parameter is null, the object will be flipped both horizontally and vertically.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>FlipParameter flipParam = new FlipParameter();<br/><br/>// Horizontal Flip<br/><br/>flipParam.Flip = Flip.HorizontalFlip;<br/><br/>graphinfo.Commands.Flip.Execute(flipParam);<br/><br/>// Vertical Flip<br/><br/>flipParam.Flip = Flip.VerticalFlip;<br/><br/>graphinfo.Commands.Flip.Execute(flipParam);<br/><br/><br/><br/></td></tr>
</table>
Without Flip

****

With Flip



**********Z** **–** **Order** **Command******

Z – Order commands enable you to visually arrange the selected objects such as Nodes and Connectors on the page.

**BringToFront** **command******

The BringToFront command visually brings the selected element to the front over all other overlapped elements. 

The following code illustrates how to execute BringToFront command.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Brings to front<br/><br/>graphinfo.Commands.BringToFront.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
![](Commands_images/Commands_img15.jpeg)


**SendToBack** **command**

The SendToBack command visually moves the selected elements behind all the other overlapped elements. 

The following code illustrates how to execute the SendToBack command.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// Send To Back<br/><br/>graphinfo.Commands.SendToBack.Execute(null);<br/><br/><br/><br/></td></tr>
</table>


![](Commands_images/Commands_img16.jpeg)


**SendBackward** **command**

The SendBackward command visually moves the selected elements behind the underlying element.

The following code illustrates how to execute the SendBackward command.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// Send To Backward<br/><br/>graphinfo.Commands.SendBackward.Execute(null);<br/><br/><br/><br/></td></tr>
</table>


![](Commands_images/Commands_img17.jpeg)


******BringForward** **command******

The BringForward command visually moves the selected element over the nearest overlapping element.

The following code illustrates how to execute the BringForward command

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// Brings To Forward<br/><br/>graphinfo.Commands.BringForward.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
![](Commands_images/Commands_img18.jpeg)


**Zoom** **Commands******

Zoom commands are used to  zoom-in and zoom-out the Diagram view.

To execute zoom commands, parameters of type IZoomParameter (IZoomManipulationParameter, IZoomPositionParameter, or IZoomPointerParameter) have to be passed.

**IZoomManipulationParameter** **Properties******

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
ManipulationArgs****<br/><br/></td><td>
Gets or sets the ManipulationDelta<br/><br/>RoutedEventArgs associated with the desired zoom function.****<br/><br/></td><td>
ManipulationDeltaRoutedEvent<br/><br/>Args****<br/><br/></td></tr>
</table>
******IZoomPositionParameter** **Property******

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
ZoomTo<br/><br/></td><td>
Gets or sets the zoom level to which the diagram is to be zoomed.****<br/><br/></td><td>
double<br/><br/></td></tr>
<tr>
<td>
ZoomFactor<br/><br/></td><td>
Gets or sets the percentage of scale value for each ZoomIn or ZoomOut function.****<br/><br/></td><td>
double<br/><br/></td></tr>
<tr>
<td>
FocusPoint<br/><br/></td><td>
Gets or sets the point of focus while zooming.****<br/><br/></td><td>
Point<br/><br/></td></tr>
<tr>
<td>
ZoomCommand<br/><br/></td><td>
Gets or sets whether zoom in or zoom out has to be performed.****<br/><br/></td><td>
Enum ZoomCommandZoomCommand.<br/><br/>ZoomInZoomCommand.ZoomOut****<br/><br/></td></tr>
</table>
******IZoomPointerParameter** **Property******

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
PointerArgs<br/><br/></td><td>
Gets or sets the PointerRoutedEventArgs associated with the desired zoom function.****<br/><br/></td><td>
PointerRoutedEventArgs****<br/><br/></td></tr>
<tr>
<td>
ZoomCommand<br/><br/></td><td>
Gets or sets whether zoom in or zoom out has to be performed****<br/><br/></td><td>
Enum<br/><br/><table><br/><tr><br/><td><br/>ZoomCommandZoomCommand.ZoomInZoomCommand.ZoomOut<br/><br/></td></tr>
</table>
### 

</td></tr>
</table>
****The following code illustrates how to zoom-in/zoom-out the diagram.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Zoom to a particular scale.<br/><br/>graphinfo.Commands.Zoom.Execute(new ZoomPositionParamenter() <br/><br/>{ <br/><br/>ZoomTo = 2, ZoomCommand = ZoomCommand.ZoomOut <br/><br/>});<br/><br/>//Zoom out based on zoom factor.<br/><br/>graphinfo.Commands.Zoom.Execute(new ZoomPositionParamenter() <br/><br/>{ <br/><br/>ZoomFactor = 2, ZoomCommand = ZoomCommand.ZoomOut <br/><br/>});<br/><br/><br/><br/></td></tr>
</table>
******Reset** **Commands******

Reset commands are used to reset horizontal Offset, vertical Offset, and zoom level of the Diagram.

To execute a reset command, a parameter of type IReset has to be passed.

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description** ****<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
Reset<br/><br/></td><td>
Gets or sets the reset function****<br/><br/></td><td>
Enum ResetReset.Zoom – To reset zoom level to 1,Reset.Pan – To reset Offsets to 0,Reset.ZoomPan****<br/><br/></td></tr>
</table>
******Execute** **ResetCommand******

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>// Reset<br/><br/>graphinfo.Commands.Reset.Execute(new ResetParameter() { Reset = Reset.Zoom });<br/><br/>****<br/><br/></td></tr>
</table>
******Draw** **Commands******

Draw commands are used to draw connections. They take parameters of type IDrawParameter.

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
DrawingTool<br/><br/></td><td>
Gets or sets a tool to draw.****<br/><br/></td><td>
Enum DrawingToolDrawingTool.Connector****<br/><br/></td></tr>
<tr>
<td>
Point<br/><br/></td><td>
Gets or sets the start point for drawing.****<br/><br/></td><td>
Point<br/><br/></td></tr>
<tr>
<td>
Node<br/><br/></td><td>
Gets or sets the source Node of the new connection****<br/><br/></td><td>
Object<br/><br/></td></tr>
<tr>
<td>
Port<br/><br/></td><td>
Gets or sets the source port of the new connection****<br/><br/></td><td>
Object<br/><br/></td></tr>
<tr>
<td>
PressedEventArgs<br/><br/></td><td>
Gets or sets the PressedEventArgs.****<br/><br/></td><td>
PointerRoutedEventArgs****<br/><br/></td></tr>
</table>
******Execute** **DrawCommand******

<table>
<tr>
<td>
void Button_PointerPressed(object sender, PointerRoutedEventArgs e)<br/><br/>{<br/><br/>IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>Point SourcePoint = new Point(200,200);<br/><br/><br/><br/>graphinfo.Commands.Draw.Execute(<br/><br/>new DrawParameter(<br/><br/>DrawingTool.Connector,<br/><br/>e,<br/><br/>SourcePoint,<br/><br/>SourceNode,<br/><br/>SourcePort));<br/><br/>}<br/><br/>****<br/><br/></td></tr>
</table>
******Undoing** **and** **Redoing** **Actions******

The Undo command reverses the last editing action performed. For example, some of the basic operations performed on diagram objects such as translation, rotation, resizing, grouping, ungrouping, changing z-order, addition, deletion, and so on, can be reversed. The Redo command restores the last editing action if no other actions have occurred since the last undo. ****

**Nudge** **Command******

Nudge commands move the selected elements towards up, down, left or right by 1 pixel.

The Nudge Commands as follows

<table>
<tr>
<td>
Commands<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
NudgeUp<br/><br/></td><td>
The NudgeUp command moves the selected object towards the top by 1 pixel. <br/><br/></td></tr>
<tr>
<td>
NudgeDown<br/><br/></td><td>
The NudgeDown command moves the selected object towards the bottom by 1 pixel. <br/><br/></td></tr>
<tr>
<td>
NudgeLeft<br/><br/></td><td>
The NudgeLeft command moves the selected object towards the left by 1 pixel. <br/><br/></td></tr>
<tr>
<td>
NudgeRight<br/><br/></td><td>
The NudgeRight command moves the selected object towards the right by 1 pixel. <br/><br/></td></tr>
</table>

The following code illustrates how to execute Nudge command.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>//Nudges up<br/><br/>graphinfo.Commands.MoveUp.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
**FitToPage** **Command******

FitToPage commands are used to bring the entire Diagram into the view.

<table>
<tr>
<td>
**Command******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Value******<br/><br/></td></tr>
<tr>
<td>
FitToPage<br/><br/></td><td>
Gets or sets whether the Diagram is to fit into the view in terms of its width, height, or entirety.<br/><br/></td><td>
Enum FitToPageFitToPage.FitToPageFitToPage.FitToHeightFitToPage.FitToWidth<br/><br/></td></tr>
<tr>
<td>
Margin<br/><br/></td><td>
Gets or sets the margin value from the view to Diagram.<br/><br/></td><td>
Thickness<br/><br/></td></tr>
</table>
The following code illustrates how to execute FitToPage command.

<table>
<tr>
<td>
IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;<br/><br/>graphinfo.Commands.FitToPage.Execute(<br/><br/>new FitToPageParameter()<br/><br/>{<br/><br/>Margin = new Thickness(25),<br/><br/>//To fit the diagram with respect to width/height use FitToWidth or FitToHeight.<br/><br/>FitToPage = FitToPage.FitToPage<br/><br/>});<br/><br/>(or)<br/><br/>graphinfo.Commands.FitToPage.Execute(null);<br/><br/><br/><br/></td></tr>
</table>
**Command** **Manager******

Command manager is used to map between user gestures (keyboard, mouse) with commands. Refer to the following table for inbuilt commands with Key Gesture and Mouse Gesture.

List of Commands and Key Gesture:

<table>
<tr>
<td>
**Command******<br/><br/></td><td>
**Key******<br/><br/></td><td>
**Key** **Modifiers******<br/><br/></td></tr>
<tr>
<td>
Copy<br/><br/></td><td>
C<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Cute<br/><br/></td><td>
X<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Paste<br/><br/></td><td>
V<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Duplicate<br/><br/></td><td>
D<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Undo<br/><br/></td><td>
Z<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Redo<br/><br/></td><td>
Y<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
MoveLeft<br/><br/></td><td>
Left<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
MoveRight<br/><br/></td><td>
Right<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
MoveUp<br/><br/></td><td>
Up<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
MoveDown<br/><br/></td><td>
Down<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
Delete<br/><br/></td><td>
Delete<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
SelectAll<br/><br/></td><td>
A<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
Group<br/><br/></td><td>
G<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
UnGroup<br/><br/></td><td>
G<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
SendToBack<br/><br/></td><td>
[<br/><br/></td><td>
Control+Shift<br/><br/></td></tr>
<tr>
<td>
SendBackward<br/><br/></td><td>
[<br/><br/></td><td>
Control<br/><br/></td></tr>
<tr>
<td>
BringToFront<br/><br/></td><td>
]<br/><br/></td><td>
Control+Shift<br/><br/></td></tr>
<tr>
<td>
BringForward<br/><br/></td><td>
]<br/><br/></td><td>
Control<br/><br/></td></tr>
</table>
List of Commands and Key Gestures with Parameter:

<table>
<tr>
<td>
**Command******<br/><br/></td><td>
**Key******<br/><br/></td><td>
**KeyModifier******<br/><br/></td><td>
**Parameter******<br/><br/></td></tr>
<tr>
<td>
Zoom<br/><br/></td><td>
-<br/><br/></td><td>
Control<br/><br/></td><td>
new ZoomPositionParamenter { ZoomCommand=ZoomCommand.ZoomOut}<br/><br/></td></tr>
<tr>
<td>
Zoom<br/><br/></td><td>
+<br/><br/></td><td>
Control<br/><br/></td><td>
new ZoomPositionParamenter { ZoomCommand = ZoomCommand.ZoomIn }<br/><br/></td></tr>
<tr>
<td>
Reset<br/><br/></td><td>
0<br/><br/></td><td>
Control<br/><br/></td><td>
new ResetParameter { Reset = Diagram.Reset.ZoomPan }<br/><br/></td></tr>
<tr>
<td>
FitToPage<br/><br/></td><td>
0<br/><br/></td><td>
Control+ Menu<br/><br/></td><td>
new FitToPageParameter { FitToPage = Diagram.FitToPage.FitToPage, Margin = new Thickness(20) }<br/><br/></td></tr>
</table>
List of Commands and Mouse Gesture with Parameter

<table>
<tr>
<td>
**Command******<br/><br/></td><td>
**Scroll** **State******<br/><br/></td><td>
**Parameter******<br/><br/></td></tr>
<tr>
<td>
Vertical Scroll using ‘Zoom’ command<br/><br/></td><td>
Scroll<br/><br/></td><td>
new ZoomPointerParamenter { ZoomCommand = ZoomCommand.VerticalScroll}<br/><br/></td></tr>
</table>
List of Commands and Key and Mouse Gesture with Parameter:

<table>
<tr>
<td>
**Command**<br/><br/></td><td>
**KeyModifier**<br/><br/></td><td>
**Scroll** **State**<br/><br/></td><td>
**Parameter**<br/><br/></td></tr>
<tr>
<td>
Horizontal Scroll using ‘Zoom’ command<br/><br/></td><td>
Shift<br/><br/></td><td>
Scroll<br/><br/></td><td>
new ZoomPointerParamenter { ZoomCommand = ZoomCommand.HorizondalScroll}<br/><br/></td></tr>
<tr>
<td>
Zoom<br/><br/></td><td>
Control<br/><br/></td><td>
Scroll<br/><br/></td><td>
new ZoomPointerParamenter { ZoomCommand = ZoomCommand.ZoomIn | ZoomCommand.ZoomOut}<br/><br/></td></tr>
</table>
**Note****:******

When different commands are registered for the same key / mouse gestures, you need to handle the command while execution.

**Custom** **command******

User defined commands can also be created and mapped with existing gesture by using command manager. The following code example explains how to register mouse key gesture with Parameter to Save Command (Control + S)

**Create** **a** **user** **defined** **command****:** **Save** **command******

<table>
<tr>
<td>
//Create ICommand<br/><br/>private ICommand _save;<br/><br/>public ICommand Save<br/><br/>{<br/><br/>get { return _save;}<br/><br/>set { _save = value; }<br/><br/>}<br/><br/><br/><br/>//Initialize Command<br/><br/>Save = new DelegateCommand(OnSaveCommand);<br/><br/><br/><br/>// Execute Command<br/><br/>private async void OnSaveCommand(Object obj)<br/><br/>{<br/><br/>var picker = new FileSavePicker();<br/><br/><br/><br/>// set appropriate file types<br/><br/><br/><br/>picker.FileTypeChoices.Add(".xaml", new List<String> {".xaml"});<br/><br/>picker.DefaultFileExtension = ".xaml";<br/><br/>Object parameter = (obj as IGestureParameter).Parameter;<br/><br/>picker.SuggestedFileName = parameter.ToString();<br/><br/>StorageFile file = await picker.PickSaveFileAsync();<br/><br/>using (var filestream = await file.OpenStreamForWriteAsync())<br/><br/>{<br/><br/>sfdiagram.Save(fileStream);<br/><br/>}<br/><br/>}<br/><br/></td></tr>
</table>
Map and user defined command with key gesture:****

<table>
<tr>
<td>
//Add new Commands to CommandManager - Cntrl + S -> Save<br/><br/><br/><br/>sfdiagram.CommandManager.Commands.Add<br/><br/>(<br/><br/>new GestureCommand()<br/><br/>{<br/><br/>Command = Save,<br/><br/>Gesture = new Gesture<br/><br/>{<br/><br/>KeyModifiers = ModifierKeys.Control,<br/><br/>KeyState = KeyStates.Down,<br/><br/>Key = Key.S<br/><br/>},<br/><br/>// Parameter is the name of the file (.xmal)<br/><br/>Parameter = "diagram"<br/><br/>}<br/><br/>);<br/><br/><br/><br/></td></tr>
</table>
