---
layout: post
title: API | SfDiagram | wpf | Syncfusion
description: api
platform: wpf
control: SfDiagram
documentation: ug
---

# API

SfDiagram Properties

The following table lists the General Properties associated with the SfDiagram control:

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
Constraints</td><td>
Gets or sets the Constraints Type.</td><td>
 Enum GraphConstraints.None GraphConstraints.Zoomable GraphConstraints.Pannable GraphConstraints.PannableX GraphConstraints.PannableY GraphConstraints.PanRails GraphConstraints.PanRailsX GraphConstraints.PanRailsY GraphConstraints.Undoable GraphConstraints.Virtualize GraphConstraints.Relationship GraphConstraints.Events GraphConstraints.Bridging GraphConstraints.LineRouting GraphConstraints.Default</td></tr>
<tr>
<td>
DefaultConnectorType</td><td>
Gets or sets the Connector Type.</td><td>
 Enum ConnectorType.Line ConnectorType.Orthogonal</td></tr>
<tr>
<td>
DragOverNode</td><td>
Gets or sets the Node to be specified for DrawingTool.</td><td>
 Node</td></tr>
<tr>
<td>
DragOverPort</td><td>
Gets or sets the Node Port to be specified for DrawingTool.</td><td>
 NodePort</td></tr>
<tr>
<td>
DrawingTool</td><td>
Gets or sets the DrawingTool Type.</td><td>
 Enum DrawingTool.Connector</td></tr>
<tr>
<td>
LayoutManager</td><td>
Gets or sets the LayoutManager of SfDiagram.</td><td>
 LayoutManager</td></tr>
<tr>
<td>
MultipleSelectionMode</td><td>
Gets or sets the MultipleSelectionMode type.</td><td>
 Enum MultipleSelectionMode.None MultipleSelectionMode.RubberBandCompleteIntersect MultipleSelectionMode.RubberBandPartialIntersect MultipleSelectionMode.JustTap MultipleSelectionMode.HoldKeyAndTap MultipleSelectionMode.Default</td></tr>
<tr>
<td>
SnapSettings</td><td>
Defines SnapConstraints and Gridlines.</td><td>
SnapSettings</td></tr>
<tr>
<td>
Tool</td><td>
Gets or sets the Tool Type.</td><td>
 Enum Tool.None Tool.SingleSelect        <br> Tool.MultipleSelect Tool.ZoomPan Tool.DrawOnce  <br> Tool.ContinuesDraw</td></tr>
<tr>
<td>
ViewDictionary</td><td>
Gets or sets the Data Template Dictionary.</td><td>
 DataTemplateDictionary</td></tr>
<tr>
<td>
ViewPort</td><td>
Gets the ViewPort of SfDiagram.</td><td>
 Rect</td></tr>
<tr>
<td>
DefaultConnectorType</td><td>
Gets or sets the drawing tool type.</td><td>
EnumConnectorType.LineConnectorType.OrthogonalConnectorType.CubicBezierConnectorType.QuadraticBezierConnectorType.PolyCubicBezier </td></tr>
<tr>
<td>
BezierSmooth</td><td>
Enables or disables the ability to customize line smoothness.</td><td>
EnumBezierSmooth.NoneBezierSmooth.SymmetricAngleBezierSmooth.SymmetricDistanceBezierSmooth.Symmetric</td></tr>
<tr>
<td>
HorizontalRuler</td><td>
Gets or sets the HorizontalRuler</td><td>
Ruler</td></tr>
<tr>
<td>
VerticalRuler</td><td>
Gets or sets the VerticalRuler</td><td>
Ruler</td></tr>
<tr>
<td>
ExportBitmapEncoder</td><td>
Gets or Sets the ExportBitmapEncoder</td><td>
BitmapEncoder</td></tr>
<tr>
<td>
ExportMode</td><td>
Gets or Sets the  ExportMode</td><td>
EnumExportMode.ContentExportMode.PageSettings</td></tr>
<tr>
<td>
BitmapAlphaMode</td><td>
Gets or Sets the BitmapAlphaMode</td><td>
Enum<br>BitmapAlphaMode.PremultipliedBitmapAlphaMode.StraightBitmapAlphaMode.Ignore</td></tr>
<tr>
<td>
BitmapPixelFormat</td><td>
Gets or Sets the BitmapPixelFormat</td><td>
EnumBitmapPixelFormat.UnknownBitmapPixelFormat.Rgba16BitmapPixelFormat.Rgba8BitmapPixelFormat.Rgba8</td></tr>
<tr>
<td>
Constraints</td><td>
Gets or sets constraints.</td><td>
EnumStencilConstraints.NoneStencilConstraints.ShowPreviewStencilConstraints.FiltersStencilConstraints.Default</td></tr>
<tr>
<td>
ExpandMode</td><td>
Gets or sets ExpandMode.</td><td>
Enum<br>ExpandMode.OneExpandMode.OneOrMoreExpandMode.ZeroOrOneExpandMode.ZeroOrMore</td></tr>
<tr>
<td>
PrintOrientation</td><td>
Gets or sets the print orientation.</td><td>
EnumPrintOrientation.Portrait,PrintOrientation.LandscapeThe default value is PrintOrientation.Landscape</td></tr>
<tr>
<td>
PrintMediaSize</td><td>
Gets or sets the size of the print media.</td><td>
EnumPrintMediaSize.NorthAmericaLetter,PrintMediaSize.IsoA4,PrintMediaSize.IsoA3More options are available in PrintMediaSize.<br>The default value is PrintMediaSize.NorthAmericaLetter</td></tr>
<tr>
<td>
PrintMargin</td><td>
Gets or sets the print margin.</td><td>
Thickness</td></tr>
</table>

### Methods

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Export</td><td>
Void Export()</td><td>
This method is used to export the diagram as an Image. </td></tr>
<tr>
<td>
PrepareDragDropPreview</td><td>
Void PrepareDragDropPreview()</td><td>
This virtual method is used to customize the drag and drop preview.</td></tr>
<tr>
<td>
RegisterForPrinting</td><td>
void RegisterForPrinting()</td><td>
This method is used to register the printing task to the printer.A printing task can be registered at once.</td></tr>
<tr>
<td>
UnregisterForPrinting</td><td>
void UnregisterForPrinting()</td><td>
This method is used to unregister the printing task from the printer.</td></tr>
</table>

### INode Properties

The following table lists the Properties associated with INode of the SfDiagram control:

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
 Value</td></tr>
<tr>
<td>
AutoBind</td><td>
Gets or sets a value indicating whether properties of View are binded to ViewModel. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
Bounds</td><td>
Gets or sets the Bounds of the node.</td><td>
 Rect</td></tr>
<tr>
<td>
Constraints</td><td>
Gets or sets the Constraints Type.</td><td>
 Enum NodeConstraints.None NodeConstraints.Selectable  NodeConstraints.Draggable NodeConstraints.Resizable NodeConstraints.Rotatable NodeConstraints.InConnect NodeConstraints.OutConnect NodeConstraints.Connectable NodeConstraints.AllowPan  NodeConstraints.Default</td></tr>
<tr>
<td>
ID</td><td>
Gets or sets the ID of the node.</td><td>
 Object</td></tr>
<tr>
<td>
IsConnecting</td><td>
Specifies whether the node is connecting. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
IsGrouped</td><td>
Specifies whether the node can be grouped. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
IsSelected</td><td>
Specifies whether the node is selected. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
Key</td><td>
Gets or sets the Key of the node.</td><td>
 Object</td></tr>
<tr>
<td>
OffsetX</td><td>
Gets or sets the offset X-axis value of the node.</td><td>
 Double</td></tr>
<tr>
<td>
OffsetY</td><td>
Gets or sets the offset Y-axis value of the node.</td><td>
 Double</td></tr>
<tr>
<td>
ParentGroup</td><td>
Gets or sets the Parent Group of the node.</td><td>
 Object</td></tr>
<tr>
<td>
Pivot</td><td>
Gets or sets the Pivot of the node.</td><td>
 Point</td></tr>
<tr>
<td>
RotateAngle</td><td>
Gets or sets the Rotation Angle of the node.</td><td>
 Double</td></tr>
<tr>
<td>
Shape</td><td>
Gets or sets the Shape of the node.</td><td>
 Geometry</td></tr>
<tr>
<td>
ShapeStyle</td><td>
Gets or sets the Shape Style of the node.</td><td>
 Style</td></tr>
<tr>
<td>
SnapToObject</td><td>
This property overrides SfDiagram.SnapToObject and decides when the node is to be snapped.(To enable this, NodeConstraints.InheritSnapToObject should be removed from Node.Constraints).</td><td>
SnapToObject</td></tr>
<tr>
<td>
VirtualizationState</td><td>
Gets or sets the Virtualization State of the node.</td><td>
 VirtualizationState</td></tr>
<tr>
<td>
ZIndex</td><td>
Gets or sets the z-index of the node.</td><td>
 Int32</td></tr>
<tr>
<td>
Constraints</td><td>
Gets or sets the Constraints Type.</td><td>
EnumNodeConstraints. ResizeNorthEastNodeConstraints. ResizeEastNodeConstraints. ResizeSouthEastNodeConstraints. ResizeSouthNodeConstraints. ResizeSouthWestNodeConstraints. ResizeWestNodeConstraints. ResizeNorthWestNodeConstraints. ResizeNorth</td></tr>
<tr>
<td>
ConnectorPadding</td><td>
Gets or sets the ConnectorPadding of the Node. </td><td>
   Double</td></tr>
</table>


### IConnector Properties



The following table lists the Properties associated with IConnector of the SfDiagram control:

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
AutoBind</td><td>
Gets or sets a value indicating whether properties of View are binded to ViewModel. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
ConnectorGeometryStyle</td><td>
Gets or sets the Connector Geometry Style of the connector.</td><td>
 Style</td></tr>
<tr>
<td>
Constraints</td><td>
Gets or sets the Constraints of the connector.</td><td>
 Enum  ConnectorConstraints.Inherit ConnectorConstraints.Selectable ConnectorConstraints.SourceDraggable ConnectorConstraints.TargetDraggable ConnectorConstraints.EndDraggable ConnectorConstraints.EndThumbs ConnectorConstraints.SegmentThumbs ConnectorConstraints.Thumbs ConnectorConstraints.Bridging ConnectorConstraints.Routing ConnectorConstraints.Default</td></tr>
<tr>
<td>
Geometry</td><td>
Gets or sets the Geometry of the connector.</td><td>
 PathGeometry</td></tr>
<tr>
<td>
ID</td><td>
Gets or sets the ID of the connector.</td><td>
 Object</td></tr>
<tr>
<td>
IsSelected</td><td>
Specifies whether the connector is selected. The default value is set to true.</td><td>
 Boolean</td></tr>
<tr>
<td>
Key</td><td>
Gets or sets the Key of the connector.</td><td>
 Object</td></tr>
<tr>
<td>
ParentGroup</td><td>
Gets or sets the Parent Group of the connector.</td><td>
 Object</td></tr>
<tr>
<td>
SourceDecorator</td><td>
Gets or sets the Source Decorator of the connector.</td><td>
 Geometry</td></tr>
<tr>
<td>
SourceDecoratorStyle</td><td>
Gets or sets the Source Decorator Style of the connector.</td><td>
 Style</td></tr>
<tr>
<td>
SourceNode</td><td>
Gets or sets the Source Node of the connector.</td><td>
 Object</td></tr>
<tr>
<td>
SourcePoint</td><td>
Gets or sets the Source Point of the connector.</td><td>
 Point</td></tr>
<tr>
<td>
SourcePort</td><td>
Gets or sets the Source Port of the connector.</td><td>
 IPort</td></tr>
<tr>
<td>
TargetDecorator</td><td>
Gets or sets the Target Decorator of the connector.</td><td>
 Geometry</td></tr>
<tr>
<td>
TargetDecoratorStyle</td><td>
Gets or sets the Target Decorator Style of the connector.</td><td>
 Style</td></tr>
<tr>
<td>
TargetNode</td><td>
Gets or sets the Target Node of the connector.</td><td>
 Object</td></tr>
<tr>
<td>
TargetPoint</td><td>
Gets or sets the Target Point of the connector.</td><td>
 Point</td></tr>
<tr>
<td>
TargetPort</td><td>
Gets or sets the Target Port of the connector.</td><td>
 IPort</td></tr>
<tr>
<td>
ZIndex</td><td>
Gets or sets the z-index of the connector.</td><td>
 Int32</td></tr>
<tr>
<td>
BezierSmooth</td><td>
Enables or disables the ability to customize line smoothness.</td><td>
EnumBezierSmooth.NoneBezierSmooth.SymmetricAngleBezierSmooth.SymmetricDistanceBezierSmooth.Symmetric</td></tr>
<tr>
<td>
CornerRadius</td><td>
Gets or sets the CornerRadius of the LineConnector. </td><td>
   Double</td></tr>
<tr>
<td>
SourcePadding</td><td>
Gets or sets the SourcePadding of the LineConnector. </td><td>
   Double</td></tr>
<tr>
<td>
TargetPadding</td><td>
Gets or sets the SourcePadding of the LineConnector. </td><td>
    Double</td></tr>
</table>


### IConnectorSegment properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
BezierSmooth</td><td>
Gets or sets the BezierSmooth property.</td><td>
EnumBezierSmooth.NoneBezierSmooth.SymmetricAngleBezierSmooth.SymmetricDistanceBezierSmooth.Symmetric</td></tr>
<tr>
<td>
Constraints</td><td>
Decides whether to consider IConnector.Smooth or IConnectorSegment.Smooth</td><td>
EnumConstraints.NoneConstraints.Inherit</td></tr>
</table>

### INodePort Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
Node</td><td>
Gets or sets the Node of the NodePort.</td><td>
 Object</td></tr>
<tr>
<td>
NodeOffsetX</td><td>
Gets or sets the NodeOffsetX value of the NodePort.</td><td>
 Double</td></tr>
<tr>
<td>
NodeOffsetY</td><td>
Gets or sets the NodeOffsetY value of the NodePort.</td><td>
 Double</td></tr>
<tr>
<td>
UnitMode</td><td>
Gets or sets the Unit Mode of the NodePort.</td><td>
 UnitMode</td></tr>
<tr>
<td>
ConnectorPadding</td><td>
Gets or sets the ConnectorPadding of the Port. </td><td>
   Double</td></tr>
</table>




### ISymbol Properties



The following table lists the Properties associated with ISymbol of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
Symbol</td><td>
Gets or sets the Symbol of the NodePort.</td><td>
 Object</td></tr>
<tr>
<td>
SymbolTemplate</td><td>
Gets or sets the Symbol Template of the NodePort.</td><td>
 DataTemplate</td></tr>
</table>


### Stencil Properties



The following table lists the Properties associated with Stencil of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
SelectedFilter</td><td>
Gets or sets the selected Filter of the NodePort.</td><td>
 SymbolFilterProvider</td></tr>
</table>


### Annotations Properties



The following table lists the Properties associated with Annotations of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
Alignment</td><td>
Specifies the alignment for the annotation when used with connectors.</td><td>
 ConnectorAnnotationAlignment.Center ConnectorAnnotationAlignment.Source ConnectorAnnotationAlignment.Target</td></tr>
<tr>
<td>
Content</td><td>
Specifies the content for the annotation.</td><td>
 String</td></tr>
<tr>
<td>
EditTemplate</td><td>
Specifies the template for editing the annotation.</td><td>
 DataTemplate</td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Specifies the horizontal alignment for the annotation when used with Nodes.</td><td>
 HorizontalAlignment.Center HorizontalAlignment.Left HorizontalAlignment.Right HorizontalAlignment.Stretch</td></tr>
<tr>
<td>
Mode</td><td>
Specifies the mode for editing the annotation during initial loading; whether it is in view mode or edit mode.</td><td>
 ContentEditorMode.Edit ContentEditorMode.View</td></tr>
<tr>
<td>
VerticalAlignment</td><td>
Specifies the vertical alignment for the annotation when used with Nodes.</td><td>
 VerticalAlignment.Center VerticalAlignment.Bottom VerticalAlignment.Top VerticalAlignment.Stretch</td></tr>
<tr>
<td>
ViewTemplate</td><td>
Specifies the template for viewing the annotation.</td><td>
 DataTemplate</td></tr>
</table>


### Layout Properties



The following table lists the Layout Properties associated with Directed Tree Layout of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
 Value</th></tr>
<tr>
<td>
HorizontalSpacing</td><td>
Specifies the horizontal spacing between the nodes.</td><td>
 Double</td></tr>
<tr>
<td>
LayoutRoot</td><td>
Specifies the root element of the tree.</td><td>
 Object</td></tr>
<tr>
<td>
SpaceBetweenSubTrees</td><td>
Specifies the space between sub trees.</td><td>
 Double</td></tr>
<tr>
<td>
VerticalSpacing</td><td>
Specifies the vertical spacing between the nodes.</td><td>
 Double</td></tr>
<tr>
<td>
Bounds</td><td>
Gets or sets the bounds where the layout has to be placed.</td><td>
Rect</td></tr>
<tr>
<td>
Margin</td><td>
Gets or sets the margin of the layout.</td><td>
Thickness</td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Gets or sets horizontal alignment of the layout.</td><td>
HorizontalAlignment enumHorizontalAlignment.CenterHorizontalAlignment.LeftHorizontalAlignment.Right</td></tr>
<tr>
<td>
VerticalAlignment</td><td>
Gets or sets vertical alignment of the layout.</td><td>
VerticalAlignment enumVerticalAlignment.CenterVerticalAlignment.TopVerticalAlignment.Bottom</td></tr>
</table>




### PageSettings Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
PageWidth</td><td>
Gets or sets the width of the page.</td><td>
doubleDefault value: 0</td></tr>
<tr>
<td>
PageHeight</td><td>
Gets or sets the page height.</td><td>
doubleDefault value: 0</td></tr>
<tr>
<td>
MultiplePage</td><td>
Gets or sets whether multiple page is enabled.</td><td>
boolDefault value: false</td></tr>
<tr>
<td>
ShowPageBreaks</td><td>
Gets or sets the visibility of page break lines.</td><td>
boolDefault value: true</td></tr>
<tr>
<td>
PageOrientation</td><td>
Gets or sets the PageOrientation.</td><td>
enum-PageOrientationPageOrientation.LandscapePageOrientation.Portrait</td></tr>
<tr>
<td>
PrintMargin</td><td>
Gets or sets the PrintMargin.</td><td>
ThicknessDefault value: new Thickness(24).</td></tr>
<tr>
<td>
PageBackground</td><td>
Gets or sets the PageBackground.</td><td>
Brush</td></tr>
<tr>
<td>
PageBorderBrush</td><td>
Gets or sets the PageBorderBrush.</td><td>
Brush</td></tr>
<tr>
<td>
PageBorderThickness</td><td>
Gets or sets the PageBorderThickness.</td><td>
Thickness</td></tr>
<tr>
<td>
Unit</td><td>
Gets or sets the Unit.</td><td>
MeasurementUnit</td></tr>
<tr>
<td>
OffPageMinMargin</td><td>
Gets or sets the OffPageMinMargin.</td><td>
Thickness</td></tr>
<tr>
<td>
OffPageMaxMargin</td><td>
Gets or sets the OffPageMaxMargin.</td><td>
Thickness</td></tr>
</table>

### Property

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value </th></tr>
<tr>
<td>
ScrollLimit</td><td>
Gets or sets the scrollable area is restricted / not. </td><td>
ScrollLimit. InfinityScrollLimit. DiagramScrollLimit. Limited</td></tr>
<tr>
<td>
AutoScrollBorder</td><td>
Gets or sets the distance inside the Diagram viewport boundaries to enable the AutoScroll. AutoScroll starts once the pointer reaches this area. AutoScroll stops when the pointer is left from this area. Default value is (20, 20, 20, 20). </td><td>
Thickness </td></tr>
<tr>
<td>
ScrollableArea </td><td>
Gets or sets the limited area that is the only area to view by auto scrolling.  Default value is Empty. This property is applicable only when ScrollLimit as Limited. </td><td>
Rect </td></tr>
<tr>
<td>
MinimumScrollableArea </td><td rowspan = "2">
Gets or sets the limited area (Minimum point (i.e Left, Top) and Maximum point (i.e Right, Bottom)) that is the only area to view by auto scrolling. Default value is Null. This property is applicable only when ScrollLimit as Limited.When these properties does not set, compiler gets ScrollableArea property automatically. </td><td rowspan = "2">
Point</td></tr>
<tr>
<td>
MaximumScrollableArea </td></tr>
</table>


## Scroll Limit

The following table lists the Properties associated with ScrollLimit of PageSettings. 

<table>
<tr>
<th>
Enum Field</th><th>
Description</th></tr>
<tr>
<td>
Infinity </td><td>
AutoScroll is not stopped until pointer leaves from the AutoScrollBorder.</td></tr>
<tr>
<td>
Diagram</td><td>
AutoScroll is stopped when the captured element / pointer reaches the boundaries of the Diagram. </td></tr>
<tr>
<td>
Limited </td><td>
AutoScroll is stopped when the captured element / pointer reaches the limited scrollable area. </td></tr>
</table>




## SfDiagram Events



The following table lists the Events associated with the SfDiagram control:

<table>
<tr>
<th>
Event</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
ConnectorSourceChangedEvent</td><td>
ChangeEventArgs<object, ConnectorChangedArgs> </td><td>
Event: Raised when the source of the connector is changed. Event cannot be cancelled.<br><br>Event Args: ChangeEventArgs</td></tr>
<tr>
<td>
ConnectorTargetChangedEvent</td><td>
ChangeEventArgs<object, ConnectorChangedArgs></td><td>
Event: Raised when the target of the connector is changed. Event cannot be cancelled.Event Args: ChangeEventArgs</td></tr>
<tr>
<td>
ItemAdded</td><td>
ItemAddedEventArgs</td><td>
Event: Raised when an item is added. Event cannot be cancelled.Event Args: ItemAddedEventArgs</td></tr>
<tr>
<td>
ItemDeleted</td><td>
 DiagramEventArgs</td><td>
Event: Raised when an item is deleted. Event cannot be cancelled.Event Args: DiagramEventArgs</td></tr>
<tr>
<td>
ItemDoubleTappedEvent</td><td>
DiagramEventArgs</td><td>
Event: Raised when an item is double-tapped. Event cannot be cancelled.<br><br>Event Args: DiagramEventArgs</td></tr>
<tr>
<td>
ItemTappedEvent</td><td>
DiagramEventArgs</td><td>
Event: Raised when an item is tapped. Event cannot be cancelled.Event Args: DiagramEventArgs</td></tr>
<tr>
<td>
ViewPortChangedEvent</td><td>
ChangeEventArgs<object, ScrollChanged></td><td>
Event: Raised when the viewport or scroll changes. Event cannot be cancelled. Event Args: ViewPortChangeEventArgs</td></tr>
<tr>
<td>
ItemSelectingEvent</td><td>
DiagramPreviewEventArgs</td><td>
Event: Raised before a diagram object is selected from the SfDiagram. Cancelable event.Event Args: DiagramPreviewEventArgs</td></tr>
<tr>
<td>
ItemUnSelectingEvent</td><td>
DiagramPreviewEventArgs</td><td>
Event: Raised before a diagram object is unselected from the SfDiagram. Cancelable event.Event Args: DiagramPreviewEventArgs</td></tr>
<tr>
<td>
ItemSelectedEvent</td><td>
DiagramEventArgs</td><td>
Event: Raised when an item is selected. Event cannot be cancelled.Event Args: DiagramEventArgs</td></tr>
<tr>
<td>
ItemUnSelectedEvent</td><td>
DiagramEventArgs</td><td>
Event: Raised when an item is unselected. Event cannot be cancelled.Event Args: DiagramEventArgs</td></tr>
</table>




### SfDiagram Event Arguments

<table>
<tr>
<th>
Event Args</th><th>
Description</th></tr>
<tr>
<td>
ChangeEventArgs<object,ConnectorChangedArgs></td><td>
ChangeEventArgsItem:  Gets Connector whose source or target is changed.OldValue: Gets the old values of the source or target.NewValue: Gets the new values of the source or target.ConnectorChangedArgsNode: Gets connector’s source or target as a node.Point: Gets connector’s source or target as a point.Port: Gets connector’s source or target as a port.Group: Gets connector’s source or target as a group.DragState: Gets connector’s DragState (enum)   DragState.None   DragState.Starting   DragState.Started   DragState.Dragging   DragState.Completed</td></tr>
<tr>
<td>
ItemAddedEventArgs</td><td>
Item: Gets new object as a node, connector, or group that is added to SfDiagram collections.     ItemSource: From where the item is created (Stencil/Drawing Tool/Unknown).</td></tr>
<tr>
<td>
DiagramEventArgs</td><td>
Item: Gets new object as a node, connector, or group where the event is raised.</td></tr>
<tr>
<td>
ChangeEventArgs<object, ScrollChanged></td><td>
ChangeEventArgsItem:  Gets the SfDiagram where the event is raised.OldValue: Gets the old scroll values.NewValue: Gets the new scroll values.ScrollChangedContentBounds:  Gets the size and position of the Diagram page based on its children.CurrentZoom: Gets the zoom value.MaxZoom:  Gets the new max zoom value.MinZoom: Gets the new mininmum zoom value.PageBounds:  Gets the size and position of diagram page based on its children and page settings.ScrollFactor:  Gets the scroll factor value.ViewPort:  Gets the viewport value.ZoomFactor: Gets zoom factor value.</td></tr>
<tr>
<td>
DiagramPreviewEventArgs</td><td>
Item: Gets new object as a node, connector, or group where the event is raised.Cancel: When set to true, this is cancelled.</td></tr>
</table>

### Public or Virtual Methods

The following table lists the Public or Virtual Methods associated with the SfDiagram control:

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Connectors</td><td>
Add(&lt;AnyType &gt;arg1)</td><td>
To Add any object(ConnectorViewModel, IConnector) into SfDiagram.</td></tr>
<tr>
<td>
Groups</td><td>
Add(&lt;AnyType &gt;arg1)</td><td>
To Add any object(GroupViewModel, IGroup) into SfDiagram.</td></tr>
<tr>
<td>
Nodes</td><td>
Add(&lt;AnyType &gt;arg1)</td><td>
To Add any object(NodeViewModel, INode) into SfDiagram.</td></tr>
<tr>
<td>
PrintTaskRequested</td><td>
virtual void PrintTaskRequested(PrintManager sender, PrintTaskRequestedEventArgs args)</td><td>
This is the event handler for PrintManager.PrintTaskRequested</td></tr>
<tr>
<td>
GetPrintPreviewPage</td><td>
virtual void GetPrintPreviewPage(object sender, GetPreviewPageEventArgs e)</td><td>
This method provides a specific print preview page, in the form of a UIElement, to an instance of PrintDocument. </td></tr>
<tr>
<td>
CreatePrintPreviewPages</td><td>
virtual void CreatePrintPreviewPages(object sender, PaginateEventArgs e)</td><td>
This creates print preview pages for the app.</td></tr>
<tr>
<td>
AddPrintPages</td><td>
virtual void AddPrintPages(object sender, AddPagesEventArgs e)</td><td>
This provides all of the pages to be printed, in the form of UIElements, to an instance of PrintDocument. </td></tr>
</table>


### SfDiagram Event

<table>
<tr>
<th>
Event</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
AutoScrolled </td><td>
AutoScrolledArgs </td><td>
Event: Raised when pointer reaches the AutoScrollBorder. Event can be cancelled.</td></tr>
</table>


### SfDiagram Event Arguments



<table>
<tr>
<th>
Event Args</th><th>
Description </th></tr>
<tr>
<td>
AutoScrolledArgs </td><td>
Cancel               : when set to true, this is cancelled. Item                   : Gets the item that is captured by pointer Delay                 : Gets or sets the time interval between each auto scroll (Related to ScrollSpeed). DragDelay         : Gets or sets the distance to scroll for each auto scroll (Related to ScrollSpeed).DistanceFromDiagram:      Gets or sets the distance outside the Diagram Viewport boundaries to remains the AutoScroll </td></tr>
</table>




### Public or Virtual Methods

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description </th></tr>
<tr>
<td>
OnAutoScroll </td><td>
virtual void OnAutoScroll(AutoScrolledArgs args) </td><td>
This method sets the default value for AutoScrolledArgs when you create the instance for custom SfDiagram.</td></tr>
</table>




### INode Methods

The following table lists the INode Methods associated with the SfDiagram control:



<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Annotations</td><td>
Add(&lt;IAnnotation&gt;arg1)</td><td>
To Add object(IAnnotation) into SfDiagram</td></tr>
<tr>
<td>
Ports</td><td>
Add(&lt;INodePort&gt;arg1)</td><td>
To Add object(INodePort) into SfDiagram</td></tr>
</table>


### IConnector Methods

The following table lists the IConnector Methods associated with the SfDiagram control:



<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Annotations</td><td>
Add(&lt;IAnnotation&gt;arg1)</td><td>
To Add object(IAnnotation) into SfDiagram</td></tr>
<tr>
<td>
Segments</td><td>
Add(&lt;IConnectorSegment&gt;arg1)</td><td>
To Add object(IConnectorSegment) into SfDiagram</td></tr>
</table>


### IGroup Methods

The following table lists the IGroup Methods associated with the SfDiagram control:



<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
Connectors</td><td>
Add(&lt;AnyType&gt;arg1)</td><td>
To Add any object(ConnectorViewModel, IConnector) into SfDiagram</td></tr>
<tr>
<td>
Groups</td><td>
Add(&lt;AnyType&gt;arg1)</td><td>
To Add any object(GroupViewModel, IGroup) into SfDiagram</td></tr>
<tr>
<td>
Nodes</td><td>
Add(&lt;AnyType&gt;arg1)</td><td>
To Add any object(NodeViewModel, INode) into SfDiagram</td></tr>
</table>


### Stencil Methods



The following table lists the Stencil Methods associated with the SfDiagram control:



<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
SymbolFilters</td><td>
Add(&lt;ISymbolFilterProvider&gt;arg1)</td><td>
To Add object(ISymbolFilterProvider) into SfDiagram</td></tr>
<tr>
<td>
SymbolGroups</td><td>
Add(&lt;ISymbolGroupProvider&gt;arg1)</td><td>
To Add object(ISymbolGroupProvider) into SfDiagram</td></tr>
<tr>
<td>
SymbolSource</td><td>
Add(&lt;ISymbol&gt;arg1)</td><td>
To Add object(ISymbol) into SfDiagram</td></tr>
</table>


### ILineSegment Properties

The following table lists the properties associated with ILineSegment of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Point</td><td>
Specifies the end point of the line segment.</td><td>
Point</td></tr>
</table>


### ILineSegmentLength Properties

The following table lists the properties associated with ILineSegmentLength of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Length</td><td>
Specifies the length of the line segment.</td><td>
DoubleExt</td></tr>
<tr>
<td>
Angle</td><td>
Specifies the angle of the line segment.</td><td>
DoubleExt</td></tr>
<tr>
<td>
AngleMode</td><td>
Specifies the mode of the angle, whether it is relative or absolute.</td><td>
RelativeMode.AbsoluteRelativeMode.Relative</td></tr>
</table>


### IOrthogonalSegment Properties

The following table lists the properties associated with IOrthogonalSegment of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Length</td><td>
Specifies the length of the line segment.</td><td>
DoubleExt</td></tr>
<tr>
<td>
OrthogonalDirection</td><td>
Specifies the direction of the line segment.</td><td>
OrthogonalDirection.AutoOrthogonalDirection.LeftOrthogonalDirection.TopOrthogonalDirection.RightOrthogonalDirection.BottomOrthogonalDirection.StraightOrthogonalDirection.ClockWise90OrthogonalDirection.OppositeOrthogonalDirection.AntiClockWise90</td></tr>
</table>


### IQuadraticCurveSegment Properties

The following table lists the properties associated with IQuadraticCurveSegment of the SfDiagram control:

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Point1</td><td>
Specifies the control point of the line segment.</td><td>
Point</td></tr>
<tr>
<td>
Point2</td><td>
Specifies the end point of the line segment.</td><td>
Point</td></tr>
</table>


### ICubicCurveSegment Properties

The following table lists the properties associated with ICubicCurveSegment of the SfDiagram control:



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Point1</td><td>
Specifies the first control point of the line segment.</td><td>
Point</td></tr>
<tr>
<td>
Point2</td><td>
Specifies the second control point of the line segment.</td><td>
Point</td></tr>
<tr>
<td>
Point3</td><td>
Specifies the end point of the line segment.</td><td>
Point</td></tr>
<tr>
<td>
Vector1</td><td>
Gets or sets the vector format of the first control point(ICubicCurveSegment.Point1)</td><td>
Vector</td></tr>
<tr>
<td>
Vector2</td><td>
Gets or sets the vector format of the second control point(ICubiccurveSegment.Point2)</td><td>
Vector</td></tr>
</table>


### Snapping to Gridlines

Gridlines and snapping can be defined by the SfDiagram.SnapSettings property.

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
SnapSettings</td><td>
Defines SnapConstraints and Gridlines.</td><td>
SnapSettings</td></tr>
</table>


### SfDiagram.SnapSettings Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
SnapConstraints</td><td>
Enables or disables the visibility of gridlines and the snapping feature.</td><td>
EnumSnapConstraints.ShowHorizontalLinesSnapConstraints.ShowVerticalLinesSnapConstraints.ShowLinesSnapConstraints.SnapToHorizontalLinesSnapConstraints.SnapToVerticalLinesSnapConstraints.SnapToLinesSnapConstraints.AllSnapConstraints.None</td></tr>
<tr>
<td>
HorizontalGridlines</td><td>
Defines the style and the space between horizontal gridlines.</td><td>
Gridlines</td></tr>
<tr>
<td>
VerticalGridlines</td><td>
Defines the style and the space between vertical gridlines.</td><td>
Gridlines</td></tr>
</table>




### Gridlines Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
Strokes</td><td>
Defines the style for a group or pattern of lines. The pattern is repeated throughout the Diagram.</td><td>
new IEnumerable<Style>(){Style values};</td></tr>
<tr>
<td>
LineInterval</td><td>
Defines the spacing between a group or pattern of lines. That pattern is repeated throughout the Diagram.</td><td>
new IEnumerable<double>(){double values};</td></tr>
<tr>
<td>
SnapInterval</td><td>
Defines a set or pattern of intervals.</td><td>
new IEnumerable<double>(){double values};</td></tr>
<tr>
<td>
DynamicZoom</td><td>
Describes whether gridlines have to be updated on zooming and panning.</td><td>
True/False</td></tr>
</table>


### SfDiagram.SnapSetting Properties

The following table lists the properties associated with guidelines in the SfDiagram control:

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value</th></tr>
<tr>
<td>
SnapToObject</td><td>
Enables or disables the appearance of guidelines and decides when guidelines have to be created.</td><td>
SnapToObject-enumSnapToObject.LeftLeftSnapToObject.LeftRightSnapToObject.LeftSnapToObject.RightRightSnapToObject.RightLeftSnapToObject.RightSnapToObject.TopTopSnapToObject.TopBottomSnapToObject.TopSnapToObject.BottomBottomSnapToObject.BottomTopSnapToObject.BottomSnapToObject.HorizontalCenterSnapToObject.VerticalCenterSnapToObject.HorizontalSpacingSnapToObject.VerticalSpacingSnapToObject.WidthSnapToObject.HeightSnapToObject.Size</td></tr>
</table>


